---
title: Настройка параметров компоновщика | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18728994be3f44152a263fb8a6009728e33a42a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="setting-linker-options"></a>Настройка параметров компоновщика
Можно задать параметры компоновщика, внутри или вне среды разработки. В этом разделе для каждого параметра компоновщика обсуждается, как это можно сделать в среде разработки. В разделе [параметры компоновщика](../../build/reference/linker-options.md) полный список.  
  
 При выполнении ссылки вне среды разработки, можно указать входные данные в один или несколько способов:  
  
-   На [командной строки](../../build/reference/linker-command-line-syntax.md)  
  
-   С помощью [командные файлы](../../build/reference/link-command-files.md)  
  
-   В [переменные среды](../../build/reference/link-environment-variables.md)  
  
 СВЯЗЬ первого обрабатывает параметры, заданные в переменной среды ссылки, следуют параметры в порядке, они были указаны в командной строке и в командных файлах. Если параметр повторяется с разными аргументами, обработанных последнее из них имеет приоритет.  
  
 Параметры применяются ко всей сборке; параметры не могут применяться для определенных входных файлов.  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)