---
title: -PDBSTRIPPED (Удалить закрытые символы) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs:
- C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 331e490512afe8e9267eb1d0d370cbcf99aa99aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (удалить закрытые символы)
```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *pdb_file_name*  
 Пользовательское имя для базы данных программы (PDB), создаваемой компоновщиком.  
  
## <a name="remarks"></a>Примечания  
 Параметр/PDBSTRIPPED создает второй файл базы данных (PDB) программы при построении образа программы с любыми параметрами компилятора или компоновщика, создающими PDB-файл ([/DEBUG](../../build/reference/debug-generate-debug-info.md), [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), /Zd или /Zi). Второй PDB-файл не содержит символов, которые нежелательно передавать клиентам. Второй PDB-файл будет содержать только:  
  
-   Открытые символы  
  
-   Список объектных файлов и частей исполняемого файла, к которым они относятся  
  
-   Записи оптимизации указателя фрейма (FPO) отладки используется для прохода по стеку  
  
 Очищенный PDB-файл не будет содержать:  
  
-   Сведения о типе  
  
-   Сведения о номерах строк  
  
-   Символы CodeView файл на объект такие функции, локальные переменные и статические данные  
  
 Полный PDB-файл будет создаваться при использовании/PDBSTRIPPED.  
  
 Если не создать PDB-файл, / PDBSTRIPPED игнорируется.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **отладки** страницу свойств.  
  
4.  Изменить **удалить закрытые символы** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)