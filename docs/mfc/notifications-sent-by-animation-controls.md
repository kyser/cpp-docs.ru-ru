---
title: Уведомления, отправленные элементами анимации | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1696389ce3dc40c5d02ec660ebaeb6bf3e6c3ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="notifications-sent-by-animation-controls"></a>Уведомления, отправленные элементами управления "Анимация"
Элемент управления анимации ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) отправляет два различных типа сообщений уведомления. Уведомления отправляются в виде [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений.  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) сообщение отправляется, когда элемент управления анимация начала проигрываться клип. [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) управления "анимация" завершения или остановки, воспроизведение отправляется сообщение.  
  
## <a name="see-also"></a>См. также  
 [Использование CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

