---
title: Ошибка компилятора C3899 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f40f1065514437463be06a89f01e067c4324cd2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3899"></a>Ошибка компилятора C3899
«переменная»: l значения можно использовать элементы данных initonly не разрешается напрямую в параллельной области в классе «класс»  
  
 [Initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) член данных не может инициализироваться внутри этой части конструктора, которая расположена в [параллельных](../../parallel/openmp/reference/parallel.md) области.  Это, поскольку компилятор выполняет внутреннего перемещения этого кода, таким образом, что он является больше не является частью конструктора.  
  
 Чтобы решить, инициализируйте элемент данных initonly в конструкторе, но вне параллельной области.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3899.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```