---
title: _endthread, _endthreadex | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4588829b3ec1d348405be925a75c493f4e8594b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

Завершает поток; **_endthread** завершает поток, созданный **_beginthread** и **_endthreadex** завершает поток, созданный **_beginthreadex**.

## <a name="syntax"></a>Синтаксис

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Параметры

*retval* код завершения потока.

## <a name="remarks"></a>Примечания

Можно вызвать **_endthread** или **_endthreadex** явным образом, чтобы завершить поток; Однако **_endthread** или **_endthreadex** вызывается автоматически при возврате потока из процедуры, переданный в качестве параметра для **_beginthread** или **_beginthreadex**. Завершение потока вызовом **endthread** или **_endthreadex** помогает обеспечить правильное восстановление ресурсов, выделяемых для потока.

> [!NOTE]
> Для исполняемого файла, связанного с Libcmt.lib, не следует вызывать функцию [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API Win32. Это помешает системе времени выполнения освобождать выделенные ресурсы. **_endthread** и **_endthreadex** освобождают выделенные ресурсы потока и затем вызвать **ExitThread**.

**_endthread** автоматически закрывает дескриптор потока. (Это поведение отличается от Win32 **ExitThread** API.) Таким образом, при использовании **_beginthread** и **_endthread**, не следует явно закрывать дескриптор потока, вызывая функцию Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API.

Win32, например **ExitThread** API, **_endthreadex** не закрывает дескриптор потока. Таким образом, при использовании **_beginthreadex** и **_endthreadex**, необходимо закрыть дескриптор потока, вызывая функцию Win32 **CloseHandle** API.

> [!NOTE]
> **_endthread** и **_endthreadex** блокируют вызов деструкторов C++, ожидающих в потоке не предназначен для вызова.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Пример

См. пример для [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
