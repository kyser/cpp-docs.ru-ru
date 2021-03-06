---
title: Поддержка базы данных, мастер приложений MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.database
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86c6cd679b69bf84504d6735ca39d572bd48ff07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="database-support-mfc-application-wizard"></a>Поддержка базы данных, мастер приложений MFC
Эта страница предоставляет параметры, которые позволяют указать уровень базы данных поддерживают (и источника данных, при необходимости) для проекта.  
  
 **Поддержка баз данных**  
 Задает уровень поддержки базы данных для проекта.  
  
|Параметр|Описание|  
|------------|-----------------|  
|**None**|Не поддерживает базы данных. Этот параметр используется по умолчанию.|  
|**Только файлы заголовков**|Предоставляет базовый уровень поддержки базы данных для приложения. Если выбрана поддержка ODBC под **тип клиента**, мастер приложений MFC включает в проект файл заголовка AFXDB. З. Он добавляет библиотеки, но не создает классы любой конкретной базе данных. Можно создать наборы записей позже и использовать их для проверки и обновления записей. Если выбрана поддержка OLE DB в списке **тип клиента**, включаются следующие файлы заголовков: ATLBASE. H AFXOLEDB. H ATLPLUS. H|  
|**Представление базы данных без поддержки файлов**|Включает файлы заголовков баз данных, библиотек DLL, представление записей и набор записей. (Доступно только для приложений с помощью **поддержка архитектуры Document/view** параметром, выбранным в [тип приложения](../../mfc/reference/application-type-mfc-application-wizard.md) страницы.) Этот параметр включает поддержку документов, но не поддержку сериализации. Если вы решили включить представления базы данных, необходимо указать источник данных.|  
|**Представление базы данных с поддержкой файлов**|Включает файлы заголовков баз данных, библиотек DLL, представление записей и набор записей. (Доступно только для приложений с помощью **поддержка архитектуры Document/view** параметром, выбранным в **тип приложения** страницы.) Этот параметр поддерживает сериализацию документов, которую можно использовать, например, для обновления файла профиля пользователя. Приложения баз данных обычно выполняются на основе записей, а не для каждого файла, поэтому не требуется сериализации. Однако могут иметь специальное использование для сериализации. Если вы решили включить представления базы данных, необходимо указать источник данных.|  
  
> [!NOTE]
>  В разделе **база данных поддерживает**, если выбрать **представление без поддержки файлов базы данных** или **представление с поддержкой файлов базы данных**, представление классов будет отличаться в зависимости на ваш **тип клиента** выбора следующим образом:  
  
-   При выборе **ODBC** под **тип клиента**, а затем класс представления приложения является производным от [CRecordView](../../mfc/reference/crecordview-class.md). Этот класс, связанный с [CRecordset](../../mfc/reference/crecordset-class.md)-производный класс, который автоматически создается мастером приложений MFC. Данный параметр предоставляет приложение форм, в котором представление записей используется для просмотра и обновления записей в наборе записей.  
  
-   При выборе **OLE DB** под **тип клиента**, то класс представления является производным от [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), связанный с [CTable](../../data/oledb/ctable-class.md) или [CCommand](../../data/oledb/ccommand-class.md)-производного класса.  
  
 **Тип клиента**  
 Указывает, используется ли в проекте классы OLE DB или ODBC.  
  
|Параметр|Описание|  
|------------|-----------------|  
|**OLE DB**|Если этот параметр выбран, при нажатии **источника данных** кнопки **свойства связи данных** мастера для создания подключения к источнику данных OLE DB.|  
|**ODBC**|Если этот параметр выбран, при нажатии **источника данных** кнопки **Выбор источника данных** мастера для создания подключения к источнику данных ODBC.|  
  
 **Источник данных**  
 Нажмите кнопку **источника данных** кнопку, чтобы настроить источник данных, используя указанный драйвер или поставщик и базы данных. Если вы выбрали OLE DB в **тип клиента** , эта кнопка будет показываться **свойства связи данных** диалоговое окно. Если вы выбрали ODBC в **тип клиента** вариант, эта кнопка позволяет **Выбор источника данных** диалоговое окно. Этот параметр доступен только в том случае, если вы решили включить представление базы данных в приложение.  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Свойства подключения к данным** (OLE DB)|Устанавливает указанный источник данных с помощью указанного поставщика OLE DB. Необходимо указать поставщика OLE DB, расположение данных, источник данных, идентификатор входа и (необязательно) пароль. Сведения в этом диалоговом окне см. в разделе **источника данных** в [Мастер потребителя ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Выберите источник данных** (ODBC)|Устанавливает указанный источник данных с помощью заданного драйвера ODBC. Необходимо выбрать имя источника данных, чтобы выбрать таблицу для источника данных. Мастер выполняет привязку всех столбцов таблицы для переменных-членов из `CRecordset`-производного класса. Сведения в этом диалоговом окне см. в разделе **источника данных** в [мастер потребителей ODBC MFC](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  В предыдущих выпусках, нажав клавиши Shift **источника данных** кнопки открывается диалоговое окно открытия файла позволяет выбрать файл данных (udl). Эта функция больше не поддерживается.  
  
 **Создать класс базы данных с атрибутами**  
 Доступный для OLE DB для клиента. Указывает, использовать ли классы баз данных в созданном проекте атрибуты.  
  
 **Привязать все столбцы**  
 Доступно только для клиентов ODBC. Указывает, связаны ли все столбцы в выбранной таблице. Если этот флажок установлен, все столбцы привязаны; Если этот флажок не установлен, столбцы не связываются, и необходимо связать их вручную в классе записей.  
  
 **Type**  
 Доступно только для клиентов ODBC. Указывает, является ли набор записей динамический или статический, как описано в следующей таблице.  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Динамический набор**|Указывает, что набор записей динамический набор. Динамический набор является результатом запроса, предоставляющим индексированное представление в запрошенных данных базы данных. Динамическое подмножество кэширует только интегральный индекс исходных данных и таким образом обеспечивается повышение производительности за моментального снимка. Индекс точки непосредственно для каждой записи обнаруженные в результате запроса и указывает, если запись удалена. Также имеется доступ к обновленным данным в запрошенных записях.|  
|Снимок|Указывает, что набор записей является моментальным снимком. Моментальный снимок является результатом запроса и — это представление базы данных в один момент времени. Все записи, обнаруженные в результате запроса кэшируются, поэтому вы не видите все изменения в исходных записях.|  
  
## <a name="see-also"></a>См. также  
 [Мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md)
