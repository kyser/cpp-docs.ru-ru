---
title: _umul128 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __umul128
dev_langs:
- C++
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6998b51be8fd11092c4266fa7eee7434be8e5b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="umul128"></a>_umul128
**Блок, относящийся только к системам Microsoft**  
  
 Умножает два 64-разрядных целых числа без знака, переданных в качестве первых двух аргументов, и помещает старшие 64 разряда произведения в 64-разрядное целое число без знака, на которое указывает `HighProduct` и возвращает младшие 64 разряда произведения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 _umul128(   
   unsigned __int64 Multiplier,   
   unsigned __int64 Multiplicand,   
   unsigned __int64 *HighProduct   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Multiplier`  
 Первое 64-разрядное целое для умножения.  
  
 [in] `Multiplicand`  
 Второе 64-разрядное целое для умножения.  
  
 [выходной] `HighProduct`  
 Старшие 64 разряда произведения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Младшие 64 разряда произведения.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|Header|  
|---------------|------------------|------------|  
|`_umul128`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<Intrin.h >|  
  
## <a name="example"></a>Пример  
  
```  
// umul128.c  
// processor: IPF, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_umul128)  
  
int main()  
{  
    unsigned __int64 a = 0x0fffffffffffffffI64;  
    unsigned __int64 b = 0xf0000000I64;  
    unsigned __int64 c, d;  
  
    d = _umul128(a, b, &c);  
  
    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);  
}  
```  
  
```Output  
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)