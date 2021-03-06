---
title: wcrtomb_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcrtomb_s
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
- wcrtomb_s
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a035010c2af49c0d12b4b7f1d6429c66ba9032cc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="wcrtombs"></a>wcrtomb_s

Преобразует расширенный символ в соответствующее представление многобайтового символа. Версия функции [wcrtomb](wcrtomb.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Возвращает записанное число символов или –1 в случае возникновения ошибки.

*mbchar*<br/>
Итоговый преобразованный многобайтовый символ.

*sizeOfmbchar*<br/>
Размер *mbchar* переменной в байтах.

*wchar*<br/>
Расширенный символ для преобразования.

*mbstate*<br/>
Указатель на **mbstate_t** объекта.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль или **errno** значение, если возникает ошибка.

## <a name="remarks"></a>Примечания

**Wcrtomb_s** функция преобразует строку расширенных символов, начиная с указанного преобразования состоянием, содержащимся в *mbstate*, из значения, содержащегося в *wchar*, в представленный адрес *mbchar*. *PReturnValue* значение будет равно числу байт преобразуется, но отсутствуют более **MB_CUR_MAX** байт или -1, если произошла ошибка.

Если *mbstate* имеет значение null, внутренний **mbstate_t** используется состояние преобразования. Если символ содержится в *wchar* не имеет соответствующий Многобайтовый символ значение *pReturnValue* равно-1 и функция возвращает **errno** значение **EILSEQ**.

**Wcrtomb_s** функция отличается от [wctomb_s _wctomb_s_l](wctomb-s-wctomb-s-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **wcsrlen** вместо **wcslen**, если в последующем вызове **wcsrtombs_s** были использованы вместо **wcstombs_s**.

В C++ использование этой функции упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Wcrtomb_s** функция является потокобезопасной, при условии, что ни одна из функций в текущем потоке вызывает **setlocale** во время выполнения этой функции и *mbstate* имеет значение null.

## <a name="example"></a>Пример

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
