---
title: float_control | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7ac671c938b80fc69b8214456efecf798e1e5f6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="floatcontrol"></a>float_control
Указывает поведение чисел с плавающей запятой для функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Флаги  
 `value`, `setting` **[принудительной]**  
 Указывает поведение чисел с плавающей запятой. `value` может быть **точный** или **за исключением**. Дополнительные сведения см. в разделе [/fp (определение поведения с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md). `setting` может быть **на** или **off**.  
  
 Если `value` — **точный**, параметры для **точный** и **за исключением** были указаны. **за исключением** можно присвоить только значение **на** при **точный** задается значение **на**.  
  
 Если необязательный **принудительной** добавлен токен, текущий параметр `value` помещается во внутренний стек компилятора.  
  
 **push**  
 Текущий параметр `float_control` помещается во внутренний стек компилятора.  
  
 **pop**  
 Удаляет `float_control` из вверху внутреннего стека компилятора и делает это новый `float_control` параметр.  
  
## <a name="remarks"></a>Примечания  
 Не удается включить `float_control precise` отключить **за исключением** включен. Аналогичным образом **точный** не может быть установлен в off при `fenv_access` включен. Чтобы перейти от строгой модели к быстродействующей с помощью прагма-директивы `float_control`, используйте следующий код:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
```  
  
 Чтобы перейти от быстродействующей модели к строгой с помощью прагма-директивы `float_control`, используйте следующий код:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
```  
  
 Другие типы директив pragma для значений с плавающей запятой:  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Пример  
 В следующем примере показан перехват исключения переполнения при операции с плавающей запятой с помощью прагма-директивы `float_control`.  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
