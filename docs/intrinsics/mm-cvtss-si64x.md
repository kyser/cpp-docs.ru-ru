---
title: _mm_cvtss_si64x | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665c52fc0dd0645e25d3014cc28f9fdfba344e2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] расширенная версия преобразовать скаляр одной точности с плавающей запятой 64-разрядное целое число (`cvtss2si`) инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `value`  
 `__m128` Структуру, содержащую значения с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 64-разрядное целое, результат преобразования первого значения с плавающей запятой в целочисленный.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Первый элемент структуры значение преобразуется в целое число и возвращается. Округления управляющие биты в MXCSR используются для определения поведения округления. Значение по умолчанию режим округления — округление до ближайшего округления до четного числа, если десятичное часть равна 0,5. Поскольку `__m128` структура представляет регистр XMM, а это встроенная функция принимает значение регистра XMM и записывает его в системной памяти.  
  
 Эта процедура доступна только как встроенная функция.  
  
## <a name="example"></a>Пример  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__m128d](../cpp/m128d.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)