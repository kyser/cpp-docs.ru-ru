---
title: _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _atoldbl
- _atoldbl_l
- _atodbl
- _atoflt
- _atoflt_l
- _atodbl_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _atoflt
- _atoflt_l
- atodbl_l
- atoflt_l
- _atoldbl
- _atoldbl_l
- atodbl
- _atodbl_l
- atoldbl
- atoflt
- atoldbl_l
- _atodbl
dev_langs:
- C++
helpviewer_keywords:
- _atodbl function
- _atoldbl_l function
- atoflt function
- atoflt_l function
- atoldbl function
- _atoldbl function
- atodbl_l function
- _atoflt_l function
- atoldbl_l function
- atodbl function
- string conversion, to floating point values
- _atoflt function
- _atodbl_l function
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da36dfae81f33f5fb30a1a4bc93a57437980d720
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atodbl-atodbll-atoldbl-atoldbll-atoflt-atofltl"></a>_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l

Преобразует строку в значение типа double (**_atodbl**), long double (**_atoldbl**), или число с плавающей запятой (**_atoflt**).

## <a name="syntax"></a>Синтаксис

```C
int _atodbl( _CRT_DOUBLE * value, char * str );
int _atodbl_l ( _CRT_DOUBLE * value, char * str, locale_t locale );
int _atoldbl( _LDOUBLE * value, char * str );
int _atoldbl_l ( _LDOUBLE * value, char * str, locale_t locale );
int _atoflt( _CRT_FLOAT * value, const char * str );
int _atoflt_l( _CRT_FLOAT * value, const char * str, locale_t locale );
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Двойное и длинное двойное значение, а также число с плавающей запятой формируются путем преобразования строки в значение с плавающей запятой. Эти значения упаковываются в структуре.

*str*<br/>
Строка для синтаксического анализа, которую необходимо преобразовать в значение с плавающей запятой.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха. Возможные коды ошибок, **_UNDERFLOW** или **_OVERFLOW**, которые определены в файле заголовка \<math.h >.

## <a name="remarks"></a>Примечания

Эти функции преобразуют строку в значение с плавающей запятой. Различие между этими функциями и **atof** — семейство функций, эти функции не создают код с плавающей запятой, а не вызовут исключения оборудования. Вместо этого условия ошибок помечаются как коды ошибок.

Если строка не имеет допустимый Интерпретация как значение с плавающей запятой, *значение* установлено в ноль и возвращаемое значение равно нулю.

Версии этих функций, имеющих **_l** суффиксом идентичны версии без суффикса, за исключением того, что они используют *языкового стандарта* параметр, передаваемый в вместо текущего потока языковой стандарт.

## <a name="requirements"></a>Требования

|Подпрограммы|Обязательный заголовок|
|--------------|---------------------|
|**_atodbl**, **_atoldbl**, **_atoflt**<br /><br /> **_atodbl_l**, **_atoldbl_l**, **_atoflt_l**|\<stdlib.h>|

## <a name="example"></a>Пример

```C
// crt_atodbl.c
// Uses _atodbl to convert a string to a double precision
// floating point value.

#include <stdlib.h>
#include <stdio.h>

int main()
{
   char str1[256] = "3.141592654";
   char abc[256] = "abc";
   char oflow[256] = "1.0E+5000";
   _CRT_DOUBLE dblval;
   _CRT_FLOAT fltval;
   int retval;

   retval = _atodbl(&dblval, str1);

   printf("Double value: %lf\n", dblval.x);
   printf("Return value: %d\n\n", retval);

   retval = _atoflt(&fltval, str1);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // A non-floating point value: returns 0.
   retval = _atoflt(&fltval, abc);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // Overflow.
   retval = _atoflt(&fltval, oflow);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   return 0;
}
```

```Output
Double value: 3.141593
Return value: 0

Float value: 3.141593
Return value: 0

Float value: 0.000000
Return value: 0

Float value: inf
Return value: 3
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
