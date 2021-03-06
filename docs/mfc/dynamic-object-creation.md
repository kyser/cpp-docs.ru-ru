---
title: Динамическое создание объектов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5763e3f0f3ee5a0e58ac20fe9f637e4f7e097999
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-object-creation"></a>Динамическое создание объектов
В этой статье объясняется, как создать объект динамически во время выполнения. Процедура использует сведения о классе во время выполнения, как описано в статье [доступ к сведениям о классе во время выполнения](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Для динамического создания объектом по заданному его класса среды выполнения  
  
1.  Используйте следующий код для динамического создания объекта с помощью `CreateObject` функция `CRuntimeClass`. Обратите внимание, что в случае сбоя `CreateObject` возвращает **NULL** не вызывает исключения:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Использование CObject](../mfc/using-cobject.md)

