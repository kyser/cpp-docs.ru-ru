---
title: 'TN055: Перенос приложений баз данных MFC ODBC на классы MFC DAO | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], migration
- TN055
- migration [MFC], ODBC database applications
- ODBC classes [MFC], DAO classes
- migrating ODBC database applications [MFC]
- porting database applications to DAO
- ODBC [MFC], DAO
- porting ODBC database applications to DAO
- migrating database applications [MFC]
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa9c7870492fed78e65c3ac25f74726acf35b7eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055. Перенос приложений, использующих классы базы данных MFC ODBC, на классы MFC DAO
> [!NOTE]
>  Среда Visual C++ и мастера не поддерживают DAO (хотя классы DAO включены и их можно по-прежнему использовать). Корпорация Майкрософт рекомендует использовать [шаблонов OLE DB](../data/oledb/ole-db-templates.md) или [ODBC и MFC](../data/odbc/odbc-and-mfc.md) для новых проектов. DAO следует использовать только для поддержки существующих приложений.  
  
 **Обзор набора средств Visual Studio для Unity**  
  
 Во многих случаях может потребоваться миграция приложений, использующих классы базы данных MFC ODBC для классов баз данных MFC DAO. Это техническое Примечание подробно рассматриваются основные различия между классами MFC ODBC и DAO. С этими отличиями, помните не следует слишком сложным перенос приложений из классов ODBC классы MFC, при необходимости.  
  
 **Почему необходимо выполнить миграцию из ODBC в DAO**  
  
 Существует ряд причин, почему может потребоваться переносить приложения от классов базы данных ODBC в DAO классы баз данных, но такое решение не обязательно простое или очевидным. Следует помнить, что базы данных Microsoft Jet, используемый DAO можно считывается любой источник данных ODBC, для которой имеется драйвер ODBC. Возможно, более рационально использовать классы баз данных ODBC или вызывать ODBC напрямую самостоятельно, но базы данных Microsoft Jet может читать данные с ODBC.  
  
 Иногда простой, упрощает решение ODBC и DAO. Для экземпляра, когда требуется только доступ к данным в формате, который может считывать ядра Microsoft Jet напрямую (формат доступа, формат Excel и т. д) очевидным решением будет использовать классы баз данных DAO.  
  
 Более сложные случаи возникают, когда данные существует на сервере или на разных серверах различных. В этом случае решение использовать классы баз данных ODBC и классы баз данных DAO является трудной. Если вы хотите выполнить такие операции, как гетерогенные соединения (join данные с серверов в различных форматах, таких как SQL Server и Oracle), а затем базы данных Microsoft Jet выполняется объединение для вас, а не приходилось выполнять действия, необходимые при использовании базы данных ODBC Классы или напрямую вызван ODBC. Если вы используете драйвер ODBC, который поддерживает драйвер курсоры, оптимальным решением может быть классы баз данных ODBC.  
  
 Выбор может быть сложной, поэтому вы можете написать пример кода для тестирования производительности различных методов, учитывая свои задачи. Это техническое Примечание предполагается внесенные решение для миграции из базы данных классов ODBC классы баз данных DAO.  
  
 **Сходство классы баз данных ODBC и классы баз данных MFC DAO**  
  
 Классы MFC ODBC исходной структуры был основан на модели объектов DAO, которая была используется в Microsoft Access и Microsoft Visual Basic. Это означает, что существует множество общих функций ODBC и DAO MFC классов, которые не все отображаются в этом разделе. Как правило модели программирования одинаковы.  
  
 Чтобы выделить несколько сходства:  
  
-   Классы DAO и ODBC имеют объекты базы данных, управляемых с помощью базового система управления базами данных (СУБД).  
  
-   Оба имеют представления набора результатов, возвращенных из этого СУБД объекта набора записей.  
  
-   Объекты базы данных и набора записей DAO иметь члены почти идентична классы ODBC.  
  
