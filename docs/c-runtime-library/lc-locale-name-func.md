---
title: ___lc_locale_name_func | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a88a518483e9ea668b98b054453e7f449e99048b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func
Внутренняя функция CRT. Получает имя текущего языкового стандарта потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, которая содержит имя текущего языкового стандарта потока.  
  
## <a name="remarks"></a>Примечания  
 `___lc_locale_name_func` — это внутренняя функция CRT, которая используется другими функциями CRT для получения текущего языкового стандарта из локального хранилища потока для данных CRT. Эти сведения можно также получить с помощью функции [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) или функций [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске. Мы не рекомендуем использовать их в коде.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`___lc_locale_name_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>См. также  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)