---
title: CAccessorBase::GetHAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2bacc7f24d112fc6714200c6347e66bb66866831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Извлекает дескриптор метода доступа, указанного метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Номер нуля смещение для метода доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метода доступа.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CAccessorBase](../../data/oledb/caccessorbase-class.md)