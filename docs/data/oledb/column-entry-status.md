---
title: COLUMN_ENTRY_STATUS | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_STATUS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_STATUS macro
ms.assetid: 29ffe8b6-cb1e-438c-813e-2e6d73a5deef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 91be475992128d21a866d0ee86860e6bb12270da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="columnentrystatus"></a>COLUMN_ENTRY_STATUS
Представляет привязку в наборе строк для конкретного столбца в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочника программиста OLE DB*.  
  
 `nOrdinal`  
 [in] Номер столбца.  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
 *status*  
 [in] Переменная может быть привязано к состояние столбца.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос поддерживает *состояние* переменной. Он используется в следующих местах:  
  
-   Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
-   Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
-   Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)