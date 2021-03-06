---
title: clock | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- clock
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4caf2518de21a938822e443c0383c22cf170d44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="clock"></a>часы

Вычисляет реальное прошедшее время для процесса.

## <a name="syntax"></a>Синтаксис

```C
clock_t clock( void );
```

## <a name="return-value"></a>Возвращаемое значение

Измеряется время, прошедшее с момента инициализацию CRT в начале процесса, **CLOCKS_PER_SEC** единиц в секунду. Если время, прошедшее недоступен или превысило максимальное положительное время, которое может быть записано как **clock_t** тип, функция возвращает значение `(clock_t)(-1)`.

## <a name="remarks"></a>Примечания

**Часы** функция сообщает, сколько физическое время, истекшее с момента с инициализацию CRT, во время запуска процесса. Обратите внимание на то, что эта функция не является строго соответствующей стандарту ISO C, который определяет возвращаемое значение как чистое время ЦП. Чтобы получить время ЦП, используйте функцию [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) Win32. Чтобы определить общее затраченное время в секундах, разделите значение, возвращаемое **часы** функция макрос **CLOCKS_PER_SEC**.

При достаточном времени значение, возвращаемое **часы** может превысить максимальное положительное значение **clock_t**. Если процесс выполнения больше, значение, возвращаемое **часы** всегда `(clock_t)(-1)`, в соответствии со стандартом ISO C99 (7.23.2.1) и стандарту ISO C11 (7.27.2.1). Корпорация Майкрософт реализует **clock_t** как **длинные**, 32-разрядное целое число со знаком и **CLOCKS_PER_SEC** определен макрос 1000. Это дает более **часы** функцию возвращаемое значение 2 147 483,647 секунд или около 24.8 дней. Не следует полагаться на значение, возвращаемое **часы** процессы выполняются дольше указанного периода времени. Можно использовать 64-разрядных [время](time-time32-time64.md) функции или Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904) функцию для записей затраченное время многих лет.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**часы**|\<time.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_clock.c
// This sample uses clock() to 'sleep' for three
// seconds, then determines how long it takes
// to execute an empty loop 600000000 times.

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Pauses for a specified number of milliseconds.
void do_sleep( clock_t wait )
{
   clock_t goal;
   goal = wait + clock();
   while( goal > clock() )
      ;
}

const long num_loops = 600000000L;

int main( void )
{
   long    i = num_loops;
   clock_t start, finish;
   double  duration;

   // Delay for a specified time.
   printf( "Delay for three seconds\n" );
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );
   printf( "Done!\n" );

   // Measure the duration of an event.
   start = clock();
   while( i-- )
      ;
   finish = clock();
   duration = (double)(finish - start) / CLOCKS_PER_SEC;
   printf( "Time to do %ld empty loops is ", num_loops );
   printf( "%2.3f seconds\n", duration );
}
```

```Output
Delay for three seconds
Done!
Time to do 600000000 empty loops is 1.354 seconds
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[difftime, _difftime32, _difftime64](difftime-difftime32-difftime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
