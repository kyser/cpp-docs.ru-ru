---
title: mbstowcs_s, _mbstowcs_s_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f366e01fbaa8da5c0dbc96ff4da324611e132f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l

Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов. Это версии функции [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Количество символов для преобразования.

*wcstr*<br/>
Адрес буфера для результирующей преобразованной строки расширенных символов.

*sizeInWords*<br/>
Размер *wcstr* буфера в словах.

*mbstr*<br/>
Адрес последовательности многобайтовых символов, заканчивающейся нуль-символом.

*count*<br/>
Максимальное число расширенных символов для хранения в *wcstr* буфер, не включая конечное значение null или [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение и **errno**|
|---------------------|------------------------------|
|*wcstr* — **NULL** и *sizeInWords* > 0|**EINVAL**|
|*mbstr* — **значение NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если не *число* — **_TRUNCATE**; см. примечания ниже)|**ERANGE**|
|*wcstr* не **NULL** и *sizeInWords* == 0|**EINVAL**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки и устанавливает **errno** как указано в таблице.

## <a name="remarks"></a>Примечания

**Mbstowcs_s** функция преобразует строку многобайтовых символов, на который указывает *mbstr* в расширенных символов, сохраненных в буфере, на который указывает *wcstr*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился многобайтовый символ null.

- Встретился недопустимый многобайтовый символ.

- Число расширенных символов, сохраненных в *wcstr* буфера равно *число*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *число* имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), затем **mbstowcs_s** преобразование строки в виде будет помещаются в буфер назначения, по-прежнему предоставляя место для значения null Признак конца.

Если **mbstowcs_s** успешно преобразует исходную строку, размер помещаются в расширенных символах преобразованных строки, включая завершающий символ null в  *&#42;pReturnValue* (предоставленный *pReturnValue* не **NULL**). Это происходит, даже если *wcstr* аргумент **NULL** и предоставляет способ определить необходимый размер буфера. Обратите внимание, что если *wcstr* — **NULL**, *число* игнорируется, и *sizeInWords* должно быть равно 0.

Если **mbstowcs_s** встречает недопустимый Многобайтовый символ, он помещает 0  *&#42;pReturnValue*, устанавливающий буфер назначения на пустую строку, задает **errno** для  **EILSEQ**и возвращает **EILSEQ**.

Если последовательности, на который указывает *mbstr* и *wcstr* перекрываются, то поведение **mbstowcs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не перекрываются и что *число* правильно отражает количество преобразуемых многобайтовых символов.

**mbstowcs_s** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_mbstowcs_s_l** идентична за исключением того, что она использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
