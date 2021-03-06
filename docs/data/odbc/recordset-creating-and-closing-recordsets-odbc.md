---
title: 'Набор записей: Создание и закрытие наборов записей (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbf020e12151e666aa8f88098865b1624403b828
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Набор записей. Создание и закрытие наборов записей (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Чтобы воспользоваться набором записей, создайте объект набора записей, а затем вызвать его **откройте** Чтобы выполнить запрос набора записей и функция-член. После завершения работы с набора записей, закройте и удалите этот объект.  
  
 Содержание раздела:  
  
-   [Когда и как следует создавать объект набора записей](#_core_creating_recordsets_at_run_time).  
  
-   [Когда и как можно определять поведение набора записей путем его параметризации, фильтрации, сортировки или блокировки](#_core_setting_recordset_options).  
  
-   [Когда и как следует закрывать объект набора записей](#_core_closing_a_recordset).  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> Создание наборов записей во время выполнения  
 Перед созданием объекта набора записей в программе, обычно вы создаете классы набора записей для конкретного приложения. Дополнительные сведения об этом предварительном этапе см. в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Откройте динамический или статический объект, если нужно будет выбрать записи из источника данных. Тип создаваемого объекта зависит от того, вам нужно с данными в приложении и на какие драйвер ODBC поддерживает. Дополнительные сведения см. в разделе [динамический набор](../../data/odbc/dynaset.md) и [моментального снимка](../../data/odbc/snapshot.md).  
  
#### <a name="to-open-a-recordset"></a>Чтобы открыть набор записей  
  
1.  Создайте объект вашей `CRecordset`-производного класса.  
  
     Можно создать объект в куче или в кадре стека функции.  
  
2.  При необходимости измените поведение по умолчанию набор записей. Доступных параметрах см. в разделе [Настройка параметров набора записей](#_core_setting_recordset_options).  
  
3.  Вызвать объект [откройте](../../mfc/reference/crecordset-class.md#open) функции-члена.  
  
 В конструкторе передайте указатель `CDatabase` объекта или передать **NULL** использовать временный объект базы данных, платформа создает и открывает на основании строки подключения, возвращаемой [GetDefaultConnect ](../../mfc/reference/crecordset-class.md#getdefaultconnect) функции-члена. `CDatabase` Объект может быть уже подключены к источнику данных.  
  
 Вызов **откройте** SQL используется для выбора записей из источника данных. Первой записью (если есть) является текущей записи. Значения полей этой записи хранятся в члены данных полей объекта набора записей. Если были выбраны какие-либо записи, как `IsBOF` и `IsEOF` функции-члены возвращают 0.  
  
 В вашей [откройте](../../mfc/reference/crecordset-class.md#open) вызов, вы можете:  
  
-   Укажите, является ли набор записей динамический или статический. Наборы записей открываются как моментальные снимки по умолчанию. Или можно указать только вперед набора записей, что позволяет только перемещение вперед, одной записи за раз.  
  
     По умолчанию в наборе записей используется стандартный тип, хранящийся в `CRecordset` данные-член **m_nDefaultType**. Мастеры написать код для инициализации **m_nDefaultType** тип набора записей, выберите в мастере. Вместо того чтобы примите значения по умолчанию, можно заменить другой тип набора записей.  
  
-   Укажите строку, чтобы заменить значение по умолчанию SQL **ВЫБЕРИТЕ** инструкцию, которая создает набор записей.  
  
-   Укажите, является ли набор записей доступным только для чтения или только для присоединения. Наборы записей могут полностью обновляться по умолчанию, но можно ограничить, чтобы только добавление новых записей или запретить все обновления.  
  
 Приведенный ниже показано, как открыть только для чтения моментальный снимок объекта класса `CStudentSet`, относящихся к приложению класс:  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 После вызова метода **откройте**, использовать член функции и данные члены объекта для работы с записями. В некоторых случаях может потребоваться повторный запрос или обновление набора записей для включения изменений, произошедших в источнике данных. Дополнительные сведения см. в разделе [набор записей: выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).  
  
> [!TIP]
>  Строка подключения, которую можно использовать во время разработки, не может быть та же строка подключения, которая требуется вашим конечным пользователям. Идей, о обобщение приложения таким образом, в разделе [источника данных: управление подключениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).  
  
##  <a name="_core_setting_recordset_options"></a> Настройка параметров набора записей  
 После создания объекта набора записей, но перед вызовом **откройте** для выбора записей, может потребоваться настройка некоторых параметров, управляющих поведением набора записей. Для всех наборов записей можно сделать следующее.  
  
-   Укажите [фильтра](../../data/odbc/recordset-filtering-records-odbc.md) ограничить выбор записей.  
  
-   Укажите [сортировки](../../data/odbc/recordset-sorting-records-odbc.md) порядок записей.  
  
-   Укажите [параметры](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) для выбора записей с помощью данных, полученных или вычисленных во время выполнения.  
  
 Можно также задать следующий параметр, если условиям:  
  
-   Если набор записей является обновляемым и поддерживает параметры блокировки, укажите [блокировки](../../data/odbc/recordset-locking-records-odbc.md) метод, используемый для обновления.  
  
> [!NOTE]
>  Чтобы повлиять на выбор записей, необходимо настроить эти параметры перед вызовом метода **откройте** функции-члена.  
  
##  <a name="_core_closing_a_recordset"></a> Закрытие набора записей  
 После завершения работы с набором записей, необходимо удалить ее и освобождать память.  
  
#### <a name="to-close-a-recordset"></a>Закрытие набора записей  
  
1.  Вызовите его [закрыть](../../mfc/reference/crecordset-class.md#close) функции-члена.  
  
2.  Удаление объекта набора записей.  
  
     Если он был объявлен в кадре стека функции, объект будет удален автоматически, когда объект выходит за пределы области. В противном случае используйте **удалить** оператор.  
  
 **Закрыть** освобождает набора записей **HSTMT** обработки. Она не удаляет объекта C++.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)   
 [Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)