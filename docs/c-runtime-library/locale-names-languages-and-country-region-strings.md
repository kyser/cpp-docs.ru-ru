---
title: Строки имени языкового стандарта, языка и страны и региона | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeaeb21dfabac173b639fe4b3e1518b276c629a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="locale-names-languages-and-countryregion-strings"></a>Строки имени языкового стандарта, языка и страны и региона
Аргумент*Языковой стандарт* для функций `setlocale` и `_create_locale` можно задать путем использования имен языкового стандарта, языков, кодов страны или региона и кодовых страниц, которые поддерживаются API многоязыковой поддержки Windows. Аргумент *locale* принимает следующую форму:  
  
> *locale* :: "*locale_name*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "*language*\[\_*country-region*]\[.*code_page*]]"  
&nbsp;&nbsp;&nbsp;&nbsp;| ".*code_page*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "C"  
&nbsp;&nbsp;&nbsp;&nbsp;| ""  
&nbsp;&nbsp;&nbsp;&nbsp;| NULL  
  
 Форма имени языкового стандарта, например `en-US` для английского языка (США) или `bs-Cyrl-BA` для боснийского (кириллица, Босния и Герцеговина), является предпочтительной. Набор имен языковых стандартов описан в разделе [Имена языковых стандартов](http://msdn.microsoft.com/library/windows/desktop/dd373814.aspx). Список поддерживаемых имен языковых стандартов по версиям операционной системы Windows см. в столбце **Название языка и региональных параметров** в [Справочнике по API многоязыковой поддержки](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Этот список ресурсов включает в себя поддерживаемый язык, скрипт и региональные части имен языковых стандартов. Дополнительные сведения о поддерживаемых именах языковых стандартов, имеющих порядок сортировки не по умолчанию, см. в столбце **Имя языкового стандарта** в разделе [Идентификаторы порядка сортировки](http://msdn.microsoft.com/library/windows/desktop/dd374060.aspx). Дополнительные сведения о поддержке языков и расположений по версии операционной системы Windows см. в [приложении A: поведение продуктов](http://msdn.microsoft.com/goglobal/bb896001.aspx) в статье [MS-LCID]: Windows Language Code Identifier (LCID) Reference ([MS-LCID]: справочник по коду языка Windows). В версии Windows 10 или более поздней допускаются имена языкового стандарта, соответствующие допустимым тегам языка BCP-47. Например, `jp-US` является допустимым тегом BCP-47, однако он работает только для функциональных возможностей языкового стандарта `US`.  
  
 Форма *language*[*_country_region*[.*code_page*]] сохраняется в параметре языкового стандарта для категории, когда строка с названием языка или строка с названием языка и строка страны или региона используются для создания языкового стандарта. Набор поддерживаемых строк с названием языка описан в разделе [Language Strings](../c-runtime-library/language-strings.md), а список поддерживаемых строк страны или региона представлен в разделе [Country/Region Strings](../c-runtime-library/country-region-strings.md). Если указанный язык не связан с указанной страной или регионом, язык по умолчанию для указанной страны или региона сохраняется в параметре языкового стандарта. Не рекомендуется использовать эту форму для строк с языкового стандарта, внедренных в коде или сериализованных в хранилище, поскольку эти строки чаще подвержены изменениям при обновлении операционной системы, чем форма имени языкового стандарта.  
  
 Кодовой страницей является кодовая страница ANSI/OEM, связанная с этим языковым стандартом. Кодовая страница определяется автоматически при указании языкового стандарта с помощью языка или с помощью языка и страны или региона по отдельности. Особое значение `.ACP` определяет кодовую страницу ANSI для страны или региона. Особое значение `.OCP` определяет кодовую страницу OEM для страны или региона. Например, если указать `"Greek_Greece.ACP"` в качестве языкового стандарта, языковой стандарт сохранится как `Greek_Greece.1253` (кодовая страница ANSI для греческого), а если в качестве языкового стандарта указать `"Greek_Greece.OCP"` , он сохранится как `Greek_Greece.737` (кодовая страница OEM для греческого). Дополнительные сведения о кодовых страницах см. в разделе [Code Pages](../c-runtime-library/code-pages.md). Список поддерживаемых кодовых страниц в Windows см. в разделе [Идентификаторы кодовой страницы](http://msdn.microsoft.com/library/windows/desktop/dd317756.aspx).  
  
 Если кодовая страница используется только для определения языкового стандарта, используются язык и страна или регион системы по умолчанию. Например, если указать `".1254"` (ANSI — турецкий) как языковой стандарт в системе, которая настроена на использование английского (США), сохранится языковой стандарт `English_United States.1254`. Не рекомендуется использовать эту форму, поскольку это может привести к нестабильному поведению.  
  
Значение аргумента *locale* `C` задает минимальную подходящую среду ANSI для преобразования C. Языковой стандарт `C` предполагает, что все типы данных `char` соответствуют 1 байту, а их значение всегда меньше 256. Если аргумент *locale* указывает на пустую строку, языковой стандарт соответствует исходной среде, определенной реализацией.  
  
Можно указать все категории языкового стандарта одновременно для функций `setlocale` и `_wsetlocale` с помощью категории `LC_ALL` . Всем категориям можно задать тот же языковой стандарт, также можно задать каждую категорию по отдельности с помощью аргумента языкового стандарта, имеющего следующую форму:  
  
> LC_ALL_specifier :: locale  
&nbsp;&nbsp;&nbsp;&nbsp;| [LC_COLLATE=locale][;LC_CTYPE=locale][;LC_MONETARY=locale][;LC_NUMERIC=locale][;LC_TIME=locale]  
  
Можно задать несколько типов категорий с разделением точкой с запятой. Типы категорий, которые не заданы, используют текущий параметр языкового стандарта. Например, этот фрагмент кода задает текущий языковой стандарт для всех категорий `de-DE`, а затем задает категории `LC_MONETARY` для `en-GB` и `LC_TIME` для `es-ES`:  
  
```C  
_wsetlocale(LC_ALL, L"de-DE");  
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)   
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Строки языка](../c-runtime-library/language-strings.md)   
 [Строки страны и региона](../c-runtime-library/country-region-strings.md)