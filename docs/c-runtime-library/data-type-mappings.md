---
title: Сопоставления типов данных | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _TXCHAR
- _TUCHAR
- _TINT
- _TSCHAR
- _TCHAR
- TCHAR::H
- TCHAR
- _T
- _TEXT
dev_langs:
- C++
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- TXCHAR type
- _TSCHAR type
- T type
- _TUCHAR type
- _TEXT type
- _T type
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a469ed8b5e6f026eecf5d8df88eee12b0e0fe74
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="data-type-mappings"></a>Сопоставления типов данных
Сопоставления типов данных определяются в TCHAR.H и зависят от того, определена ли в вашей программе константа `_UNICODE` или `_MBCS`.  
  
 Дополнительные сведения см. в разделе [Использование типов данных TCHAR.H с кодом _MBCS](../text/using-tchar-h-data-types-with-mbcs-code.md).  
  
### <a name="generic-text-data-type-mappings"></a>Сопоставления типов данных универсального текста  
  
|Универсальный текст<br /><br /> имя типа данных|SBCS (_UNICODE,<br /><br /> _MBCS не<br /><br /> определен)|_MBCS<br /><br /> определенный|_UNICODE<br /><br /> определенный|  
|--------------------------------------|----------------------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` или `_TEXT`|Не действует (удаляется препроцессором)|Не действует (удаляется препроцессором)|`L` (преобразует следующий символ или строку в аналог в Юникоде)|  
  
## <a name="see-also"></a>См. также  
 [Универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md)   
 [Сопоставления констант и глобальных переменных](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Сопоставления подпрограмм](../c-runtime-library/routine-mappings.md)   
 [Пример программы с использованием универсального текста](../c-runtime-library/a-sample-generic-text-program.md)   
 [Использование универсальных текстовых сопоставлений](../c-runtime-library/using-generic-text-mappings.md)