---
title: Ошибка компилятора C3232 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3232
dev_langs:
- C++
helpviewer_keywords:
- C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a770613c2cd851d48d7424166a90ed8183e5e536
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3232"></a>Ошибка компилятора C3232
"параметр": параметр универсального типа нельзя использовать в полном имени  
  
 Параметр универсального типа был использован неправильно.  
  
 Следующий пример приводит к возникновению ошибки C3232:  
  
```  
// C3232.cpp  
// compile with: /clr  
generic <class T>  
ref class C {  
   typename T::TYPE t;   // C3232  
};  
```