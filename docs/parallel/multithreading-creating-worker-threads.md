---
title: 'Многопоточность: Создание рабочих потоков | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 175fc018ddba436f9a331f861a492dcd43e1ec1e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-creating-worker-threads"></a>Многопоточность. Создание рабочих потоков
Рабочий поток обычно используется для обработки фоновых задач, которые пользователь не должен ожидать, чтобы продолжить работу с приложением. Хорошими примерами рабочих потоков могут быть задачи, такие как повторное вычисление и печати в фоновом режиме. В этом разделе подробно описываются действия, необходимые для создания рабочего потока. Ниже приведен список разделов.  
  
-   [Запуск потока](#_core_starting_the_thread)  
  
-   [Реализация функции управления](#_core_implementing_the_controlling_function)  
  
-   [Пример](#_core_controlling_function_example)  
  
 Создание рабочего потока является относительно простой задачей. Для запуска потока требуются только два этапа: реализация функции управления и запуска этого потока. Нет необходимости наследовать класс от [CWinThread](../mfc/reference/cwinthread-class.md). Если вам требуется специальная версия, можно наследовать класс `CWinThread`, но не является обязательным для большинства простых рабочих потоков. Можно использовать `CWinThread` без изменений.  
  
##  <a name="_core_starting_the_thread"></a> Запуск потока  
 Существует две перегруженные версии `AfxBeginThread`:, можно создать только рабочих потоков и который может создаваться потоков пользовательского интерфейса и рабочие потоки. Чтобы начать выполнение рабочего потока с помощью первой перегрузки, вызовите [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), указав следующие сведения:  
  
-   Адрес функции управления.  
  
-   Параметр, передаваемый в функцию управления.  
  
-   (Необязательно) Необходимый приоритет потока. Значение по умолчанию используется обычный приоритет. Дополнительные сведения о доступных уровнях приоритета см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
-   (Необязательно) Размер требуемой стека для потока. По умолчанию используется тот же размер стека, что и для создания потока.  
  
-   (Необязательно) **CREATE_SUSPENDED** Если требуется, чтобы поток мог быть создан в приостановленном состоянии. Значение по умолчанию равно 0 или запустить поток в обычном режиме.  
  
-   (Необязательно) Атрибуты требуемой безопасности. Значение по умолчанию — такой же доступ, как родительского потока. Дополнительные сведения о формате информации о безопасности см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread` Создает и инициализирует `CWinThread` объекта, запускает его и возвращает его адрес, чтобы ссылаться на него позднее. Проверяет вносятся во всей процедуры, убедитесь, что все объекты, освобожденных должным образом вызывать любую часть создания.  
  
##  <a name="_core_implementing_the_controlling_function"></a> Реализация функции управления  
 Функция управления определяет поток. При вводе этой функции поток запускается, и при завершении работы, поток завершается. Эта функция должна иметь следующий прототип:  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 Параметр имеет одно значение. Значение, которое эта функция получает в этот параметр имеет значение, которое было передано в конструктор при создании объекта потока. Функция управления может интерпретировать это значение любым образом, он выбирает. Его можно рассматривать как скалярное значение или указатель на структуру, содержащую несколько параметров, или его можно пропустить. Если параметр ссылается на структуру, структуру может использоваться не только для передачи данных из вызывающего потока, но также и для передачи данных из потока вызывающего объекта. При использовании такой структуры для передачи данных обратно в вызывающий поток необходимо уведомить вызывающий объект, когда результаты готовы. Сведения о связи рабочего потока с вызывающим объектом см. в разделе [Многопоточность: советы про программированию](../parallel/multithreading-programming-tips.md).  
  
 При завершении функции, он должен возвращать **UINT** значение, указывающее причину завершения. Как правило этот код выхода: 0 в случае успеха другие значения, означающие различные типы ошибок. Это полностью зависит от реализации. Некоторые потоки могут поддерживать счетчики объектов и возвращать текущее количество использования этого объекта. Как приложения могут получать это значение описаны в разделе [Многопоточность: прерывание потоков](../parallel/multithreading-terminating-threads.md).  
  
 Существуют некоторые ограничения на действия в многопоточных программах, написанным с использованием библиотеки MFC. Описание этих ограничений, а также другие советы по использованию потоков см. в разделе [Многопоточность: советы про программированию](../parallel/multithreading-programming-tips.md).  
  
##  <a name="_core_controlling_function_example"></a> Пример функции управления  
 В следующем примере показано, как определения функции управления и использовать его из другой части программы.  
  
```  
UINT MyThreadProc( LPVOID pParam )  
{  
    CMyObject* pObject = (CMyObject*)pParam;  
  
    if (pObject == NULL ||  
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))  
    return 1;   // if pObject is not valid  
  
    // do something with 'pObject'  
  
    return 0;   // thread completed successfully  
}  
  
// inside a different function in the program  
.  
.  
.  
pNewObject = new CMyObject;  
AfxBeginThread(MyThreadProc, pNewObject);  
.  
.  
.  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Многопоточность. Создание потоков пользовательского интерфейса](../parallel/multithreading-creating-user-interface-threads.md)  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C++ с помощью классов MFC](../parallel/multithreading-with-cpp-and-mfc.md)