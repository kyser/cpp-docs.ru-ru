---
title: Регистрация классов окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WndProc
dev_langs:
- C++
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00e397f8880f6f42f1930e668b64d3ba62eb2c64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="registering-window-classes"></a>Регистрация классов Window
Окно «классы» в традиционном программировании для Windows определения характеристик «класс» (а не класс C++), из которого можно создать любое количество windows. Этот тип класса — это шаблон или модель для создания windows.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Регистрация класса Window в традиционных программ для Windows  
 В традиционной программы для Windows, без использования MFC, обрабатывать все сообщения в окно в его «процедуру окна» или «**WndProc**.» Объект **WndProc** связана с окном с помощью процесса «регистрация класса window». Зарегистрированный в главном окне `WinMain` функцию, но другие классы windows могут регистрироваться в любом месте в приложении. Регистрация зависит от структуры, которая содержит указатель на **WndProc** работать вместе с спецификации для курсора, кисть фона и т. д. Структуры передается как параметр, а также строковое имя класса, в предыдущем вызове **RegisterClass** функции. Таким образом класс регистрации может совместно использоваться несколькими окнами.  
  
## <a name="window-class-registration-in-mfc-programs"></a>Регистрация класса Window в приложениях MFC  
 Напротив большинство активность регистрации класса окна выполняется автоматически в программе MFC framework. При использовании MFC обычно производный класс окна C++ из существующего класса библиотеки с помощью обычного синтаксиса C++ для наследования классов. Платформа по-прежнему использует традиционный «регистрация классы» и предоставляет стандартные обработчики, зарегистрированные для вас, если это требуется. Регистрация классов можно зарегистрировать путем вызова [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальной функции и затем передачу зарегистрированный класс для **создать** функции-члена `CWnd`. Как описано здесь, традиционные «регистрация класса» в Windows является не следует путать с классом C++.  
  
 Дополнительные сведения см. в разделе [технические Примечание 1](../mfc/tn001-window-class-registration.md).  
  
## <a name="see-also"></a>См. также  
 [Создание окон](../mfc/creating-windows.md)

