---
title: 'Набор записей: Порядок обновления записей в наборе записей (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b16faf4c5ef0208c946cff123ecbe62b513e65ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Набор записей. Порядок обновления записей в наборе (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Помимо функции выбора записей из источника данных наборы записей можно (необязательно) обновления или удаления выбранных записей и добавлять новые записи. Три фактора определяют набора записей к обновлению: подключенного источника данных обновляется, указанных при создании объекта набора записей и SQL, который создается параметров.  
  
> [!NOTE]
>  SQL, на котором вашей `CRecordset` основан объект может повлиять на возможность обновления набора записей. Например если SQL имеет соединение или **GROUP BY** предложение, библиотека MFC устанавливает функцию обновления в **FALSE**.  
  
> [!NOTE]
>  Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовая выборка не был реализован. Если используется выборка строк, см. раздел [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Содержание раздела:  
  
-   [Роль пользователя в обновлении набора записей](#_core_your_role_in_recordset_updating) и что платформа делает за вас.  
  
-   [Набор записей в качестве буфера редактирования](#_core_the_edit_buffer) и [различия между подмножества и моментальные снимки](#_core_dynasets_and_snapshots).  
  
 [Набор записей: Как AddNew, Edit и Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) описывает действия этих функций с точки зрения набора записей.  
  
 [Набор записей: Дополнительные сведения об обновлении (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) завершает рассказ влияние транзакций на обновления, влияние закрытия набора записей или прокрутки выполняется обновление и взаимодействие с обновлениями для других обновлений пользователи.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> Роль пользователя в обновлении набора записей  
 В следующей таблице показаны роли с помощью наборы записей, чтобы добавить, изменить или удалить записи, а также платформа делает за вас.  
  
### <a name="recordset-updating-you-and-the-framework"></a>Обновление набора записей: Вы и платформы  
  
|Вы|Платформа|  
|---------|-------------------|  
|Определите, является ли источник данных возможно обновление (или добавление).|Предоставляет [CDatabase](../../mfc/reference/cdatabase-class.md) функции-члены для тестирования обновлению или к присоединению источника данных.|  
|Откройте обновляемого набора записей (любого типа).||  
|Определить, является ли набор записей обновляемым путем вызова `CRecordset` обновления функций, таких как `CanUpdate` или `CanAppend`.||  
|Вызов функции-члены для добавления, изменения и удаления записей набор записей.|Управляет механизмом обмена данными между объекта набора записей и источником данных.|  
|При необходимости используйте транзакции для управления процессом обновления.|Предоставляет `CDatabase` функции-члены для поддержки транзакций.|  
  
 Дополнительные сведения о транзакциях см. в разделе [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a> В буфере  
 Взятые все вместе, члены данных полей в наборе записей служат в качестве буфера изменений, содержит одну запись — текущая запись. Операции обновления используют этот буфер для работы с текущей записи.  
  
-   При добавлении записи в буфере используется для создания новой записи. После завершения добавления записи, запись, которая была текущей снова становится текущей.  
  
-   При обновлении буфера (изменения) записи, редактирования используется для задания поля элементов данных набора записей для новых значений. После завершения обновления, обновленная запись устарели.  
  
 При вызове [AddNew](../../mfc/reference/crecordset-class.md#addnew) или [изменить](../../mfc/reference/crecordset-class.md#edit), текущий запись сохраняется для дальнейшего восстановления. При вызове [удалить](../../mfc/reference/crecordset-class.md#delete), текущая запись не сохраняется, но помечаются как удаленные, и необходимо перейти к другой записи.  
  
> [!NOTE]
>  В буфере не играет никакой роли в процессе удаления записи. При удалении текущей записи, запись помечается как удаленная и recordset является «не в записи» пока прокрутки к другой записи.  
  
##  <a name="_core_dynasets_and_snapshots"></a> Подмножества и моментальные снимки  
 [Динамические наборы](../../data/odbc/dynaset.md) обновляют содержимое записей, при переходе к записи. [Моментальные снимки](../../data/odbc/snapshot.md) являются статическими представлениями записей, поэтому содержание записи обновляется только при вызове [Requery](../../mfc/reference/crecordset-class.md#requery). Чтобы использовать все функции динамических подмножеств данных, необходимо работать с помощью драйвера ODBC, который соответствует требуемому уровню поддержки ODBC API. Дополнительные сведения см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [динамический набор](../../data/odbc/dynaset.md).  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Наборы записей. Принципы работы функций AddNew, Edit и Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)