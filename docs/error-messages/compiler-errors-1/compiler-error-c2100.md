---
title: Ошибка компилятора C2100 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2100
dev_langs:
- C++
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bdea978fe5012a09325a39f706b40236ff60baa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2100"></a>Ошибка компилятора C2100
Недопустимое косвенное обращение  
  
 Оператор косвенного обращения ( `*` ) применяется к значению не являющимся указателем.  
  
 Следующий пример приводит к возникновению ошибки C2100:  
  
```  
// C2100.cpp  
int main() {  
   int r = 0, *s = 0;  
   s = &r;  
   *r = 200;   // C2100  
   *s = 200;   // OK  
}  
```