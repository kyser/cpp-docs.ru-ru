---
title: Ошибка компилятора C2602 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2602
dev_langs:
- C++
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07fd581d8d95ae33ba2a38ea45a458f2085e0ef1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2602"></a>Ошибка компилятора C2602
«класс::идентификатор» не является членом базового класса «класс»  
  
 `Identifier` может быть недоступна, так как он не является членом, унаследованным от базового класса.  
  
 Следующий пример приводит к возникновению ошибки C2602:  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```