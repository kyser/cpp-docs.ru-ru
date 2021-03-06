---
title: _free_locale | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _free_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __free_locale
- free_locale
- _free_locale
dev_langs:
- C++
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b74725ddd7884bcc714e1048b28c53f201ebe4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="freelocale"></a>_free_locale

Освобождает объект языкового стандарта.

## <a name="syntax"></a>Синтаксис

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*языковой стандарт* объект языкового стандарта для освобождения.

## <a name="remarks"></a>Примечания

**_Free_locale** функция используется, чтобы освободить объект языкового стандарта, полученный из вызова **_get_current_locale** или **_create_locale**.

Предыдущее имя этой функции **__free_locale** (с двух символов подчеркивания) рекомендуется к использованию.

## <a name="requirements"></a>Требования

|**Подпрограммы**|Обязательный заголовок|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
