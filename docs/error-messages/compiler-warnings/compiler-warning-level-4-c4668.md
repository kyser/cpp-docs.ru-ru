---
title: Предупреждение (уровень 4) C4668 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a6349e867382a327f53676583f5daad7df80dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4668"></a>Предупреждение компилятора (уровень 4) C4668
"символ" не определен в качестве макроса препроцессора и будет заменен в "директивах" на "0"  
  
 В директиве препроцессора использовался символ, который не был определен. Символ принимает значение false. Для определения символа, можно использовать [#define-директива](../../preprocessor/hash-define-directive-c-cpp.md) или [/D](../../build/reference/d-preprocessor-definitions.md) параметр компилятора.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4668:  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```