---
title: Клиенты автоматизации | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52eaae8074b984da32e115e779724fa86602b8f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="automation-clients"></a>клиентами автоматизации
Автоматизация позволяет приложения для работы с объектами, реализованными в другом приложении или получить доступ к объектам, поэтому ими можно управлять. Клиента автоматизации — это приложение, можно управлять раскрытых объектов, принадлежащих другим приложением. Приложение, которое предоставляет доступ к объектам называется сервера автоматизации. Клиент управляет объектами сервера приложений с доступа к свойствам этих объектов и функций.  
  
### <a name="types-of-automation-clients"></a>Типы клиентов автоматизации  
 Существует два типа клиентов автоматизации.  
  
-   Клиенты, которые динамически (во время выполнения), получить сведения о свойствах и операций сервера.  
  
-   Клиенты, которые имеются статические данные (предоставляется во время компиляции), указывающая свойства и операции сервера.  
  
 Клиенты первого типа получить сведения о методах и свойствах сервера с помощью запроса к системе OLE `IDispatch` механизм. Несмотря на то, что оно достаточно для динамического клиентов `IDispatch` трудно использовать для статических клиентов, где объектов, управляется должно быть известно во время компиляции. Для клиентов, привязанного к статическим, Microsoft Foundation classes предоставляют [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) класса.  
  
 Статические привязанного клиенты используют прокси-класса, которое статически связано с клиентским приложением. Этот класс предоставляет типобезопасный C++ инкапсуляция свойства и операции серверного приложения.  
  
 Класс `COleDispatchDriver` обеспечивает основной поддержку на стороне клиента автоматизации. С помощью `Add New Item` диалоговое окно, создайте класс, производный от `COleDispatchDriver`.  
  
 Укажите файл библиотеки типов, описывающая свойства и функции объекта приложения на сервере. В диалоговом окне Добавление элемента читает этот файл и создает `COleDispatchDriver`-производного класса с функциями-членами, приложение может вызвать для доступа к объектам серверного приложения в C++ в строго типизированным образом. Дополнительные функциональные возможности наследуется от `COleDispatchDriver` упрощает процесс вызова на соответствующий сервер автоматизации.  
  
### <a name="handling-events-in-automation-clients"></a>Обработка событий в клиентах автоматизации  
 Если вы хотите обрабатывать события в клиентском приложении автоматизации, необходимо добавить интерфейс приемника. MFC поддерживает мастер добавления приемника интерфейсов для элементов управления ActiveX, но не поддерживает для других серверов COM. Сведения о том, как добавить интерфейс приемника в клиентском приложении MFC для интерфейсов источника, описываемого COM-серверов см. в разделе Практическое руководство: Создание интерфейса приемника в клиент COM MFC-Based (181845 КБ) в [ http://support.microsoft.com/default.aspxscid=kb; en-us; 181845](http://support.microsoft.com/default.aspxscid=kb;en-us;181845).  
  
## <a name="see-also"></a>См. также  
 [Клиенты автоматизации: Использование библиотек типов](../mfc/automation-clients-using-type-libraries.md)   
 [Автоматизация](../mfc/automation.md)   
 [Мастер приложений MFC](../mfc/reference/mfc-application-wizard.md)

