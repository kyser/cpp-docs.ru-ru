---
title: Ошибка компилятора C2093 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2093
dev_langs:
- C++
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11419a7df335bd87077759228be1256c92d09caa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2093"></a>Ошибка компилятора C2093
«variable1»: не удается инициализировать с помощью адреса автоматической переменной «variable2»  
  
 При компиляции с параметром [/Za](../../build/reference/za-ze-disable-language-extensions.md), программа пыталась использовать автоматическую переменную в качестве инициализатора.  
  
 Следующий пример приводит к возникновению ошибки C2093:  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```