---
title: Константы кучи | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25118792500d679d243f55e5d87e62a4994eaa0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="heap-constants"></a>Константы кучи
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Эти константы предоставляют возвращаемое значение, отображающее состояние кучи.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|Начальные сведения о заголовке не найдены или недопустимы.|  
|`_HEAPBADNODE`|Обнаружен недопустимый узел или куча повреждена.|  
|`_HEAPBADPTR`|Поле **_pentry** структуры **_HEAPINFO** не содержит допустимого указателя на кучу (только для подпрограммы `_heapwalk`).|  
|`_HEAPEMPTY`|Куча не инициализирована.|  
|`_HEAPEND`|Конец кучи успешно достигнут (только для подпрограммы `_heapwalk`).|  
|`_HEAPOK`|Куча согласована (только для подпрограмм `_heapset` и `_heapchk`). Пока без ошибок: структура **_HEAPINFO** содержит сведения о следующей записи (только для подпрограммы `_heapwalk`).|  
  
## <a name="see-also"></a>См. также  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)