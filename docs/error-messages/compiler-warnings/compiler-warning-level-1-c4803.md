---
title: Предупреждение компилятора предупреждение (уровень 1) C4803 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c574b51fc13f9224d48495f8b591a56abdc74966
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4803"></a>Предупреждение компилятора (уровень 1) C4803
«метод»: метод raise имеет отличается от класса хранения события, «событие»  
  
Событие методы должны иметь тот же класс хранения, что и объявление события. Компилятор корректирует методы события таким образом, чтобы классы хранения совпадают.  
  
Это предупреждение может возникать, если имеется класс, который реализует событие интерфейса. Компилятор не создает неявно метода raise событие в интерфейсе. При реализации этого интерфейса в классе, компилятор неявно создает метода raise и этот метод не будет виртуальным, поэтому предупреждение. Дополнительные сведения о событиях см. в разделе [событие](../../windows/event-cpp-component-extensions.md).  
  
В разделе [предупреждение](../../preprocessor/warning.md) Дополнительные сведения о том, как отключить предупреждение.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4803.  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  
