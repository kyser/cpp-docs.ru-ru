---
title: BEGIN_ACCESSOR_MAP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR_MAP macro
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e03e4aed105a488d646921fd458496d8d5a950f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="beginaccessormap"></a>BEGIN_ACCESSOR_MAP
Отмечает начало карты записей метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BEGIN_ACCESSOR_MAP(x, num)  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 [входные данные] Имя класса записей пользователя.  
  
 *num*  
 [входные данные] Число методов доступа в этой карте метода доступа.  
  
## <a name="remarks"></a>Примечания  
 Если в наборе строк имеется несколько методов доступа, необходимо указать `BEGIN_ACCESSOR_MAP` в начале и использовать макрос `BEGIN_ACCESSOR` для каждого отдельного метода доступа. Макрос `BEGIN_ACCESSOR` выполняется с помощью макроса `END_ACCESSOR` . Карта метода доступа выполняется с помощью макроса `END_ACCESSOR_MAP` .  
  
 Если в записи пользователя имеется только один метод доступа, используйте макрос [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).  
  
## <a name="example"></a>Пример  

 ```cpp  
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
 ```

  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)