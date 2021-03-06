---
title: IDBSchemaRowsetImpl::CreateSchemaRowset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateSchemaRowset method
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 90a942fc92faf3066669b46fd825ad2eae393f43
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimplcreateschemarowset"></a>IDBSchemaRowsetImpl::CreateSchemaRowset
Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [входные данные] Внешний [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) при агрегировании; в противном случае — **NULL**.  
  
 `cRestrictions`  
 [входные данные] Число ограничений, применяемых к набору строк.  
  
 `rgRestrictions`  
 [входные данные] Массив `cRestrictions`**VARIANT**, применяемых к набору строк.  
  
 `riid`  
 [входные данные] Интерфейс [QueryInterface](../../atl/queryinterface.md) для выходного значения **IUnknown**.  
  
 `cPropertySets`  
 [входные данные] Число задаваемых наборов свойств.  
  
 `rgPropertySets`  
 [входные данные] Массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) , определяющих задаваемые свойства.  
  
 `ppRowset`  
 [выходные данные] Выходное значение **IUnknown** , запрошенное `riid`. **IUnknown** — это интерфейс объекта набора строк схемы.  
  
 `pSchemaRowset`  
 [выходные данные] Указатель на экземпляр класса набора строк схемы. Как правило, этот параметр не используется, но может применяться, если необходимо выполнить дополнительные действия в наборе строк схемы перед передачей его в COM-объект. Время жизни `pSchemaRowset` ограничено `ppRowset`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="remarks"></a>Примечания  
 Эта функция реализует универсальный создатель для всех типов наборов строк схемы. Как правило, пользователь не вызывает эту функцию. Ее вызывает реализация карты схемы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)