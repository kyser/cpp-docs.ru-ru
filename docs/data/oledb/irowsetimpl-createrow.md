---
title: IRowsetImpl::CreateRow | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eae3fbdce1db5760d4ee5ca75e007c01e98b7bed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Вспомогательный метод, вызываемый [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) выделить новый **HROW**.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>Параметры  
 *lRowsOffset*  
 Позиция курсора создаваемой строки.  
  
 *cRowsObtained*  
 Ссылка передается обратно в пользователя, указывая число созданных строк.  
  
 *rgRows*  
 Массив **HROW**s возвращается вызывающему с дескрипторами только что созданной строки.  
  
## <a name="remarks"></a>Примечания  
 Если строка существует, этот метод вызывает метод [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и возвращает. В противном случае он выделяет новый экземпляр переменной шаблона RowClass и добавляет его в [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)