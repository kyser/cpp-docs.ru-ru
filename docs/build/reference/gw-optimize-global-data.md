---
title: -Gw (оптимизация глобальных данных) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Gw
dev_langs:
- C++
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 173b9499477ee02cbb1f052d3d85445a9ffb7732
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="gw-optimize-global-data"></a>/Gw (оптимизация глобальных данных)
Данные пакета в разделах COMDAT для оптимизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Gw[-]  
```  
  
## <a name="remarks"></a>Примечания  
 **/Gw** параметр указывает компилятору на необходимость пакета глобальных данных в отдельных разделах COMDAT. По умолчанию **/Gw** отключено и должно быть явно включено. Чтобы явно отключить его, используйте **/Gw-**. Если оба **/Gw** и [/GL](../../build/reference/gl-whole-program-optimization.md) являются включен, компоновщик использует оптимизации всей программы для сравнения COMDAT разделы в нескольких файлах объекта, чтобы исключить неиспользуемые глобальные данные или для слияния идентичные только для чтения глобальные данные. Это может значительно снизить объем выходной двоичный исполняемый файл.  
  
 Компиляция и компоновка выполняются отдельно, можно использовать [/OPT: ref](../../build/reference/opt-optimizations.md) компоновщика, чтобы исключить из исполняемого файла, скомпилированного неиспользуемые глобальные данные в объектных файлах с **/Gw** параметр.  
  
 Можно также использовать [/OPT: ICF](../../build/reference/opt-optimizations.md) и [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) параметры компоновщика для слияния в любой идентичные только для чтения глобальных данных в нескольких файлах объекта скомпилирована в исполняемый файл **/Gw** параметр.  
  
 Дополнительные сведения см. в разделе [введение /Gw переключатель компилятора](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) блоге группы разработчиков Visual C++.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Изменить **Дополнительные параметры** включив **/Gw** и выберите **ОК**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)