---
title: multimap::Reference (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: bc402641-8310-479f-b345-b9646e534c00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9e41b689996f0f6004b1ae91e755311bd9295c7c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="multimapreference-stlclr"></a>multimap::reference (STL/CLR)
Тип ссылки на элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает ссылку на элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_multimap_reference.cpp   
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
    Mymultimap::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mymultimap::reference ref = *it;   
        System::Console::Write(" [{0} {1}]", ref->first, ref->second);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [несколько карт (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::const_reference (STL/CLR)](../dotnet/multimap-const-reference-stl-clr.md)   
 [multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)