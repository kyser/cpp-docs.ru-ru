---
title: Ошибка компилятора C2477 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2477
dev_langs:
- C++
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca1212a664582f19e91fbf21bde36431ec715946
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2477"></a>Ошибка компилятора C2477
«член»: не удается инициализировать статические данные-член в производном классе  
  
 Статические данные-член шаблона класса был инициализирован неправильно. Это критическое изменение в версии компилятора Visual C++ до Visual Studio .NET 2003, в целях обеспечения соответствия стандарту ISO c++.  
  
 Следующий пример приводит к возникновению ошибки C2477:  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```