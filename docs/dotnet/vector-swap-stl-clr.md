---
title: Vector::Swap (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 9ad083fe-f79b-4b97-8013-581fd00c059a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 085ecfa966cb852b44500cf72c16ad14f535f1a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="vectorswap-stlclr"></a>vector::swap (STL/CLR)
Меняет местами содержимое двух контейнеров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void swap(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для обмена содержимым.  
  
## <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `*this` и `right`. Она делает это в константном времени, и он не создает исключений. Используется в качестве быстро меняет местами содержимое двух контейнеров.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_vector_swap.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::vector<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/vector >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)