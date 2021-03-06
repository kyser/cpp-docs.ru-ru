---
title: Создание простого объекта-получателя | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 711aaaff2bc4e012ba4c4ef78465f06c51b9d307
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-simple-consumer"></a>Создание простого объекта-получателя
Используйте мастер проектов ATL и Мастер потребителя ATL OLE DB для создания объекта-получателя OLE DB-шаблоны.  
  
#### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Создание консольного приложения для объекта-получателя OLE DB  
  
1.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
2.  В области "типы проектов", щелкните **проекты Visual C++** папки, а затем щелкните **проект Win32** значок в области шаблонов. В **имя** введите имя проекта, например, **MyCons**.  
  
3.  Нажмите кнопку **ОК**.  
  
     Откроется мастер проектов Win32.  
  
4.  На **параметры приложения** выберите **консольное приложение**, а затем выберите **добавить поддержку ATL**.  
  
5.  Нажмите кнопку **Готово** закрыть мастер и создать проект.  
  
 Затем используйте мастер потребителя ATL OLE DB для добавления объекта потребителя OLE DB.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>Создание объекта-получателя с помощью мастера потребителя ATL OLE DB  
  
1.  В представлении классов щелкните правой кнопкой мыши `MyCons` проекта.  
  
2.  В контекстном меню выберите **добавить**, а затем нажмите кнопку **Добавление класса**.  
  
     **Добавить класс** откроется диалоговое окно.  
  
3.  В области категорий щелкните **Visual C++**, нажмите кнопку **потребителя ATL OLE DB** значок в панели «шаблоны», а затем выберите **откройте**.  
  
     Появится Мастер потребителя ATL OLE DB.  
  
4.  Нажмите кнопку **источника данных** кнопки.  
  
     **Свойства связи данных** откроется диалоговое окно.  
  
5.  В **свойства связи данных** диалогового окна поле, выполните следующие действия:  
  
    -   На **поставщика** укажите поставщика OLE DB.  
  
    -   На **подключения** укажите имя сервера, имя пользователя и пароль для источника данных и базы данных на сервере.  
  
    > [!NOTE]
    >  Проблема безопасности с **Разрешить сохранение пароля** функция **свойства связи данных** диалоговое окно. В **введите данные для входа сервер**, существует два переключателя: **встроенные средства безопасности Windows NT используется** и **использовать указанные имя пользователя и пароль**.  
  
    > [!NOTE]
    >  При выборе **использовать указанные имя пользователя и пароль**, вы можете сохранить пароль (с помощью **Разрешить сохранение пароля** флажок), однако этот параметр не является безопасным. Рекомендуется выбрать **встроенные средства безопасности Windows NT используется**; этот параметр использует Windows NT, чтобы подтвердить свою личность.  
  
    > [!NOTE]
    >  Если невозможно использовать средства безопасности Windows NT, запрашивать у пользователя пароль или сохранить пароль в расположении с механизмами безопасности для его защиты следует использовать приложения среднего уровня (а не в исходном коде).  
  
     После выбора поставщика и других параметров, нажмите кнопку **проверить подключение** для проверки значений, заданных на предыдущих страницах диалогового окна. Если **результатов** поле отчеты `Test connection succeeded`, нажмите кнопку **ОК** для создания связи с данными.  
  
     **Выбор объектов базы данных** откроется диалоговое окно.  
  
6.  Используйте древовидный элемент управления для выбора таблицы, представления или хранимой процедуры. В рамках данного руководства выберите таблицу Products из базы данных "Борей".  
  
7.  Нажмите кнопку **ОК**. При этом снова Мастер потребителя ATL OLE DB.  
  
8.  Имена для завершения работы мастера `Class` и **h-файл** на основе имени таблицы, представления или хранимой процедуры, которые вы выбрали. Эти имена можно изменить, если требуется.  
  
9. Очистить **атрибуты** флажок, чтобы мастер создавал код потребителя с помощью [классы шаблонов OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) вместо значения по умолчанию [атрибуты потребителя OLE DB](../../windows/ole-db-consumer-attributes.md).  
  
10. В разделе **тип**выберите **команда**.  
  
     Мастер создает [CCommand](../../data/oledb/ccommand-class.md)-основе потребителем, при выборе **команда** или [CTable](../../data/oledb/ctable-class.md)-основе потребителем, при выборе **таблицы**. После выбора объекта называется классу таблицы или команды, но можно изменить имя.  
  
11. В разделе **поддержки**, оставьте **изменений**, **вставить**, и **удалить** флажки.  
  
     Выберите **изменений**, **вставить**, и **удалить** флажки при необходимости поддержки изменений, вставки или удаления записей в наборе строк. Дополнительные сведения о записи данных в данных хранения см. в разделе [обновление наборов строк](../../data/oledb/updating-rowsets.md).  
  
12. Нажмите кнопку **Готово** для создания потребителя.  
  
 Мастер создает класс команд и класс записей пользователя, как показано в [классы, создаваемые мастером потребителя](../../data/oledb/consumer-wizard-generated-classes.md). Класс команд будет иметь имя, введенное на `Class` поле в мастере (в этом случае `CProducts`), и класс записей пользователя будет иметь имя в формате «*ClassName*метод доступа» (в этом случае `CProductsAccessor`).  
  
> [!NOTE]
>  Мастер помещает следующую строку в файл Products.h:  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Эта строка предотвращает компиляцию и напоминание о проверке строки подключения для жестко запрограммированные пароли. После проверки строки подключения, можно удалить эту строку кода.  
  
## <a name="see-also"></a>См. также  
 [Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)