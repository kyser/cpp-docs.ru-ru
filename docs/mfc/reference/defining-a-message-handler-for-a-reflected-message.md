---
title: Определение обработчика сообщений для отраженного сообщения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed941816824c77f14a3364b06af0b3da171ee8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Определение обработчика сообщений для отраженного сообщения
После создания нового класса элемента управления MFC для него можно определить обработчик сообщений. Обработчики отраженных сообщений позволяют классу элемента управления обрабатывать собственные сообщения, прежде чем сообщение в родительском. Можно использовать MFC [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) функции для отправки сообщений от элемента управления в родительское окно.  
  
 С помощью этой функции можно было бы, например, создать поле со списком, будет перерисовывает себя, а не полагаться на родительское окно, чтобы сделать (рисование владельцем). Дополнительные сведения об отраженных сообщениях см. в разделе [обработки сообщений отражены](../../mfc/handling-reflected-messages.md).  
  
 Для создания [элемента управления ActiveX](../../mfc/activex-controls-on-the-internet.md) с такой же функциональностью, необходимо создать проект для элемента управления ActiveX.  
  
> [!NOTE]
>  Не удается добавить отраженное сообщение (OCM_*сообщение*) для ActiveX элемента управления с помощью окна свойств, как описано ниже. Необходимо вручную добавить эти сообщения.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Определение обработчика сообщений для отраженного сообщения в окне «Свойства»  
  
1.  Добавьте элемент управления, такой как список, элемент управления главной панели, панели инструментов или дерево, в проект MFC.  
  
2.  В представлении классов щелкните имя класса элемента управления.  
  
3.  В [окно свойств](/visualstudio/ide/reference/properties-window), отображается имя класса элемента управления в **имя класса** списка.  
  
4.  Нажмите кнопку **сообщений** кнопку, чтобы отобразить список сообщений Windows, можно добавить к элементу управления.  
  
5.  Прокрутите вниз список сообщений в окне «Свойства», пока не появится заголовок **отражен**. Щелкнуть **категории** кнопку и свернуть окно, чтобы увидеть **отражен** заголовок.  
  
6.  Выберите отраженное сообщение, для которого требуется определить обработчик. Отраженные сообщения помечаются со знака равенства (=).  
  
7.  Щелкните ячейку в столбце справа в окне «Свойства», чтобы отобразить предлагаемое имя обработчика как \<Добавить >*HandlerName*. (Например, **= WM_CTLCOLOR** обработчик сообщений предлагает \<Добавить >**CtlColor**).  
  
8.  Щелкните предлагаемое имя для приема. Обработчик добавляется в проект.  
  
     В правом столбце окна отраженных сообщений отображаются имена обработчиков сообщения, которые были добавлены.  
  
9. Чтобы изменить или удалить обработчик сообщений, повторите шаги с 4 по 7. Щелкните ячейку, содержащую имя обработчика, чтобы изменить или удалить и выберите соответствующую задачу.  
  
## <a name="see-also"></a>См. также  
 [Сопоставление сообщений с функциями](../../mfc/reference/mapping-messages-to-functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
