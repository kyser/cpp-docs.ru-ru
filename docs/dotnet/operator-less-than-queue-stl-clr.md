---
title: оператор&lt; (очередь) (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: 2c981e2b-9a88-4b4a-8060-9ac24d5631f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a590a2e1ccb9ea840508084360eecd1cacf62a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operatorlt-queue-stlclr"></a>оператор&lt; (очередь) (STL/CLR)
Очередь меньше сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
## <a name="remarks"></a>Примечания  
 Оператор функция возвращает значение true, если для нижнюю позицию `i` которого `!(right[i] < left[i])` верно, кроме того, `left[i] < right[i]`. В противном случае он возвращает `left->` [queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` использовать для тестирования ли `left` упорядочен до `right` при двух очереди являются сравниваемых элемент элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_queue_operator_lt.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
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
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [очереди (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [оператор == (очередь) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)   
 [оператор! = (очередь) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)   
 [оператор > = (очередь) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [оператор > (очередь) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)   
 [operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)