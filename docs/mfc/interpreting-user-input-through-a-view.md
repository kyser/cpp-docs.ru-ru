---
title: Интерпретация ввода пользователя через представление | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3ade658046ad789a92bce044d12e5a6e76f7ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="interpreting-user-input-through-a-view"></a>Интерпретация ввода пользователя через представление
Другие функции-члены представления, обрабатывать и интерпретировать данные, вводимые пользователями. Функции-члены обработчика сообщений обычно определяются в классе представления для обработки:  
  
-   Windows [сообщений](../mfc/messages.md) созданные действия мыши и клавиатуры.  
  
-   [Команды](../mfc/user-interface-objects-and-command-ids.md) из меню, кнопки панели инструментов и сочетания клавиш.  
  
 Эти функции-члены обработчика сообщений интерпретировать следующих действий как входные данные, выбора или редактирования, включая перемещение данных в и из буфера обмена.  
  
-   Движения мыши щелчков, перетаскивает и дважды щелкает  
  
-   Нажатия клавиш  
  
-   Команды меню  
  
 Какие сообщения Windows дескрипторам представление зависит от потребностей вашего приложения.  
  
 [Обработка и сопоставление разделы сообщений](../mfc/message-handling-and-mapping.md) описывается назначение пункты меню и других объектов пользовательского интерфейса для команд и привязка команд к функции обработчика. [Обработка и сопоставление разделы сообщений](../mfc/message-handling-and-mapping.md) также объясняется, как MFC перенаправляет команды и отправляет стандартные сообщения Windows для объектов, которые содержат обработчики для них.  
  
 Например приложение может потребоваться реализовать прямой мыши рисование в представлении. Пример Scribble демонстрируется обработка `WM_LBUTTONDOWN`, `WM_MOUSEMOVE`, и `WM_LBUTTONUP` сообщений, соответственно, чтобы начать, продолжить и завершить рисование сегмента линии. С другой стороны иногда может потребоваться интерпретировать щелчка кнопкой мыши в представлении как выделенной области. В представлении `OnLButtonDown` функция обработчика определит рисования или при выборе пользователя. Если при выборе, обработчик следует определить, успешно ли щелкните в пределах границ какой-либо объект в представлении и, в этом случае alter отображать как выделенный объект.  
  
 Представление также может обрабатывать некоторые команды, например те, в меню "Правка", чтобы вырезать, копировать, вставить или удалить выбранные данные через буфер обмена. Такой обработчик будет вызывать некоторые связанные буфер обмена элемента функции класса `CWnd` для перемещения выбранного элемента данных или из буфера обмена.  
  
## <a name="see-also"></a>См. также  
 [Использование представлений](../mfc/using-views.md)

