---
title: Предоставление активации без мерцания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9d9c0108ce4afd2e65678280248488181ad34f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="providing-flicker-free-activation"></a>Предоставление активации без мерцания
Если элемент управления рисовании одинаково в активным и неактивным состоянием (и не использует активации без окна), можно исключить операции рисования и сопутствующее видимое мерцание, которое обычно случается при переходе между неактивные и активные состояния. Чтобы сделать это, включите **noFlickerActivate** флаг в набор флагов, возвращенных [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 Код, чтобы включить этот флаг создается автоматически при выборе **активации без мерцания** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы при создании элемента управления с помощью мастера элементов управления ActiveX MFC.  
  
 При использовании активации без окна Данная оптимизация не оказывает влияния.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

