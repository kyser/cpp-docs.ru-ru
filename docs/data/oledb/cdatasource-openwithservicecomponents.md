---
title: CDataSource::OpenWithServiceComponents | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- OpenWithServiceComponents method
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 793f1fcb22ac0c57bc1cccb375a0be24b18116ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourceopenwithservicecomponents"></a>CDataSource::OpenWithServiceComponents
Открывает объект источника данных с помощью компонентов службы в oledb32.dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  


HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] **CLSID** поставщика данных.  
  
 `szProgID`  
 [входные данные] Идентификатор программы поставщика данных.  
  
 `pPropset`  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структур, содержащих свойства и значения, задаваемые. В разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) в *справочника программиста OLE DB* в Windows SDK. При инициализации объекта источника данных свойства должны принадлежать к группе свойств источника данных. Если одно свойство указано в `pPropset` более одного раза, используется значение, связанное с поставщиком. Если значение `ulPropSets` равно нулю, этот параметр не учитывается.  
  
 `ulPropSets`  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент. Если это значение равно нулю, поставщик не учитывает `pPropset`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB на [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataSource](../../data/oledb/cdatasource-class.md)