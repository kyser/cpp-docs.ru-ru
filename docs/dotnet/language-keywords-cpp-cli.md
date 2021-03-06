---
title: Ключевые слова языка (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 241205ad25314034d8d36fa7ad1b156b13080fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="language-keywords-ccli"></a>Ключевые слова языка (C++/CLI)
Некоторые ключевые слова языка изменен с управляемых расширений для C++ к Visual C++.  
  
 В новом синтаксисе Visual C++, двойной знак подчеркивания удаляется как префикс из всех ключевых слов (с одним исключением: `__identifier` сохраняется). Например, свойство теперь объявлено как `property`, а не `__property`.  
  
 Обнаружены две основные причины использования префикса двойным подчеркиванием в управляемых расширениях:  
  
-   Это метод conformant определения локальных расширений в стандарте ISO C++. Основной целью при разработке управляемых расширений было не обеспечение совместимости со стандартным языком, например новых ключевых слов и маркеров. Поэтому было в значительной мере определяющих Выбор указатель синтаксис для объявления объектов управляемых ссылочных типов.  
  
-   Двойной знак подчеркивания, отдельно от его аспект совместимые используется также гарантирует того, что не вмешивается в работу с существующей базе кода пользователей языка. Это было второй основной целью при разработке управляемых расширений.  
  
 Несмотря на удаление двух символов подчеркивания, Microsoft остается заявляет, что соответствует стандартам в. Однако поддержка динамической объектной модели CLR представляет новую и эффективную парадигмы программирования. Для поддержки этого нового подхода требуется собственный высокоуровневые ключевых слов и маркеров. Мы пытаются предоставить выражение первого класса новой парадигме при его интеграции и поддержки стандартного языка. Новая структура синтаксиса обеспечивает качественную программирования этих двух разнородных объектных моделей.  
  
 Аналогичным образом мы интересует развертывание не вмешивается в работу характер новых ключевых слов. Этого с помощью контекстные и составные ключевые слова. Прежде чем мы рассмотрим нового синтаксиса языка, попробуем смысл этих разновидностями ключевых слов.  
  
 Контекстное ключевое слово имеет особое значение в различных контекстах программы. В общем контексте программы, например `sealed` рассматривается как обычный идентификатор. Тем не менее при их возникновении в разделе объявления управляемого ссылочного типа класса, он рассматривается как ключевое слово в контексте объявления этого класса. Это сводит к минимуму вероятность неоднозначного введение новое ключевое слово на языке, что-нибудь, мы думаем, очень важно для пользователей с существующего кода. В то же время позволяет пользователям новые функциональные возможности эффективные возможности и функции языка -, недоступные с помощью управляемых расширений. Пример того, как `sealed` используется в разделе [объявления типа управляемого класса](../dotnet/declaration-of-a-managed-class-type.md).  
  
 Составные ключевые слова, такие как `value class`, является особым случаем контекстно-зависимое ключевое слово. Ключевое слово existing группируется с контекстным модификатором, разделенные пробелом. Пара рассматривается как единое целое, а не как два отдельных ключевых слова.  
  
## <a name="see-also"></a>См. также  
 [C + +/ CLI Основы миграции](../dotnet/cpp-cli-migration-primer.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)