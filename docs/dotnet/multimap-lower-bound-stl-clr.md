---
title: multimap::lower_bound (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::lower_bound
dev_langs:
- C++
helpviewer_keywords:
- lower_bound member [STL/CLR]
ms.assetid: b8f9b2c2-ebcd-4553-b410-75fd8d472a49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2267f889a27a1b48989c5bd9aebe9dd9b7722e93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="multimaplowerbound-stlclr"></a>multimap::lower_bound (STL/CLR)
Начало находит диапазон, соответствующий указанному ключу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Параметры  
 клавиша  
 Искомое значение ключа.  
  
## <a name="remarks"></a>Примечания  
 Функция-член определяет первый элемент `X` в управляемой последовательности, соответствующим образом для `key`. Если такого элемента не существует, она возвращает [multimap::end (STL/CLR)](../dotnet/multimap-end-stl-clr.md)`()`; в противном случае он возвращает итератор, задающий `X`. Используется для поиска в начале последовательности элементов в данный момент в управляемой последовательности, которые соответствуют заданному ключу.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_multimap_lower_bound.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Mymultimap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = [a 1]  
*lower_bound(L'b') = [b 2]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [несколько карт (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::Count (STL/CLR)](../dotnet/multimap-count-stl-clr.md)   
 [multimap::equal_range (STL/CLR)](../dotnet/multimap-equal-range-stl-clr.md)   
 [multimap::Find (STL/CLR)](../dotnet/multimap-find-stl-clr.md)   
 [multimap::upper_bound (STL/CLR)](../dotnet/multimap-upper-bound-stl-clr.md)