---
title: Определение хранимых процедур | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e03a5ae2e7c75d905216a6be92630376484d047
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="defining-stored-procedures"></a>Определение хранимых процедур
Перед вызовом хранимой процедуры, необходимо сначала определить, с помощью [DEFINE_COMMAND](../../data/oledb/define-command.md) макрос. После определения команды обозначьте параметры вопросительным знаком (?) как маркер параметров:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Обратите внимание, что синтаксис (Использование фигурных скобок и т. д) используется в примерах кода в этом разделе, связанные с SQL Server. Синтаксиса, который можно использовать в хранимых процедурах может различаться в зависимости от используемого поставщика.  
  
 Затем в сопоставлении параметров укажите параметры, которые можно использовать в команде, со списком параметров, в том порядке, в котором они расположены в команде:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Предыдущий пример определяет хранимой процедуры, поскольку он выполняется. Как правило для эффективного повторного использования кода, база данных содержит набор стандартные хранимые процедуры с именами, например «Продажи по годам» или «dt_adduserobject». Вы можете просматривать их определения с помощью SQL Server Enterprise Manager. Можно вызвать следующим образом (размещение '?' параметров зависит от интерфейса хранимых процедур):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Объявите класс команд:  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 Наконец, вызовите хранимую процедуру `OpenRowset` следующим образом:  
  
```  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 Также Обратите внимание, что хранимая процедура, с помощью атрибутов базы данных можно определить [db_command](../../windows/db-command.md) следующим образом:  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>См. также  
 [Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)