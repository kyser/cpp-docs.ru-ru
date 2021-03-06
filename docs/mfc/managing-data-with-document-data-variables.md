---
title: Управление данными с помощью переменных данных документа | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8048a38c2ec09828c462d5b671cc0c89aec30805
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="managing-data-with-document-data-variables"></a>Управление данными с помощью переменных данных документа
Данные документа и реализуйте как переменные-члены класса документа. Например, программа Scribble объявляет член данных типа `CObList` — связанного списка, который хранит указатели на `CObject` объектов. Этот список используется для хранения массивов точек, которые составляют произвольной рисования линии.  
  
 Как реализовать член данных в документе зависит от характера приложения. Чтобы out, MFC предоставляет группу «коллекции классы» — массивов, списков и схем (словари), включая коллекциях, основанных на шаблонах C++ — а также классы, инкапсулирующие разнообразные общие типы данных, такие как `CString`, `CRect`, `CPoint`, `CSize`, и `CTime`. Дополнительные сведения об этих классах см. в разделе [Общие сведения о библиотеке классов](../mfc/class-library-overview.md) в *Справочник по библиотеке MFC*.  
  
 При определении данные элемента в документе вы добавите обычно функции-члены в класс документа, чтобы задать и получить элементы данных и другие полезные операции над ними.  
  
 Представления доступ к объекту документа, используя указатель на документ, установлены в режиме во время создания представления. Указатель this в функции-члены представления можно получить, вызвав `CView` функции-члена **GetDocument**. Убедитесь, что приведение этого указателя на свой собственный тип документа. Затем можно обращаться к членам общих документов через указатель.  
  
 Если передача данных часто требуется прямой доступ, или вы хотите использовать закрытые члены класса документа, может потребоваться сделать представление класса friend (в терминах C++) класса документа.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

