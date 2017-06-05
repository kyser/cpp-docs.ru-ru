---
title: "C2178 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 96232cdb52fc84a90c768fa23b8a98da913c7982
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2178"></a>C2178 ошибки компилятора  
  
"*идентификатор*«не может объявляться с»*описатель*" спецификатор  
  
Объект `mutable` используется спецификатор в объявлении, но спецификатора не допускается в данном контексте.  
  
`mutable` Указателя может применяться только к именам членов класса данных и не может применяться к именам, объявленным `const` или `static`и не может применяться к элементам ссылки.  
  
## <a name="example"></a>Пример  
  
Следующий пример показывает, как может возникнуть C2178 и способы ее устранения.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  
