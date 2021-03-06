---
title: strcmp, wcscmp, _mbscmp | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df2168da257c6d1d07cff6400122830da60b5fef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp

Сравнивают строки.

> [!IMPORTANT]
> **_mbscmp** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
```

### <a name="parameters"></a>Параметры

*string1*, *строка2*<br/>
Строки с завершающим нулем для сравнения.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение для каждого из этих функций отображает порядковое отношение из *string1* для *string2*.

|Значение|Отношение string1 к string2|
|-----------|----------------------------------------|
|< 0|*string1* — меньше, чем *строка2*|
|0|*string1* идентична *строка2*|
|> 0|*string1* больше, чем *строка2*|

При ошибке проверки параметра **_mbscmp** возвращает **_NLSCMPERROR**, которая определена в \<string.h > и \<mbstring.h >.

## <a name="remarks"></a>Примечания

**Strcmp** функция выполняет порядковое сравнение *string1* и *string2* и возвращает значение, которое показывает их связь. **wcscmp** и **_mbscmp** представляют, соответственно, версии Юникода и многобайтовых символов **strcmp**. **_mbscmp** распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает **_NLSCMPERROR** при возникновении ошибки. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). Кроме того Если *string1* или *string2* является пустым указателем, **_mbscmp** вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_mbscmp** возвращает **_NLSCMPERROR** и задает **errno** для **EINVAL**. **strcmp** и **wcscmp** не проверяют свои параметры. В остальном эти три функции ведут себя идентично.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

**Strcmp** функции отличаются от **strcoll** функции в том, что **strcmp** сравнения является порядковым и не зависит от языкового стандарта. **strcoll** сравнивает строки лексикографически с помощью **LC_COLLATE** категории текущего языкового стандарта. Дополнительные сведения о **LC_COLLATE** категории, в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md).

В языковом стандарте "C" порядок символов в наборе символов (набор символов ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу ä (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.

Языки, для которых отличаются символов в наборе и лексикографическим порядком символов, можно использовать **strcoll** вместо **strcmp** для лексикографического сравнения строк. Кроме того, можно использовать **strxfrm** на исходные строки, а затем использовать **strcmp** для результирующих строк.

**Strcmp** функции чувствительны к регистру. **_stricmp**, **_wcsicmp**, и **_mbsicmp** сравнения строк с первой их преобразования в нижний регистр. Две строки, содержащие символы, которые расположены между «Z» и «» в таблице ASCII ("[«,»\\", "]", "^", «_» и "\`") сравниваются по-разному, в зависимости от их регистра. Например, две строки «ABCDE» и «ABCD ^» сравниваются с одним из способов, если сравнение производится в нижнем регистре («abcde» > «abcd ^») и с другим («ABCDE» <» ABCD ^») Если сравнение производится в верхнем регистре.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strcmp**|<string.h>|
|**wcscmp**|<string.h> или <wchar.h>|
|**_mbscmp**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
