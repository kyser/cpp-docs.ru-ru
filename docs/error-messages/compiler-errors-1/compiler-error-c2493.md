---
title: Ошибка компилятора C2493 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2493
dev_langs:
- C++
helpviewer_keywords:
- C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 336378894f5bc6d4e0dc061b630f8517b97e89c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2493"></a>Ошибка компилятора C2493
Недопустимая форма __based  
  
 Объект `__based` выражения должен быть основан на указатель.  
  
 Следующий пример приводит к возникновению ошибки C2493:  
  
```  
// C2493.cpp  
// compile with: /c  
char mybase;  
int __based(mybase) ptr;   // C2493  
  
// OK  
char * mybase;  
int __based(mybase) * ptr;  
```