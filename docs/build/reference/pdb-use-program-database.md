---
title: -PDB (использование базы данных программы) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 776d23c0c0c7ce392b1ff0d7a989c3c5503129b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="pdb-use-program-database"></a>/PDB (Использование базы данных программы)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Пользовательское имя для базы данных программы (PDB), создаваемой компоновщиком. Он заменяет имя по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию когда [/DEBUG](../../build/reference/debug-generate-debug-info.md) указан, компоновщик создает базу данных программы (PDB), содержащий отладочную информацию. Имя файла по умолчанию для PDB-ФАЙЛ имеет базовое имя программы и расширение PDB.  
  
 Используйте/PDB:*filename* для указания имени PDB-файл. Если не задан параметр/debug, / PDB-параметр игнорируется.  
  
 PDB-файл может быть размером до 2 ГБ.  
  
 Дополнительные сведения см. в разделе [PDB-файлы в качестве входных данных компоновщика](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **отладки** страницу свойств.  
  
4.  Изменить **создавать файл базы данных программы** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)