-   С оба набора классов код для получения данных идентична за исключением изменения имени некоторые объекты и элементы. Изменения необходимо, но обычно выполняется изменение имени простой при переходе из классов ODBC в DAO-классы.  
  
 Например в обеих моделях, которые выполняет хранимая процедура для получения данных для создания и открытия объекта базы данных, создайте и откройте объекта набора записей и перемещаться (перемещения) данных, операции.  
  
 **Различия между классы DAO MFC и ODBC**  
  
 Классы DAO включают дополнительные объекты и более широкий набор методов, но только в этом разделе подробно различия в похожие классы и функции.  
  
 Возможно, очевидное различия между классами являются изменения имени для похожих классов и глобальные функции. В следующем списке приведены изменения имени объектов, методов и глобальные функции, связанные с классами баз данных:  
  
|Класс или функция|Эквивалент в классы MFC DAO|  
|-----------------------|-----------------------------------|  
|`CDatabase`|`CDaoDatabase`|  
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|  
|`CRecordset`|`CDaoRecordset`|  
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|  
|`CFieldExchange`|`CDaoFieldExchange`|  
|`RFX_Bool`|`DFX_Bool`|  
|`RFX_Byte`|`DFX_Byte`|  
|`RFX_Int`|`DFX_Short`|  
|`RFX_Long`|`DFX_Long`|  
||`DFX_Currency`|  
|`RFX_Single`|`DFX_Single`|  
|`RFX_Double`|`DFX_Double`|  
|**RFX_Date \***|**DFX_Date** (`COleDateTime`-основе)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \*    `RFX_Date` Функция основана на `CTime` и **TIMESTAMP_STRUCT**.  
  
 Ниже перечислены основные изменения в функциях, которые могут повлиять на приложение и требуют изменения более простое имя.  
  
-   Константы и макросы, используемые для указания типа откройте таких вещей, как набор записей, а набор записей параметры были изменены.  
  
     Классы ODBC MFC, необходимые для определения этих параметров через макросы или перечисляемые типы.  
  
     Классы DAO DAO предоставляет определение этих параметров в файле заголовка (DBDAOINT. (H). Таким образом тип recordset доступен член перечисления `CRecordset`, но с DAO константа вместо. Например можно использовать **моментального снимка** при указании типа `CRecordset` в ODBC, но **DB_OPEN_SNAPSHOT** при указании типа `CDaoRecordset`.  
  
-   Тип набора записей по умолчанию для `CRecordset` — **моментального снимка** стабилизации записей по умолчанию для `CDaoRecordset` — **динамический набор** (см. примечания ниже дополнительные проблемы, о моментальных снимках классов ODBC).  
  
-   ODBC `CRecordset` класс имеет новый параметр, чтобы создать тип данных последовательного доступа. В `CDaoRecordset` класса последовательного доступа не является тип набора записей, но вместо этого свойство (или параметр) определенных типов наборов записей.  
  
-   Только для добавления записей при открытии `CRecordset` объект означает, что данные набора записей может считывать и добавляется. С `CDaoRecordset` объекта, заполняемом только параметр означает буквально набора записей данных может быть только добавляется (и не считывать).  
  
-   Функции-члены классов ODBC транзакции являются членами `CDatabase` и действуют на уровне базы данных. В классах DAO транзакции функции-члены являются членами класса выше уровня (`CDaoWorkspace`) и таким образом может повлиять на несколько `CDaoDatabase` объектов, общий доступ к той же рабочей области (место транзакций).  
  
-   Класс exception был изменен. **CDBExceptions** исключение в классах ODBC и **CDaoExceptions** в классы DAO.  
  
-   `RFX_Date` использует `CTime` и **TIMESTAMP_STRUCT** объектов, пока **DFX_Date** использует `COleDateTime`. `COleDateTime` Почти идентичен `CTime`, но основе OLE 8-байтовое **даты** вместо 4-байтовый `time_t` может содержать гораздо больший диапазон данных.  
  
    > [!NOTE]
    >  DAO (`CDaoRecordset`) моментальные снимки доступны только для чтения во время ODBC (`CRecordset`) моментальных снимков может быть обновляемым, в зависимости от того, что драйвер и использование библиотеки курсоров ODBC. При использовании библиотеки курсоров `CRecordset` моментальные снимки являются обновляемыми. Если вы используете какие-либо драйверы Microsoft 3.0 с пакетом обновления драйвера рабочий стол без библиотеку курсоров ODBC `CRecordset` моментальные снимки доступны только для чтения. Если вы используете другой драйвер, обратитесь к Если документации драйвера моментальные снимки (**STATIC_CURSORS**) доступны только для чтения.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

