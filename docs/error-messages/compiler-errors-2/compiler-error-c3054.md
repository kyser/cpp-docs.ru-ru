---
title: Ошибка компилятора C3054 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3054
dev_langs:
- C++
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9880373d0d401c15754a2aaf6759fe2c6c68574
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3054"></a>Ошибка компилятора C3054
Директива #pragma omp parallel в настоящее время не поддерживается в универсальном классе или функции  
  
 Дополнительные сведения см. в разделе [универсальных шаблонов](../../windows/generics-cpp-component-extensions.md) и [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3054:  
  
```  
// C3054.cpp  
// compile with: /openmp /clr /c  
#include <omp.h>  
  
ref struct MyBaseClass {  
   // Delete the following 7 lines to resolve.  
   generic <class ItemType>  
   void Test(ItemType i) {   // C3054  
      #pragma omp parallel num_threads(4)  
      {  
         int i = omp_get_thread_num();  
      }  
   }  
  
   // OK  
   void Test2() {  
      #pragma omp parallel num_threads(4)  
      {  
         int i = omp_get_thread_num();  
      }  
   }  
};  
```