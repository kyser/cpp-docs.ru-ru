---
title: Ошибка компилятора C2970 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0775f9d771b2c9497b3dc731e26c6a3b4e6ab30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2970"></a>Ошибка компилятора C2970
«класс»: параметр шаблона «параметр»: «аргумент»: выражение, включающее объекты с внутренней компоновкой не может использоваться как аргумент не является типом  
  
 Нельзя использовать имя или адрес статической переменной в качестве аргумента шаблона. Класс шаблона ожидает константу, которая может быть вычислено во время компиляции.  
  
 Следующий пример приводит к возникновению ошибки C2970:  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```