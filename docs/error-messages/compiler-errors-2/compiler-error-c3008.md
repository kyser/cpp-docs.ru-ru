---
title: Ошибка компилятора C3008 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3008
dev_langs:
- C++
helpviewer_keywords:
- C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d70f065c8cff6154aa706203210973f67b82a73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3008"></a>Ошибка компилятора C3008
"аргумент": в аргументе директивы OpenMP "директива" отсутствует закрывающая скобка ")"  
  
 Директива OpenMP, которая принимает аргумент, не содержит закрывающую скобку.  
  
 При компиляции следующего примера возникнет ошибка C3008:  
  
```  
// C3008.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x   // C3008  
   // Try the following line instead:  
   #pragma omp parallel shared(x)  
   {  
   }  
}  
```