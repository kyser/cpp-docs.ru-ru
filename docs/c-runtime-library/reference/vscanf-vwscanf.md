---
title: vscanf, vwscanf | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vscanf
- vwscanf
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
apitype: DLLExport
f1_keywords:
- vscanf
- vwscanf
- _vtscanf
dev_langs:
- C++
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825d0d61fccc6d0f83ae8b11648a3c7a3a9c50a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="vscanf-vwscanf"></a>vscanf, vwscanf

Считывает отформатированные данные из стандартного входного потока. Существуют более безопасные версии этих функций; см. раздел [vscanf_s, vwscanf_s](vscanf-s-vwscanf-s.md).

## <a name="syntax"></a>Синтаксис

```C
int vscanf(
   const char *format,
   va_list arglist
);
int vwscanf(
   const wchar_t *format,
   va_list arglist
);

```

### <a name="parameters"></a>Параметры

*format*<br/>
Строка управления форматированием.

*arglist*<br/>
Список аргументов переменных.

## <a name="return-value"></a>Возвращаемое значение

Возвращает количество успешно преобразованных и назначенных полей. Возвращаемое значение не включает поля, которые были прочитаны, но не были назначены. Возвращаемое значение 0 указывает, что поля не были назначены.

Если *формат* — **NULL** вызывается указатель, обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EOF** и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Vscanf** функция считывает данные из стандартного входного потока **stdin** и записывает данные в местоположения, которые определяются *arglist* список аргументов. Каждый аргумент в списке должен быть указателем на переменную типа, соответствующий спецификатору типа в *формат*. Если копирование производится между перекрывающимися строками, поведение не определено.

> [!IMPORTANT]
> При использовании **vscanf** Чтобы выполнить чтение строки, всегда указывайте ширину для **%s** формат (например, **«% 32s»** вместо **«%s»**); в противном случае неправильного формата входных данных может привести к переполнению буфера. В качестве альтернативы можно использовать [vscanf_s vwscanf_s](vscanf-s-vwscanf-s.md) или [fgets](fgets-fgetws.md).

**vwscanf** — это двухбайтовая версия **vscanf**; *формат* аргумент **vwscanf** представляет собой строку расширенных символов. **vwscanf** и **vscanf** ведут себя одинаково, если поток открыт в режиме ANSI. **vscanf** не поддерживает входные данные из потока ЮНИКОДА.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf**|**vscanf**|**vscanf**|**vwscanf**|

Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**vscanf**|\<stdio.h>|
|**vwscanf**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_vscanf.c
// compile with: /W3
// This program uses the vscanf and vwscanf functions
// to read formatted input.

#include <stdio.h>
#include <stdarg.h>

int call_vscanf(char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vscanf(format, arglist);
    va_end(arglist);
    return result;
}

int call_vwscanf(wchar_t *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vwscanf(format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    int   i, result;
    float fp;
    char  c, s[81];
    wchar_t wc, ws[81];
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );
    printf( "The number of fields input is %d\n", result );
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );
    wprintf( L"The number of fields input is %d\n", result );
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}

```

```Output

      71 98.6 h z Byte characters
36 92.3 y n Wide charactersThe number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vscanf_s, vwscanf_s](vscanf-s-vwscanf-s.md)<br/>
