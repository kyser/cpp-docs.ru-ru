---
title: _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
dev_langs:
- C++
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe2b9c824fcc45eb2d0fda82cd350d3a9435b94
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l

**Функции, относящиеся к кодовой странице 932**

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _ismbchira(
   unsigned int c
);
int _ismbchira_l(
   unsigned int c,
   _locale_t locale
);
int _ismbckata(
   unsigned int c
);
int _ismbckata_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется проверить.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет. Если *c* < = 255 и имеется соответствующий **_ismbb** процедура (например, **_ismbcalnum** соответствует **_ismbbalnum**), Результатом является возвращаемым значением соответствующего **_ismbb** подпрограммы.

## <a name="remarks"></a>Примечания

Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта для их поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

|Подпрограмма|Условие теста (только для кодовой страницы 932)|
|-------------|-------------------------------------------|
|**_ismbchira**|Двухбайтовые символы хирагана: 0x829F < =*c*< = 0x82F1.|
|**_ismbchira_l**|Двухбайтовые символы хирагана: 0x829F < =*c*< = 0x82F1.|
|**_ismbckata**|Катакана двухбайтовых: 0x8340 < =*c*< = 0x8396.|
|**_ismbckata_l**|Катакана двухбайтовых: 0x8340 < =*c*< = 0x8396.|

**Конец раздела для кодовой страницы 932**

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbchira**|\<mbstring.h>|
|**_ismbchira_l**|\<mbstring.h>|
|**_ismbckata**|\<mbstring.h>|
|**_ismbckata_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Подпрограммы _ismbc](../../c-runtime-library/ismbc-routines.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
