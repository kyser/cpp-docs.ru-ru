---
title: Запишите представления (доступ к данным MFC) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 742866b2b11811ee37365ee6cc5e4d3aa881db91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="record-views--mfc-data-access"></a>Представления записей (доступ к данным MFC)
Этот раздел относится только к классам ODBC библиотеки MFC. Сведения о представлениях записей OLE DB см. в разделе [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) и [с помощью OLE DB для представлений записей](../data/oledb/using-ole-db-record-views.md).  
  
 Для поддержки приложений доступа к данным на основе форм, библиотека классов предоставляет классы [CRecordView](../mfc/reference/crecordview-class.md). Представление записей — это объект представления формы, элементы управления которого напрямую сопоставлены с элементами данных полей [записей](../data/odbc/recordset-odbc.md) объекта (и косвенно сопоставляются соответствующим столбцам в результате запроса или таблицы в источнике данных). Как его базовый класс [CFormView](../mfc/reference/cformview-class.md), `CRecordView` основан на ресурс шаблона диалоговых окон.  
  
## <a name="form-uses"></a>Использование форм  
 Формы полезны для различных задач доступа к данным:  
  
-   Ввод данных  
  
-   Выполнение анализа данных только для чтения  
  
-   Обновление данных  
  
## <a name="further-reading-about-record-views"></a>Дополнительные сведения о представлениях записей  
 Материалы в следующих разделах относятся к классам и на основе ODBC и на основе DAO . Использование `CRecordView` для ODBC и `CDaoRecordView` для DAO.  
  
 Ниже приведен список разделов.  
  
-   [Функции классов представлений записей](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [Обмен данными в представлениях записей](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [Роль пользователя в работе с представлением записи](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [Проектирование и создание представления записей](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)  
  
## <a name="see-also"></a>См. также  
 [Доступ к данным программирования (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)