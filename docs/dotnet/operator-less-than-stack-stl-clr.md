---
title: оператор&lt; (стек) (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 77f8dd42-89d1-4ce1-a7ec-04c3a45dd3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 77ed992b33dee758b6ca7d2997135b704863c02c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-stack-stlclr"></a>оператор&lt; (стек) (STL/CLR)
Стек меньше сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
## <a name="remarks"></a>Примечания  
 Оператор функция возвращает значение true, если для нижнюю позицию `i` которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае он возвращает `left->` [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `() <` `right->size()` использовать для тестирования ли `left` упорядочен до `right` при двух стеков, сравниваемые элемент элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/stack >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [оператор == (стек) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [оператор! = (стек) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [оператор > = (стек) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [оператор > (стек) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)