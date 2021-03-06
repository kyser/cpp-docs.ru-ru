---
title: Сопоставление сообщений с функциями | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3388cd8e9a52ef9aacb427d66b027d793b08ca75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mapping-messages-to-functions"></a>Сопоставление сообщений с функциями
Окно свойств позволяет привязать обработчики сообщений (функции-члены классов MFC пользовательского интерфейса) сообщения, созданные ресурсы приложения. Они используют [схемы сообщений MFC](../../mfc/messages-and-commands-in-the-framework.md) для создания привязки.  
  
 При использовании представления классов для создания нового класса, производного от одного из классов framework, она автоматически помещается в полные и рабочие класс заголовков (h) и реализации (CPP) файлы, указанные.  
  
> [!NOTE]
>  Чтобы добавить новый класс, который не обрабатывает сообщения, создайте класс непосредственно в текстовом редакторе.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Определение или удаление обработчика сообщений в окне «Свойства»  
  
1.  В представлении классов щелкните требуемый класс.  
  
2.  В окне «Свойства» щелкните **сообщений** кнопки.  
  
    > [!NOTE]
    >  **Сообщений** кнопка доступна при выборе имени класса в представлении классов или при нажатии кнопки в окне исходного кода.  
  
     Если проект содержит обработчик для сообщения, имя обработчика появляется в правом столбце рядом с сообщением.  
  
3.  Если сообщение не имеет обработчика, затем щелкните ячейку в правом столбце в окне «Свойства», чтобы отобразить предлагаемое имя обработчика как \<Добавить >*HandlerName*. (Например, `WM_TIMER` обработчик сообщений предлагает \<Добавить >`OnTimer`).  
  
4.  Щелкните предлагаемое имя, чтобы добавить код заглушки для функции.  
  
5.  Чтобы изменить обработчик сообщения, дважды щелкните сообщение в представлении классов и редактировать код в окне исходного кода.  
  
 Чтобы удалить обработчик сообщений, дважды щелкните обработчик в правом столбце и выберите \<удалить >*HandlerName*. Код функции комментарий.  
  
## <a name="see-also"></a>См. также  
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Добавление обработчиков событий для элементов управления диалогового окна](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
