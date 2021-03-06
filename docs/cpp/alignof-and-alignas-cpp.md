---
title: alignof и alignas (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2988d1260cac91e2614765aba8ae1b9be9b922
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="alignof-and-alignas-c"></a>alignof и alignas (C++)
Спецификатор типа `alignas` — стандартный для C++ переносимый способ задания настраиваемого выравнивания переменных и пользовательских типов. Оператор `alignof` — аналогичен стандартному переносимому способу получения выравнивания указанного типа или переменной.  
  
## <a name="example"></a>Пример  
 `alignas` можно использовать для класса, прохода или объединения, а также для отдельных членов. При обнаружении нескольких спецификаторов `alignas` компилятор выберет самый строгий из них (который имеет наибольшее значение).  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Выравнивание](../cpp/alignment-cpp-declarations.md)