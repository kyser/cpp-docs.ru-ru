---
title: CRowset::ReleaseRows | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ReleaseRows
- CRowset::ReleaseRows
- ATL::CRowset<TAccessor>::ReleaseRows
- CRowset<TAccessor>.ReleaseRows
- CRowset.ReleaseRows
- ATL.CRowset.ReleaseRows
- ATL.CRowset<TAccessor>.ReleaseRows
- CRowset<TAccessor>::ReleaseRows
- ATL::CRowset::ReleaseRows
dev_langs:
- C++
helpviewer_keywords:
- ReleaseRows method
ms.assetid: fa7254f5-566f-4754-bdf7-d0874256926f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 606e5887d226c2ed9dae909bf04716efcb5de737
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetreleaserows"></a>CRowset::ReleaseRows
Вызовы [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) для освобождения дескриптора текущей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT ReleaseRows() throw();  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)