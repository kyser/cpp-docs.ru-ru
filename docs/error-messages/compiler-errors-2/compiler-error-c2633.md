---
title: Ошибка компилятора C2633 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2633
dev_langs:
- C++
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97bc51896487b0520245aa714eafb25a393365e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2633"></a>Ошибка компилятора C2633
«Идентификатор»: «inline» является единственным допустимым классом хранения для конструкторов  
  
 Конструктор объявлен как класс хранения, отличные от встроенной.  
  
 Следующий пример приводит к возникновению ошибки C2633:  
  
```  
// C2633.cpp  
// compile with: /c  
class C {  
   extern C();   // C2633, not inline  
   inline C();   // OK  
};  
```