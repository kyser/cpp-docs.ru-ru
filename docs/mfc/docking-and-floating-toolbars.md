---
title: Закрепленные и плавающие панели инструментов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
dev_langs:
- C++
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 430af2344888696e3cbf053677ef59c7249b50bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="docking-and-floating-toolbars"></a>Закрепленные и плавающие панели инструментов
Библиотеки классов Microsoft Foundation поддерживает закрепляемых панелей инструментов. Закрепляемая панель инструментов можно подключить или закрепить, с любой стороны родительского окна, или он может быть отсоединена или перемещается в отдельном окне области. В этой статье описывается использование закрепляемых панелей инструментов в ваших приложениях.  
  
 При использовании мастера приложений для создания схемы приложения вам будет предложено выбрать, следует ли закрепляемых панелей инструментов. По умолчанию мастер приложения создает код, который выполняет три действия, необходимые для размещения закрепляемой панели инструментов в приложении:  
  
-   [Включение закрепления в окне фрейма](#_core_enabling_docking_in_a_frame_window).  
  
-   [Включение закрепления для панели инструментов](#_core_enabling_docking_for_a_toolbar).  
  
-   [Закрепить панель инструментов (фрейм окна)](#_core_docking_the_toolbar).  
  
 Если отсутствует один из следующих действий в приложении будет выводиться Стандартная панель инструментов. Последние два этапа необходимо выполнить для каждой закрепляемой панели инструментов в приложении.  
  
 Другие разделы, описанные в данной статье:  
  
-   [Число с плавающей панели инструментов](#_core_floating_the_toolbar)  
  
-   [Динамическое изменение размера панели инструментов](#_core_dynamically_resizing_the_toolbar)  
  
-   [Параметр wrap позиций для панели инструментов-style](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)  
  
 См. в образце MFC Общие [DOCKTOOL ПОКАЗАНА](../visual-cpp-samples.md) примеры.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> Включение закрепления в окне фрейма  
 Окна фрейма (или назначения) необходимо включить для закрепления панели инструментов область окна, чтобы разрешить соединение. Это делается с помощью [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) функции, которая принимает один `DWORD` параметр, который представляет собой набор стилей bits, указывающее, какой стороне фрейма окна поддерживает закрепление. Если панель инструментов собирается закрепляться и существует несколько сторон, ее можно закрепить, сторон в параметр, передаваемый `EnableDocking` используются в следующем порядке: сверху, снизу, слева, справа. Если вы хотите закрепить управления панелей в любом месте, передайте `CBRS_ALIGN_ANY` для `EnableDocking`.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> Включение закрепления для панели инструментов  
 После подготовки назначения закрепления таким же образом, необходимо подготовить панель инструментов (или исходного кода). Вызовите [CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) для каждой требуется закрепить панели инструментов задания целевой стороны для которого следует закрепления панели инструментов. Если ни одна из сторон, указанный в вызове `CControlBar::EnableDocking` соответствуют сторон включено закрепление фрейм окна, нельзя закрепить панель инструментов — он будет число с плавающей запятой. Как только он перемещается, он остается перемещаемой панелью инструментов, невозможно закрепить окно фрейма.  
  
 Если требуется действует постоянно плавающую панель инструментов, вызовите `EnableDocking` с параметром 0. Затем вызовите [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar). Панели инструментов остается с плавающей запятой, без возможности восстановления не удается закрепить в любом месте.  
  
##  <a name="_core_docking_the_toolbar"></a> Закрепление панели инструментов  
 Платформа вызывает [CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) при попытке пользователя удалить на стороне окна фрейма, позволяющий закрепления панели инструментов.  
  
 Кроме того эту функцию можно вызвать в любое время для закрепления панели элементов управления в фрейме окна. Обычно это делается во время инициализации. Существует несколько инструментов можно прикреплять к определенной части окна фрейма.  
  
##  <a name="_core_floating_the_toolbar"></a> Число с плавающей панели инструментов  
 Отсоединение Закрепляемая панель инструментов в окне фрейма, называется плавающей панели инструментов. Вызовите [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) это сделать. Укажите, панели инструментов, чтобы быть перемещается, точки, где он должен быть помещен и выравнивание стиль, который определяет, является ли перемещаемой панелью инструментов горизонтальная или вертикальная.  
  
 Платформа вызывает эту функцию, когда пользователь перетаскивает off его закрепленное расположение панели инструментов и сбрасывает его в расположении, где закрепление не включена. Это может быть в любом месте внутри или за пределами окна фрейма. Как и в `DockControlBar`, можно также вызвать эту функцию во время инициализации.  
  
 Реализация MFC закрепляемых панелей инструментов не предоставляет некоторые расширенные возможности, имеющиеся в некоторых приложениях, поддерживающих закрепляемых панелей инструментов. Функции, такие как настраиваемые панели инструментов не предоставляются.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> Динамическое изменение размера панели инструментов  
 Начиная с Visual C++ версии 4.0 вы можете позволяют для пользователей приложения динамического изменения размера перемещаемых панелей инструментов. Как правило панель инструментов имеет форму long, линейный, отображаемых по горизонтали. Однако вы можете изменить ориентацию панели инструментов и его форму. Например когда пользователь закрепляет инструментов для одного вертикальной границы окна фрейма, фигуры изменяет вертикальный макет. Можно также изменить в прямоугольник с множеством строк для кнопок панели инструментов.  
  
 Можно выполнить следующие действия.  
  
-   Укажите динамического изменения размера как характеристики панели инструментов.  
  
-   Укажите в качестве характеристика инструментов фиксированного размера.  
  
 Для поддержки этого существует два новых стилей панели инструментов для использования в вызовах с [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) функции-члена. Они приведены ниже.  
  
-   **CBRS_SIZE_DYNAMIC** панели элементов управления является динамическим.  
  
-   **CBRS_SIZE_FIXED** фиксированной панель элементов управления.  
  
 Стиль динамического размер позволяет пользователю изменять размер панели инструментов, пока он открывается как плавающее окно, но не при его закреплены. Панели инструментов создает «оболочку» там, где требуется форма изменяется, когда пользователь перетаскивает его краями.  
  
 Размер фиксированной стиля сохраняет переноса состояния панели инструментов, исправления положение кнопки в каждом столбце. Пользователь приложения не может изменить фигуру на панели инструментов. Создает оболочку для панели инструментов в указанный местах, например расположения разделителей между кнопками. Это обеспечивает эта фигура ли панели инструментов, закрепленной или с плавающей запятой. Результатом является предопределенной палитры с несколькими столбцами кнопок.  
  
 Можно также использовать [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) для возврата состояния и стиль для кнопок на панели инструментов. Определяет стиль кнопки, как кнопка появляется, и как он реагирует на ввод данных пользователем; состояние указывает, является ли кнопка в свернутом состоянии.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> Параметр Wrap позиций для панели инструментов-Style  
 Панель инструментов с размером фиксированной стиля можно назначить панели инструментов кнопку индексы, в которых будет служить оболочкой панели инструментов. Следующий код показывает, как это сделать в окне главного фрейма `OnCreate` переопределения:  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]  
  
 Пример MFC Общие [DOCKTOOL ПОКАЗАНА](../visual-cpp-samples.md) показано использование функции-члены классов [CControlBar](../mfc/reference/ccontrolbar-class.md) и [CToolBar](../mfc/reference/ctoolbar-class.md) для управления динамический макет панели инструментов. См. в файле EDITBAR. CPP в DOCKTOOL ПОКАЗАНА.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Принципы работы инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)  
  
-   [Использование старых панелей инструментов](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>См. также  
 [Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)

