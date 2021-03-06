---
title: _getdcwd, _wgetdcwd | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getdcwd
- _wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0ccc526b196982402ca3b795276df8c790ad35a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd

Получает полный путь текущей рабочей папки на указанном диске.

## <a name="syntax"></a>Синтаксис

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Параметры

*Диск*<br/>
Неотрицательное целое число, которое определяет диск (0 — диск по умолчанию, 1 — A, 2 — B и т. д.).

Если указанный диск недоступен или невозможно определить тип диска (например, съемный, жесткий, компакт-диск, электронный диск или сетевой диск), вызывается обработчик недопустимых параметров, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md).

*buffer*<br/>
Место хранения для пути или **NULL**.

Если **NULL** указано, эта функция выделяет буфер размером не менее *maxlen* с помощью функции **malloc**и возвращаемое значение **_getdcwd**— это указатель на выделенный буфер. Буфер можно освободить путем вызова **свободного** и передачи ему указателя.

*MaxLen*<br/>
Ненулевое значение, положительное целое число, определяющее максимальную длину пути в символах: **char** для **_getdcwd** и **wchar_t** для **_wgetdcwd**.

Если *maxlen* не больше нуля, обработчик недопустимых параметров, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md), вызывается.

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку, представляющую полный путь текущей рабочей папки на указанном диске, или **NULL**, что указывает на ошибку.

Если *буфера* указывается как **NULL** и недостаточно памяти для выделения *maxlen* символов, возникает ошибка и **errno** — значение **ENOMEM**. Если длина пути, включая завершающий символ null, превышает *maxlen*, возникает ошибка и **errno** равно **ERANGE**. Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Getdcwd** функция возвращает полный путь текущей рабочей папки на указанном диске и сохраняет его в параметре *буфера*. Если текущей рабочей папкой является корневой каталог, строка заканчивается обратной косой чертой (\\). Если текущая рабочая папка находится в каталоге, отличном от корневого, строка заканчивается именем каталога, а не обратной косой чертой.

**_wgetdcwd** — это двухбайтовая версия **_getdcwd**и его *буфера* параметр и возвращаемое значение являются строками с расширенными символами. В противном случае **_wgetdcwd** и **_getdcwd** ведут себя одинаково.

Эта функция потокобезопасна, даже если она зависит от функции **GetFullPathName**, которая сама не потокобезопасна. Однако можно нарушить потокобезопасность, если многопоточное приложение вызывает и эту функцию, и функцию **GetFullPathName**. Дополнительные сведения см. на сайте [Библиотека MSDN](http://go.microsoft.com/fwlink/p/?linkid=150542) , выполнив поиск с запросом **GetFullPathName**.

Версия этой функции с **_nolock** суффикс работает идентично этой функции, за исключением того, что она не потокобезопасна и не защищена от помех со стороны других потоков. Дополнительные сведения см. в разделе [_getdcwd_nolock _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

Когда **_DEBUG** и **_CRTDBG_MAP_ALLOC** определены, при вызове **_getdcwd** и **_wgetdcwd** заменяются вызовами функций для **_getdcwd_dbg** и **_wgetdcwd_dbg** , чтобы выполнить отладку выделения памяти. Дополнительные сведения см. в разделе [_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в разделе [_getdrive](getdrive.md).

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
