---
title: _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strnextc
- _mbsnextc_l
- _mbsnextc
- _wcsnextc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strnextc
- tcsnextc
- _mbsnextc_l
- _mbsnextc
- mbsnextc_l
- ftcsnextc
- mbsnextc
- _tcsnextc
- _wcsnextc
- _ftcsnextc
- _strnextc
- wcsnextc
dev_langs:
- C++
helpviewer_keywords:
- _mbsnextc function
- _tcsnextc function
- _wcsnextc function
- tcsnextc function
- strnextc function
- mbsnextc function
- _strnextc function
- _mbsnextc_l function
- mbsnextc_l function
- wcsnextc function
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f759ce9a4617ab0ca8e97ef308508d836b53b742
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="strnextc-wcsnextc-mbsnextc-mbsnextcl"></a>_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l

Находит следующий символ в строке.

> [!IMPORTANT]
> **_mbsnextc** и **_mbsnextc_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _strnextc(
   const char *str
);
unsigned int _wscnextc(
   const wchar_t *str
);
unsigned int _mbsnextc(
   const unsigned char *str
);
unsigned int _mbsnextc_l(
   const unsigned char *str,
   _locale_t locale
);

```

### <a name="parameters"></a>Параметры

*str*<br/>
Исходная строка.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает следующий символ в целочисленное значение *str*.

## <a name="remarks"></a>Примечания

**_Mbsnextc** функция возвращает целочисленное значение следующего многобайтового символа в *str*, без перемещения указатель на строку. **_mbsnextc** распознает последовательности многобайтовых символов в соответствии с [многобайтовой кодовой страницей](../../c-runtime-library/code-pages.md) в настоящий момент.

Если *str* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает значение 0.

**Примечание о безопасности.** Эти функции представляют потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnextc**|**_strnextc**|**_mbsnextc**|**_wcsnextc**|

**_strnextc** и **_wcsnextc** одного байт символа строки и версий строки расширенных символов **_mbsnextc**. **_wcsnextc** возвращает целочисленное значение следующий расширенный символ в *str*; **_strnextc** возвращает целочисленное значение в следующий символ однобайтовый *str*. **_strnextc** и **_wcsnextc** предоставляются только для этого сопоставления и не должны использоваться иным образом. Дополнительные сведения см. в разделах [Использование универсальных текстовых сопоставлений](../../c-runtime-library/using-generic-text-mappings.md) и [Универсальные текстовые сопоставления](../../c-runtime-library/generic-text-mappings.md).

**_mbsnextc_l** идентична за исключением того, что она использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnextc**|\<mbstring.h>|
|**_mbsnextc_l**|\<mbstring.h>|
|**_strnextc**|\<tchar.h>|
|**_wcsnextc**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
