---
title: 'Затраченное время: Классы общего назначения | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff7ef11bb20124a05e2e85c408ce27de8f982546
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="elapsed-time-general-purpose-classes"></a>Затраченное время: Классы общего назначения
Ниже показано, как вычислить разницу между двумя `CTime` объектов и get `CTimeSpan` результат.  
  
#### <a name="to-calculate-elapsed-time"></a>Для вычисления истекшего времени  
  
1.  Используйте `CTime` и `CTimeSpan` объекты для вычисления истекшего времени, следующим образом:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     После вычисляется `elapsedTime`, можно использовать функции-члены `CTimeSpan` для извлечения компонентов значения затраченного времени.  
  
## <a name="see-also"></a>См. также  
 [Дата и время. Классы общего назначения](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

