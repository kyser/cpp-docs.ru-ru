---
title: set::value_compare (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare member [STL/CLR]
ms.assetid: cf45d7ae-5cd1-4633-9fe6-f0b97730465c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fa2fc0cd545acc36db6a33b5b17bc7ab21b54d5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="setvaluecompare-stlclr"></a>set::value_compare (STL/CLR)
Делегат упорядочения для значения двух элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип является синонимом делегат, который определяет порядок его значения аргументов.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_set_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    Myset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)   
 [set::value_comp (STL/CLR)](../dotnet/set-value-comp-stl-clr.md)   
 [set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)