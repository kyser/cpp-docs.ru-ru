---
title: STACK::Assign (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: 18cc35ad-23cf-4a5a-adae-d967dc5d6980
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 409e86e0ed11cd1e6cda2984105e3f23a629cd28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="stackassign-stlclr"></a>stack::assign (STL/CLR)
Заменяет все элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void assign(stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Адаптер контейнера для вставки.  
  
## <a name="remarks"></a>Примечания  
 Функция-член назначает `right.get_container()` для базового контейнера. Используется, чтобы изменить все содержимое стека.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_stack_assign.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mystack c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/stack >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)