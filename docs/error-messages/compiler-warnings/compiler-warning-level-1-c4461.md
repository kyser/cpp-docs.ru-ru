---
title: Предупреждение компилятора (уровень 1) C4461 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884daeb7497f6664cecf864ec705891cac62f48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4461"></a>Предупреждение компилятора (уровень 1) C4461
«Тип»: этот класс содержит метод завершения «finalizer», но нет деструктора «dtor»  
  
 Присутствие метода завершения в типе обозначает удаление ресурсов. Если метод завершения явно не вызывается из деструктора типа, общеязыковая среда выполнения определяет время выполнения метода завершения после объект выходит за пределы области.  
  
 Если деструктор определяется в типе и явно вызывать метод завершения из деструктора, определенно можно использовать метод завершения.  
  
 Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4461.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```