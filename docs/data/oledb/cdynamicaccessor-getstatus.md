---
title: CDynamicAccessor::GetStatus | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 98e120e19c6115b98ed57bc8d25a934b84573386
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetstatus"></a>CDynamicAccessor::GetStatus
Получает состояние указанного столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```
bool GetStatus(DBORDINAL nColumn,   
  DBSTATUS* pStatus) const throw();  

bool GetStatus(const CHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  

bool GetStatus(const WCHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nColumn`  
 [in] Номер столбца. Номера столбцов начинается с 1. Значение 0 ссылается на столбец закладки в том случае, если таковые имеются.  
  
 `pColumnName`  
 [in] Указатель на символьную строку, содержащую имя столбца.  
  
 `pStatus`  
 [out] Указатель на переменную, содержащую состояние столбца. В разделе [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) в *Справочник программиста OLE DB* для получения дополнительной информации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при обнаружении указанного столбца. В противном случае эта функция возвращает **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)