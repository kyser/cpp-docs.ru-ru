---
title: Выбор подходящего метода доступа | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 89a55127b8f7e5e0e7d338a9e7ba4f85e8c568d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="determining-which-type-of-accessor-to-use"></a>Выбор подходящего метода доступа
Во время компиляции или во время выполнения, можно определить типы данных для набора строк.  
  
 Если необходимо определить типы данных во время компиляции, используйте статический метод доступа (такие как `CAccessor`). Можно определить типы данных, вручную или с помощью мастера потребителя ATL OLE DB.  
  
 Если необходимо определить типы данных во время выполнения, используйте динамическое (`CDynamicAccessor` или его дочерние элементы) или ручного доступа (`CManualAccessor`). В этих случаях можно вызвать `GetColumnInfo` в наборе строк, чтобы вернуть сведения о привязке столбца, из которого можно определить типы.  
  
 Ниже перечислены типы доступа, предоставляемых в шаблонах потребителей. Каждый метод доступа имеет свои преимущества и недостатки. В зависимости от конкретной ситуации один тип метода доступа должен при необходимости.  
  
|Класс доступа|Привязка|Параметр|Примечание|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|Создайте запись пользователя с `COLUMN_ENTRY` макросы. Макросы для привязки элемента данных этой записи для метода доступа. При создании набора строк, не удается отменить связывание столбцов.|Да, с помощью **PARAM_MAP** запись макроса. После привязки параметров не может быть отменена.|Самый быстрый метод доступа из-за небольшого объема кода.|  
|`CDynamicAccessor`|Автоматически.|Номер|Полезно, если вы не знаете тип данных в наборе строк.|  
|`CDynamicParameterAccessor`|Автоматически, но может быть [переопределении](../../data/oledb/overriding-a-dynamic-accessor.md).|Да, если поставщик поддерживает `ICommandWithParameters`. Автоматическая привязка параметров.|Медленнее, чем `CDynamicAccessor` но полезен для вызова универсальных хранимых процедур.|  
|**CDynamicStringAccessor[A,W]**|Автоматически.|Номер|Извлекает данные из хранилища данных в виде строковых данных.|  
|`CManualAccessor`|Вручную с помощью `AddBindEntry`.|Вручную с помощью `AddParameterEntry`.|Очень быстро; только один раз привязка параметров и столбцов. Можно определить тип данных для использования. (См. [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) образец в качестве примера.) Требуется больше кода, чем `CDynamicAccessor` или `CAccessor`. Это больше похожи на прямой вызов OLE DB.|  
|`CXMLAccessor`|Автоматически.|Номер|Извлекает данные из хранилища данных в виде строковых данных и форматирует их как XML-тегами для данных.|  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)