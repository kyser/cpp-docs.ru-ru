---
title: "Пошаговые руководства для среды выполнения с параллелизмом | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- walkthroughs [Concurrency Runtime]
- Concurrency Runtime, walkthroughs
ms.assetid: 7374c5e9-54eb-44bf-9ed9-5e190cfd290b
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9aaff86eb5781872675a46863ccfbafff60d24e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="concurrency-runtime-walkthroughs"></a>Пошаговые руководства по среде выполнения с параллелизмом
Разделы на базе сценария в этом разделе показано, как использовать многие функции среды выполнения с параллелизмом.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пошаговое руководство. Подключение с использованием задач и HTTP-запросов XML](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Показано, как использовать [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) и [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) интерфейсы вместе с задачами отправки запросов HTTP GET и POST веб-службу в [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] приложения.  
  
 [Пошаговое руководство. Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
 Описывает, как создать простое приложение на основе агентов.  
  
 [Пошаговое руководство. Создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)  
 Показано, как создавать приложения на основе агентов на основе потока данных, а не на потоке управления.  
  
 [Пошаговое руководство. Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)  
 Показано, как создавать сеть асинхронных блоков сообщений, выполняющих обработку изображений.  
  
 [Пошаговое руководство. Реализация фьючерсов](../../parallel/concrt/walkthrough-implementing-futures.md)  
 Показано, как асинхронно вычислять значения для последующего использования.  
  
 [Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)  
 Производит Проблема обедающих философов показано использование [concurrency::join](../../parallel/concrt/reference/join-class.md) для недопущения взаимоблокировок в приложении.  
  
 [Пошаговое руководство. Удаление задач из потока пользовательского интерфейса](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)  
 Показано, как повысить производительность приложения MFC, который рисует фрактал "Мандельброт".  
  
 [Пошаговое руководство. Использование среды выполнения с параллелизмом в приложениях с поддержкой модели COM](../../parallel/concrt/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)  
 Показано, как использовать среду выполнения с параллелизмом в приложении, которое использует компонент модели объектов (COM).  
  
 [Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)  
 Показано, как адаптировать имеющийся код, который использует Windows API для создания и выполнения потока, в котором используется упрощенная задача.  
  
 [Пошаговое руководство. Создание пользовательского блока сообщений](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)  
 Описывает создание настраиваемого блочного типа сообщений, сортирующий входящие сообщения по приоритету.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)  
 Вводит платформой параллельного программирования для Visual C++.
