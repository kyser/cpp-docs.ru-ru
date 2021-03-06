---
title: Создание шаблонов документов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36650e0ae1ce042a887c6a87d1bbe62d8b6d7fe4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="document-template-creation"></a>Создание шаблонов документов
При создании нового документа в ответ на `New` или **откройте** из **файл** меню шаблон документа также создает новый объект окна по которому необходимо просмотреть документ.  
  
 Конструктор шаблона документа определяет, какие типы документов, окон и представлений, которые будут иметь возможность создавать шаблон. Это определяется аргументы, передаваемые конструктору шаблона документа. В следующем коде показано создание [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) образец приложения:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 Указатель на новый `CMultiDocTemplate` объект используется в качестве аргумента для [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Аргументы для `CMultiDocTemplate` конструктор включают идентификатор ресурса, связанный с типом документа меню и сочетания клавиш и использует три [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) макрос. `RUNTIME_CLASS` Возвращает [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) объекта для класса C++, с именем в качестве своего аргумента. Три `CRuntimeClass` объекты, передаваемые конструктору шаблона документа укажите сведения, необходимые для создания новых объектов, указанных классов во время создания документа. В примере показано создание шаблон документа, который создает `CScribDoc` объекты с `CScribView` вложенные объекты. Представления выделяются по стандартной кадра дочерних MDI-окон.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

