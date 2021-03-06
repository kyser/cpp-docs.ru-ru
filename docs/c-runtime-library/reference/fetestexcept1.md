---
title: fetestexcept | Документы Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0450fcaddf8ca05484d0b2bd122ff006eb8355f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fetestexcept"></a>fetestexcept

Определяет, какие из указанных флагов состояний исключения с плавающей запятой в настоящее время заданы.

## <a name="syntax"></a>Синтаксис

```C
int fetestexcept(
   int excepts
);

```

### <a name="parameters"></a>Параметры

*excepts*<br/>
Побитовая операция ИЛИ для флагов состояний с плавающей запятой, которые требуется проверить.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает битовую маску, содержащую побитовую операцию ИЛИ для макросов исключений с плавающей запятой, которая соответствует установленным в данный момент флагам состояний исключения. Если исключения не заданы, возвращает 0.

## <a name="remarks"></a>Примечания

Чтобы определить исключения, которые были вызваны операцией с плавающей запятой, используйте функцию fetestexcept. Используйте *excepts* параметр, чтобы указать, какие флаги состояния исключения для тестирования. **Fetestexcept** функция использует эти макросы исключений, определенных в \<fenv.h > в *excepts* и возвращаемое значение:

|Макрос исключения|Описание|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

Указанный *excepts* аргумент может иметь значение 0, один из макросов поддерживаемых исключений с плавающей запятой или побитового или из двух или более макросов. Эффект какого-либо другого *excepts* значение аргумента не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
