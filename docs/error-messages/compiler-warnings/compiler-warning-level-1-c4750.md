---
title: Предупреждение (уровень 1) C4750 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ffe378f8d2466e702c90127e44f3b48831abf50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4750"></a>Предупреждение компилятора (уровень 1) C4750
"идентификатор": функция с _alloca() включена в цикл  
  
 Функция "идентификатор" принудительно выполняет встраиваемую подстановку функции [_alloca](../../c-runtime-library/reference/alloca.md) в цикле, что может привести к переполнению стека при выполнении цикла.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что функция "идентификатор" не будет изменена с помощью описателя [__forceinline](../../cpp/inline-functions-cpp.md) .  
  
2.  Убедитесь, что функция "идентификатор" не содержит функцию [_alloca](../../c-runtime-library/reference/alloca.md) , которая включена в цикл.  
  
3.  Не указывайте параметр компиляции [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md)или [/Og](../../build/reference/og-global-optimizations.md) .  
  
4.  Поместите функцию [_alloca](../../c-runtime-library/reference/alloca.md) в [инструкцию try-except](../../cpp/try-except-statement.md) , которая будет перехватывать переполнение стека.  
  
## <a name="example"></a>Пример  
 В следующем примере кода `MyFunction` вызывается в цикле, и `MyFunction` вызывает функцию `_alloca` . Модификатор `__forceinline` вызывает встраиваемую подстановку функции `_alloca` .  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [_alloca](../../c-runtime-library/reference/alloca.md)