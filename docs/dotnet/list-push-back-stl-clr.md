---
title: List::push_back (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::push_back
dev_langs:
- C++
helpviewer_keywords:
- push_back member [STL/CLR]
ms.assetid: f2c70470-a899-4e5f-8f3e-b55d6a8bff0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 669a83de8c904d9e129f6351c64cd7d6b11f77d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="listpushback-stlclr"></a>list::push_back (STL/CLR)
Добавляет новый последний элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void push_back(value_type val);  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член вставляет элемент со значением `val` на конец управляемой последовательности. Используется для добавления другого элемента в список.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_push_back.cpp   
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
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)   
 [List::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)   
 [list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)