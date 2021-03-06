---
title: 'Источник данных: Определение схемы источника данных (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6da4067766eddab40bac75ee73d825dc5886dd0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Источник данных. Определение схемы источника данных (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Чтобы задать элементы данных в вашей `CRecordset` объектов, необходимо знать схему источника данных, к которому вы подключаетесь. Определение схемы источника данных предполагает получение списка таблиц в источнике данных, список столбцов в каждой таблице, тип данных каждого столбца и наличия индексов.  
  
## <a name="see-also"></a>См. также  
 [Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)