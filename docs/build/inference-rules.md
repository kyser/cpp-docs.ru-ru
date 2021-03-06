---
title: Правила вывода | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2baa4bdd749e7553d052600cc9efe524ec09910d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="inference-rules"></a>Правила вывода
Правила вывода содержат команды для обновления целевых объектов и для вывода объектов, зависящих от целевых объектов. Расширения в правиле вывода соответствуют один целевой объект и зависимых, имеющие такое же базовое имя. Правила вывода пользовательских или предопределенных; предопределенные правила можно переопределять.  
  
 Если устаревшей зависимости не сопоставлены команды и [. СУФФИКСЫ](../build/dot-directives.md) содержит расширение зависимого объекта, NMAKE использует правило, расширения которого соответствуют целевой объект и существующий файл в текущем или указанном каталоге. Если существующие файлы соответствует более чем одному правилу **. СУФФИКСЫ** определяет список, который следует использовать; приоритет в списке понижается слева направо. Если зависимый файл не существует и не указан в качестве цели в другом блоке описания, правило зависимости можно создать отсутствующий зависимый из другого файла с тем же базовым именем. Если целевой блок описания нет зависимых элементов или команды, правило зависимости можно обновить целевой объект. Правила вывода могут построить целевой объект командной строки, даже если блока описания не существует. Программа NMAKE может вызывать правило для выведенного зависимого, даже если указан явного.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Определение правила](../build/defining-a-rule.md)  
  
 [Правила пакетного режима](../build/batch-mode-rules.md)  
  
 [Предварительно определенные правила](../build/predefined-rules.md)  
  
 [Выводимые зависимости и правила](../build/inferred-dependents-and-rules.md)  
  
 [Приоритет правил вывода](../build/precedence-in-inference-rules.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по программе NMAKE](../build/nmake-reference.md)