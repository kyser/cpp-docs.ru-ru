---
title: -VERBOSE (Печать сообщений о ходе выполнения) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1bf99cdf27e432bf8bdf6b7c0e48a84aeaac21
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (печать сообщений о ходе выполнения)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>Примечания  
 Компоновщик отправляет сведения о ходе выполнения сеанса компоновки для **вывода** окна. В командной строке данные отправляются в стандартный вывод и могут быть перенаправлены в файл.  
  
|Параметр|Описание|  
|------------|-----------------|  
|/VERBOSE|Отображает подробные сведения о процессе компоновки.|  
|/ VERBOSE: ICF|Отображает сведения о действиях компоновщика, полученный в результате применения [/OPT: ICF](../../build/reference/opt-optimizations.md).|  
|/ VERBOSE: INCR|Отображает сведения о процессе инкрементной компоновки.|  
|/ VERBOSE: LIB|Отображает сообщения о ходе выполнения, которые указывают только библиотек при поиске.<br /><br /> Отображаемые сведения включает процесс поиска библиотеки и списки каждой библиотеки и имя объекта (с указанием полного пути), символ, разрешаемый из библиотеки и список объектов, которые ссылаются на этот символ.|  
|/ VERBOSE: REF|Отображает сведения о действиях компоновщика, полученный в результате применения [/OPT: ref](../../build/reference/opt-optimizations.md).|  
|/ VERBOSE: SAFESEH|Отображает сведения о модулях, которые не совместимы с безопасной обработки при исключений [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) не указан.|  
|/ VERBOSE: UNUSEDLIBS|Отображает сведения обо всех файлах библиотеки, которые не используются при создании образа.|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Разверните **компоновщика** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Параметр, чтобы добавить **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)