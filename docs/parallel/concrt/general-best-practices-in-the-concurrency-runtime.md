---
title: Общие рекомендации в среде выполнения с параллелизмом | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2cd9cffa76ce179f478422af9c8efce380a2465
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>Общие рекомендации в среде выполнения с параллелизмом
В этом документе описываются рекомендации, относящиеся к различным областям среды выполнения с параллелизмом.  
  
##  <a name="top"></a> Разделы  
 Этот документ содержит следующие разделы.  
  
- [Используйте конструкции совместной синхронизации, когда это возможно](#synchronization)  
  
- [Избегайте продолжительных задач, не выполняющих передачу](#yield)  
  
- [Использование лимита подписки для операций смещения, блокирующие или иметь высокую задержку](#oversubscription)  
  
- [Используйте функции параллельного управления памятью по возможности](#memory)  
  
- [Используйте RAII для управления временем существования параллельных объектов](#raii)  
  
- [Не создавайте параллельные объекты в глобальной области видимости](#global-scope)  
  
- [Не используйте параллельные объекты в сегментах общих данных](#shared-data)  
  
##  <a name="synchronization"></a> Используйте конструкции совместной синхронизации, когда это возможно  
 Среда выполнения с параллелизмом предоставляет множество параллельно безопасно конструкции, которые не требуют внешнему объекту синхронизации. Например [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс предоставляет параллельно безопасно append и операций доступа к элементу. Тем не менее для случаев, когда вам требуется монопольный доступ к ресурсу, среда выполнения предоставляет [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), и [параллелизма :: событие](../../parallel/concrt/reference/event-class.md) классы. Эти типы ведут себя совместно; Таким образом планировщик может перераспределить ресурсы обработки к другому контексту, пока первая задача ожидает получения данных. По возможности используйте эти типы синхронизации, а не другие механизмы, например предоставляемые интерфейсом Windows API, не предназначенные для совместно. Дополнительные сведения об этих типах синхронизации и пример кода см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md) и [Сравнение структур данных синхронизации с Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 [[В начало](#top)]  
  
##  <a name="yield"></a> Избегайте продолжительных задач, не выполняющих передачу  
 Поскольку планировщик заданий работает совместно, он не обеспечивает распределение ресурсов между задачами. Таким образом задача может запускаться другие задачи. Хотя это приемлемо, в некоторых случаях, в других случаях это может привести к взаимоблокировке или нехватку ресурсов.  
  
 В следующем примере выполняется несколько задач, чем количество выделенных ресурсов обработки. Первая задача не уступают планировщику заданий и поэтому вторая задача не запускается до завершения первой задачи.  
  
 [!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]  
  
 В этом примере выводятся следующие данные:  
  
 1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000  
  

 Существует несколько способов обеспечить взаимодействие между двумя задачами. Один из способов — выполнить передачу с планировщиком задач в длительную задачу. В следующем примере изменяется `task` функции, вызываемой [Concurrency::Context:: yield](reference/context-class.md#yield) метод уступающего выполнение планировщику заданий, чтобы могла запуститься другая задача.  

  
 [!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]  
  
 В этом примере выводятся следующие данные:  
  
```Output  
1: 250000000  
2: 250000000  
1: 500000000  
2: 500000000  
1: 750000000  
2: 750000000  
1: 1000000000  
2: 1000000000  
```  
  
 `Context::Yield` Действует только на другой активный поток в планировщике, к которому принадлежит текущий поток, упрощенной задачи или другому потоку операционной системы. Этот метод не уступает работе, запланированной для выполнения в [concurrency::task_group](reference/task-group-class.md) или [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта, но еще не запущен.  
  
 Существуют другие способы обеспечить совместную работу длительно выполняемых задач. Можно разделить большие задачи на более мелкие подзадачи. Можно также включить превышение лимита подписки во время продолжительной операции. Превышение лимита подписки позволяет создать больше потоков, чем количество доступных аппаратных потоков. Превышение лимита подписки особенно полезна в случаях, когда длительную задачу связана с большими задержками, например, чтение данных с диска или из сетевого подключения. Дополнительные сведения о упрощенными задачами и превышение лимита подписки см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 [[В начало](#top)]  
  
##  <a name="oversubscription"></a> Использование лимита подписки для операций смещения, блокирующие или иметь высокую задержку  
 Среда выполнения с параллелизмом предоставляет примитивы синхронизации, такие как [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md), позволяющие задачам выполнять совместную блокировку и уступать друг другу. Когда одна задача совместно блокирует либо передачу, планировщик может перераспределить ресурсы обработки к другому контексту, пока первая задача ожидает получения данных.  
  
 Существуют случаи, в которых нельзя использовать механизм совместной блокировки, предоставляемые средой выполнения с параллелизмом. Например внешние библиотеки, используемой использовать другой механизм синхронизации. Еще один пример — при выполнении операции, которая может иметь большой объем задержки, например, при использовании Windows API `ReadFile` функция для чтения данных из сетевого подключения. В этих случаях превышение лимита подписки можно включить другие задачи для запуска, когда другая задача находится в состоянии простоя. Превышение лимита подписки позволяет создать больше потоков, чем количество доступных аппаратных потоков.  
  
 Рассмотрим следующую функцию `download`, который загружает файл в заданный URL-адрес. В этом примере используется [Concurrency::Context:: Oversubscribe](reference/context-class.md#oversubscribe) метод, чтобы временно увеличить количество активных потоков.  

 [!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]  
  
 Поскольку `GetHttpFile` функция выполняет операцию с возможностью задержек, превышение лимита подписки можно включить другие задачи для запуска, пока текущая задача ожидает получения данных. Полную версию этого примера см. в разделе [как: превышение лимита подписки используется для смещения задержки](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 [[В начало](#top)]  
  
##  <a name="memory"></a> Используйте функции параллельного управления памятью по возможности  

 Использовать функции управления памятью, [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) и [concurrency::Free](reference/concurrency-namespace-functions.md#free)при работе с детализированными задачами, постоянно выделяющими небольшие объекты с коротким временем существования. Среда выполнения с параллелизмом содержит отдельный кэш памяти для каждого выполняемого потока. `Alloc` И `Free` функции выделяют и освобождают память из такого кэша без использования блокировки или барьеры памяти.  
  
 Дополнительные сведения об этих функциях управления памяти см. в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md). Пример использования этих функций см. в разделе [как: использование функций Alloc и Free для повышения производительности памяти](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).  
  
 [[В начало](#top)]  
  
##  <a name="raii"></a> Используйте RAII для управления временем существования параллельных объектов  
 Среда выполнения с параллелизмом использует обработку исключений для реализации функций, таких как отмены. Таким образом можно напишите код, безопасный в отношении исключений, если вызов среды выполнения или другую библиотеку, которая вызывает среду выполнения.  
  
 *Получение ресурса есть инициализация* шаблон (RAII) — один из способов спокойно управления временем жизни объекта параллелизма в данной области. При использовании шаблона RAII структура данных выделяется в стеке. Что структуры данных инициализирует или приобретает ресурс, когда он создается и уничтожает или освобождает ресурс, при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Этот шаблон полезен, если функция содержит несколько `return` инструкции. Этот шаблон также помогает писать безопасный в отношении исключений код. Когда `throw` инструкция вызывает стека, деструктор для объекта RAII; таким образом, всегда правильно удален или освобождения ресурса.  
  
 Среда выполнения определяет несколько классов, использующих шаблон RAII, например, [Concurrency::critical_section:: scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) и [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class). Эти вспомогательные классы называются *блокировками с областью*. Эти классы обеспечивают несколько преимуществ при работе с [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) или [concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) объектов. Конструктор этих классов получает доступ к предоставленному `critical_section` или `reader_writer_lock` объект; деструктор выпуски доступ к этому объекту. Так как блокировка с областью автоматически освобождает доступ к объекту взаимного исключения, когда он будет уничтожен, вам не требуется вручную разблокировать базового объекта.  
  
 Рассмотрим следующий класс `account`, который определяется внешней библиотеки и не может быть изменено.  
  
 [!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]  
  
 В следующем примере выполняется несколько транзакций на `account` объекта в параллельном режиме. В этом примере `critical_section` объект для синхронизации доступа к `account` объекта, так как `account` класс не является безопасным в режиме параллелизма. Каждая параллельная операция использует `critical_section::scoped_lock` объекта, чтобы гарантировать, что `critical_section` объекта не заблокирован, если операция заканчивается успешно или неуспешно. Если баланс счета, является отрицательной, `withdraw` операция завершается неудачей, создавая исключение.  
  
 [!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]  
  
 В этом примере получается следующий результат:  
  
```Output  
Balance before deposit: 1924  
Balance after deposit: 2924  
Balance before withdrawal: 2924  
Balance after withdrawal: -76  
Balance before withdrawal: -76  
Error details:  
    negative balance: -76  
```  
  
 Дополнительные примеры, использующие шаблон RAII для управления временем существования параллельных объектов см. в разделе [Пошаговое руководство: удаление задач из потока пользовательского интерфейса](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [как: использование класса Context для реализации совместной Семафор](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), и [как: использование лимита подписки для устранения задержек](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
 [[В начало](#top)]  
  
##  <a name="global-scope"></a> Не создавайте параллельные объекты в глобальной области видимости  
 При создании объекта параллелизма в глобальной области в приложении могут возникнуть такие проблемы, как взаимоблокировка или нарушение прав доступа к памяти.  
  
 Например, при создании объекта исполняющей среды с параллелизмом среда создает планировщик по умолчанию, если он еще не создан. Объект среды выполнения, созданный при конструировании глобального объекта, соответственно вызовет то, что среда выполнения создаст этот планировщик по умолчанию. Однако этот процесс принимает внутреннюю блокировку, которая может помешать инициализации других объектов, поддерживающих инфраструктуру исполняющей среды с параллелизмом. Эта внутренняя блокировка может потребоваться другому, еще не инициализированному, объекту инфраструктуры, и поэтому может привести к возникновению взаимоблокировки в приложении.  
  
 В следующем примере показано создание глобального [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) объекта. Эта схема применяется не только к классу `Scheduler`, но и ко всем остальным типам, предоставленным исполняющей средой с параллелизмом. Рекомендуется не использовать эту схему, поскольку она может привести к неожиданному поведению в приложении.  
  
 [!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]  
  
 Примеры правильного способа создания `Scheduler` объектов, в разделе [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 [[В начало](#top)]  
  
##  <a name="shared-data"></a> Не используйте параллельные объекты в сегментах общих данных  
 Среда выполнения с параллелизмом не поддерживает использование параллельных объектов в разделе общих данных, например, секции данных, созданный [data_seg](../../preprocessor/data-seg.md) `#pragma` директивы. Несогласованные или недопустимое состояние объекта параллелизма, которые доступны через границы процессов может подвергнуть среды выполнения.  
  
 [[В начало](#top)]  
  
## <a name="see-also"></a>См. также  
 [Рекомендации для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)   
 [Сравнение структур данных синхронизации с интерфейсом Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)   
 [Как: использование функций Alloc и Free для повышения производительности памяти](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)   
 [Как: использование лимита подписки для устранения задержек](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)   
 [Как: использование класса Context для реализации семафора](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Пошаговое руководство: Удаление задач из потока пользовательского интерфейса](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)   
 [Рекомендации в библиотеке параллельных шаблонов](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Рекомендации по работе с библиотекой асинхронных агентов](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
