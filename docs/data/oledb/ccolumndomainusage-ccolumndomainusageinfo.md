---
title: CColumnDomainUsage, CColumnDomainUsageInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_szCatalog
- m_nColumnPropID
- CColumnDomainUsageInfo
- COLUMN_GUID
- DOMAIN_NAME
- m_szColumnName
- DOMAIN_SCHEMA
- DOMAIN_CATALOG
- m_szTableCatalog
- m_szSchema
- COLUMN_PROPID
- m_guidColumn
- CColumnDomainUsage
- m_szTableName
- m_szName
- COLUMN_DOMAIN_USAGE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szSchema
- DOMAIN_NAME
- DOMAIN_SCHEMA
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- m_nColumnPropID
- CColumnDomainUsageInfo parameter class
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szName
- m_szTableCatalog
- m_szTableName
- COLUMN_DOMAIN_USAGE
- COLUMN_GUID
- CColumnDomainUsage typedef class
- m_guidColumn
- DOMAIN_CATALOG
ms.assetid: 5ff331f1-b99c-4002-9e04-367708c5759f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0ca95cadf5ac3502ba8de034fad91a75ba123f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ccolumndomainusage-ccolumndomainusageinfo"></a>CColumnDomainUsage, CColumnDomainUsageInfo
Вызовите typedef-класс **CColumnDomainUsage** реализации класса своего параметра **CColumnDomainUsageInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс определяет столбцы, определенные в каталоге, зависящие от домена определены в каталоге и принадлежащие данному пользователю.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [строк COLUMN_DOMAIN_USAGE](https://msdn.microsoft.com/en-us/library/ms711240.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|DOMAIN_CATALOG|  
|m_szSchema|DOMAIN_SCHEMA|  
|m_szName|DOMAIN_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)