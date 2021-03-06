---
title: Ошибка компилятора C3490 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 593e5509ada926f27243a761da3470eb2d846a22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3490"></a>Ошибка компилятора C3490
"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект  
  
 Лямбда-выражение, объявленное в методе `const` , не может изменять данные недоступного для изменения члена.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите модификатор `const` из объявления метода.  
  
## <a name="example"></a>Пример  
 Приведенный ниже пример вызывает ошибку C3490, так как переменная-член `_i` изменяется в методе `const` .  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере ошибка C3490 устраняется путем удаления модификатора `const` из объявления метода.  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)