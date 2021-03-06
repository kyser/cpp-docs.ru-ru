---
title: Записи пользователя | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c58807dac8ae320ee69c8e1a372fff5b9d3db02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="user-record"></a>Запись пользователя
Запись пользователя предоставляет структуру кода и данных, представляющий данные столбца для набора строк. Записи пользователя могут создаваться во время компиляции или во время выполнения. При создании поставщика, используя мастер поставщика ATL OLE DB, мастер создает запись пользователя по умолчанию, выглядит следующим образом (предполагается, что указано имя поставщика [краткое имя] «MyProvider»):  
  
```  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 Шаблоны поставщика OLE DB обрабатывают все характеристики OLE DB, касающиеся взаимодействия с клиентом. Для получения необходимых для отклика данных столбца, поставщик вызывает `GetColumnInfo` функция, которую необходимо поместить в записи пользователя. Можно явно переопределить `GetColumnInfo` в записи пользователя, например, путем объявления его в h-файл как показано ниже:  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Это соответствует следующей записи:  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Необходимо также реализовать `GetColumnInfo` в записи пользователя CPP-файле.  
  
 Макросы PROVIDER_COLUMN_MAP помочь в создании `GetColumnInfo` функции:  
  
-   BEGIN_PROVIDER_COLUMN_MAP определяет прототип функции и статического массива **ATLCOLUMNINFO** структуры.  
  
-   PROVIDER_COLUMN_ENTRY определяет и инициализирует один **ATLCOLUMNINFO**.  
  
-   END_PROVIDER_COLUMN_MAP закрывает массива и функции. Он также помещает число элементов массива в `pcCols` параметра.  
  
 При создании записи пользователя во время выполнения **GetColumnInfo** использует `pThis` параметр для получения указателя на экземпляр набора или команды. Команды и наборы строк должны поддерживать `IColumnsInfo` интерфейс, поэтому можно получить сведения о столбцах из этот указатель.  
  
 **CommandClass** и **RowsetClass** команды и набора строк, с помощью записи пользователя.  
  
 Более подробный пример переопределения `GetColumnInfo` в записи пользователя, в разделе [динамически определить столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)