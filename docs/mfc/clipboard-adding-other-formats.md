---
title: 'Буфер обмена: Добавление других форматов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c28fd1d628d0aed79028e43d9cce383f3acbb4ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="clipboard-adding-other-formats"></a>Буфер обмена. Добавление других форматов
В этом разделе объясняется, как развертывать список поддерживаемых форматов, особенно для поддержки OLE. Раздел [буфер обмена: копирование и вставка данных](../mfc/clipboard-copying-and-pasting-data.md) описывается минимальная реализация необходима поддержка копирования и вставки из буфера обмена. Если все реализации, только форматы, буфер обмена: `CF_METAFILEPICT`, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**и, возможно, `CF_LINKSOURCE`. Большинство приложений должны Дополнительные форматы в буфере обмена больше трех.  
  
##  <a name="_core_registering_custom_formats"></a> Регистрация пользовательских форматов  
 Чтобы создать собственный пользовательский формат, выполните ту же процедуру, используется при регистрации любой пользовательский формат буфера обмена: передать имя формата **RegisterClipboardFormat** функции и использовать ее возвращаемое значение в качестве идентификатор формата.  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Форматы помещения в буфер обмена  
 Чтобы добавить дополнительные форматы которые помещены в буфер обмена, необходимо переопределить `OnGetClipboardData` функции в класс, производный от либо `COleClientItem` или `COleServerItem` (в зависимости от данных для копирования собственного). В этой функции следует использовать следующую процедуру.  
  
#### <a name="to-place-formats-on-the-clipboard"></a>Чтобы поместить форматы в буфер обмена  
  
1.  Создание объекта `COleDataSource`.  
  
2.  Передать этот источник данных функции, которая добавляет в список поддерживаемых форматов ваш собственные форматы данных путем вызова `COleDataSource::CacheGlobalData`.  
  
3.  Добавьте стандартных форматов, вызвав метод `COleDataSource::CacheGlobalData` для каждого стандартного формата, которую требуется поддерживать.  
  
 Этот метод используется в программе MFC OLE образец [HIERSVR](../visual-cpp-samples.md) (проверьте `OnGetClipboardData` функцию-член **CServerItem** класса). В этом образце отличается только этот шаг 3 не реализован, поскольку HIERSVR поддерживает другие стандартные форматы.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Объекты и данные источников данных OLE и универсальный передачи данных](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [Перетаскивание OLE](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>См. также  
 [Буфер обмена. Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

