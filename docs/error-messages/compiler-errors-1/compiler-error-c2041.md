---
title: Ошибка компилятора C2041 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 747dd5621aec556e89fee2ab8e7ff512736e408c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2041"></a>Ошибка компилятора C2041
Недопустимая цифра «знак» для основания «число»  
  
 Указанный символ не является допустимой цифрой для основания (например, восьмеричного или шестнадцатеричного).  
  
 Следующий пример приводит к возникновению ошибки C2041:  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 Возможное решение  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```