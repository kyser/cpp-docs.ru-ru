---
title: hash_map::rend (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: 87fb2a06-c92b-4d86-855d-22f5c04aabdb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 28c0368b7ce7bb62eca6dedefe372a935ef0bb9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hashmaprend-stlclr"></a>hash_map::rend (STL/CLR)
Задает конец обратной управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, указывающий начало управляемой последовательности. Таким образом, он обозначает `end` обратной последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, отображаемой в обратном порядке, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_hash_map_rend.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_map::reverse_iterator rit = c1.rend();   
    --rit;   
    --rit;   
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*--rend() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*-- --rend() = [b 2]  
*--rend() = [a 1]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/hash_map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::Begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md)   
 [hash_map::End (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)   
 [hash_map::rbegin (STL/CLR)](../dotnet/hash-map-rbegin-stl-clr.md)