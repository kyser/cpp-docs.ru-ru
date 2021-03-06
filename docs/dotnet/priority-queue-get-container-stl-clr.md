---
title: priority_queue::get_container (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::get_container
dev_langs:
- C++
helpviewer_keywords:
- get_container member [STL/CLR]
ms.assetid: bd3cc63b-776f-495c-bf81-a9e8ba189a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5bb6ca83c8be9e1ab7b39a0f3552adc2ebaafa17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="priorityqueuegetcontainer-stlclr"></a>priority_queue::get_container (STL/CLR)
Обращается к базового контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
container_type get_container();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает базового контейнера. Используется для обхода ограничений, накладываемых на оболочку контейнера.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_priority_queue_get_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)