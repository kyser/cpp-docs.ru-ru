---
title: Включение имен файлов в кавычках | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80f6afbc503b52d1ef620050bf5592eb84e75fa9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="including-quoted-filenames"></a>Включение имен файлов в кавычках
**ANSI 3.8.2** Поддержка заключенных в кавычки имен для включаемых файлов исходного кода  
  
 Если указана полная и неоднозначная спецификация пути для включаемого файла между двумя наборами двойных кавычек (" "), препроцессор ищет только спецификацию пути и игнорирует стандартные каталоги.  
  
 Для включаемых файлов, заданных в виде [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", поиск по каталогам начинается с каталога родительского файла и продолжается по каталогам всех прародительских файлов. Таким образом, поиск начинается относительно каталога, который содержит обрабатываемый в настоящее время файл исходного кода. Если отсутствует файл "прародителя" и файл не найден, поиск продолжается, как если бы имя файла было включено в угловые скобки.  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)