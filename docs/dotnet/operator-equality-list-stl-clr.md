---
title: оператор == (список) (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::operator==
dev_langs:
- C++
helpviewer_keywords:
- operator== member [STL/CLR]
ms.assetid: b290f7df-1bcd-44a5-a89e-925a0fcb8c65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 83125edf3b2aee5ca4152852c0d60fd42836c23f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operator-list-stlclr"></a>operator== (list) (STL/CLR)
Список равно сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Value>  
    bool operator==(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 left  
 Левый контейнер для сравнения.  
  
 right  
 Правый контейнер для сравнения.  
  
## <a name="remarks"></a>Примечания  
 Функция оператор возвращает значение true, только в том случае, если последовательности, на которые управляются `left` и `right` имеют одинаковую длину и для каждого положения `i`, `left[i] ==` `right[i]`. Можно использовать для тестирования ли `left` упорядочен таким же, как `right` при двух списков, сравниваемые элемент элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_operator_eq.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [оператор! = (список) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)   
 [оператор\< (список) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)   
 [оператор > = (список) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)   
 [оператор > (список) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)   
 [operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)