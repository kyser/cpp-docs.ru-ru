---
title: Мастер обработчиков событий | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 544ce4cd0f4ed9a7f3592e5ec1691fb3734b8772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="event-handler-wizard"></a>Мастер обработчиков событий
Этот мастер добавляет обработчик событий для элемента управления диалогового окна поле класса по своему усмотрению. При добавлении обработчика событий из [окно свойств](/visualstudio/ide/reference/properties-window), его можно добавить только в класс, реализующий диалоговое окно. В разделе [Добавление обработчиков событий для элементов управления диалоговых](../windows/adding-event-handlers-for-dialog-box-controls.md) для получения дополнительной информации.  
  
 **Имя команды**  
 Определяет выбранный элемент управления, для которого добавляется обработчик события. Этот флажок недоступен.  
  
 **Тип сообщения**  
 Отображает список возможных обработчиков сообщений для выбранного элемента управления.  
  
 **Имя функции обработчика**  
 Отображает имя функции, которая добавляется для обработки события. По умолчанию имя основано на тип сообщения и команды, присоединяется с «On». Например, для кнопки с именем `IDC_BUTTON1`, тип сообщения `BN_CLICKED` отображает имя функции обработчика `OnBnClickedButton1`.  
  
 **Список классов**  
 Отображает доступные классы, к которым можно добавить обработчик событий. Класс для выбранного диалогового окна отображается красным цветом.  
  
 **Описание обработчика**  
 Содержит описание для элемента, выбранного в **тип сообщений** поле. Этот флажок недоступен.  
  
 **Добавление и изменение**  
 Добавляет обработчик сообщений в выбранный класс или объект, а затем открывается текстовый редактор, чтобы новая функция, поэтому можно добавить код обработчика уведомлений элемента управления.  
  
 **Изменение кода**  
 Открывает для выбранной существующей функции текстовый редактор, можно добавить или изменить код обработчика уведомлений элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Добавление обработчика событий](../ide/adding-an-event-handler-visual-cpp.md)