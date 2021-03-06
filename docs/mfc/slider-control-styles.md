---
title: Стили элемента управления "ползунок" | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fa099e050bd460756ff9e2584d37f9e628293f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="slider-control-styles"></a>Стили элемента управления "Ползунок"
Элементы управления "ползунок" ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) может иметь вертикальной или горизонтальной ориентации. Они могут иметь делений шкалы на обеих сторонах обоих сторон или ни одного. Они также могут использоваться для указания диапазона последовательных значений. Эти свойства управляются с помощью стилей управления "ползунок", которые указываются при создании управления "ползунок".  
  
 `TBS_HORZ` И `TBS_VERT` стили определяет ориентацию элемента управления "ползунок". Если не указать ориентацию, элемент управления "ползунок" ориентирован горизонтально.  
  
 `TBS_AUTOTICKS` Стиль создает элемент управления "ползунок" с деление для каждого фрагмента в значения из заданного диапазона. Эти деления добавляются автоматически при вызове [SetRange](../mfc/reference/csliderctrl-class.md#setrange) функции-члена. Если вы не укажете `TBS_AUTOTICKS`, можно использовать функции-члены, такие как [SetTic](../mfc/reference/csliderctrl-class.md#settic) и [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), чтобы указать расположение делений. Чтобы создать элемент управления "ползунок", который не отображать деления, можно использовать `TBS_NOTICKS` стиля.  
  
 Можно отображать деления одного или обоих этих стороны элемента управления "ползунок". Для горизонтального ползунка элементов управления, можно указать `TBS_BOTTOM` или `TBS_TOP` стиль. Для вертикального ползунка элементов управления, можно указать `TBS_RIGHT` или `TBS_LEFT` стиль. (`TBS_BOTTOM` и `TBS_RIGHT` являются параметрами по умолчанию.) Деления с обеих сторон элемента управления "ползунок" в любой ориентации, укажите `TBS_BOTH` стиля.  
  
 Элемент управления "ползунок" можно отобразить диапазон выбора только в том случае, если указать `TBS_ENABLESELRANGE` стилей при его создании. Если элемент управления "ползунок" содержит этот стиль, деления с позициями начального и конечного диапазона выбора отображаются в виде треугольники (вместо вертикальной дефисы) и диапазон выбора будет выделен. Например Выбор диапазоны могут пригодиться при простое приложение планирования. Пользователь может выбрать диапазон делений, соответствующий часов в день, чтобы определить время запланированного собрания.  
  
 По умолчанию длина ползунок элемента управления "ползунок" изменяется при изменении выделения диапазона. Если для элемента управления "ползунок" **TBS_FIXEDLENGTH** стиля, длина ползунок не изменится даже в случае изменения выбранного диапазона. Элемент управления "ползунок", имеющий **TBS_NOTHUMB** стиль не включает ползунка.  
  
## <a name="see-also"></a>См. также  
 [Использование CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

