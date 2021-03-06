---
title: MAP::value_type (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map::value_type
dev_langs:
- C++
helpviewer_keywords:
- value_type member [STL/CLR]
ms.assetid: 9f02ac42-c1e0-4671-bed3-72d6c06a1e66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a87302d57b26f2e498974d16271bb3257dcf4031
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mapvaluetype-stlclr"></a>map::value_type (STL/CLR)
Тип элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef generic_value value_type;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип является синонимом `generic_value`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_map_value_type.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using value_type   
    for (Mymap::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mymap::value_type val = *it;   
        System::Console::Write(" [{0} {1}]", val->first, val->second);   
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
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [MAP::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)   
 [MAP::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)   
 [map::reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)