---
title: "Преимущества архитектуры представления документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b48166f1002bd5a43325c2838a6d4b5a3626811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="advantages-of-the-documentview-architecture"></a>Преимущества архитектуры "документ-представление"
Ключевое преимущество использования архитектурой документ/представление MFC является архитектура особенно хорошо поддерживает несколько представлений одного документа. (Если не требуется несколько представлений и небольшой объем затрат для документов и представлений не слишком велика, в приложении, можно избежать архитектуры. [Альтернативы для архитектуры Document/View](../mfc/alternatives-to-the-document-view-architecture.md).)  
  
 Предположим, что приложение позволяет пользователям просматривать числовые данные в виде электронной таблицы или в виде диаграммы. Пользователь может понадобиться просмотреть одновременно оба необработанных данных, в виде электронной таблицы и диаграммы, полученный в результате данные. Эти отдельные представления отображаются в отдельном фреймов или разделитель областей в пределах одного окна. Теперь предположим, что пользователь может редактировать данные в таблицы и см. изменения немедленно отражаются в диаграммы.  
  
 В MFC представление электронной таблицы и представления диаграммы будет основываться на различные классы, производные от CView. Оба представления будет связан с объектом одного документа. Документ хранит данные (или может быть получен из базы данных). Оба представления, доступ к документу и отобразить данные, получаемые от него.  
  
 Когда пользователь обновляет представления, на которые просматривать вызовы объекта `CDocument::UpdateAllViews`. Эта функция уведомляет всех представлений документа, и каждое представление обновляется с использованием последних данных из документа. Один вызов `UpdateAllViews` синхронизирует различные представления.  
  
 Этот сценарий будет трудно кода без разделения данных из представления, особенно в том случае, если представления хранятся сами данные. Документ представление будет легко. Платформа выполняет большую часть работы координации.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Альтернативы для документов и представлений](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)  
  
-   [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)
