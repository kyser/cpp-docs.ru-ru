---
title: 'Страницы свойств HLSL: Общие | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cc9a44076999633fd17b049cbcfad75f65eb7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-general"></a>Страницы свойств "HLSL": страница "Общие"
Чтобы настроить следующие свойства компилятор HLSL (fxc.exe), используйте его **Общие** страницу свойств. Сведения о доступе к **Общие** см. на странице свойств в папке HLSL [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Дополнительные каталоги включения**  
 Добавляет один или несколько каталогов в путь включаемых файлов. Используйте точки с запятой для разделения каталогов.  
  
 Это свойство соответствует **/I [путь]** аргумент командной строки.  
  
 **Имя точки входа**  
 Указывает точку входа для шейдера. Значением по умолчанию является **основной**.  
  
 Это свойство соответствует **/E [name]** аргумент командной строки.  
  
 **Отключить оптимизацию**  
 **Да (/ Od)** Отключение оптимизации; в противном случае **нет**. Значением по умолчанию является **Да (/ Od)** для **отладки** конфигураций и **нет** для **выпуска** конфигурации.  
  
 **/Od** аргумент командной строки для компилятора HLSL неявно применяет **/gfp** аргумент командной строки, но выходные данные может не совпадать с выхода, созданная путем передачи оба **/Od**  и **/gfp** аргументы командной строки явным образом.  
  
 **Включить отладочную информацию**  
 **Да (/Zi)** Включение отладочной информации; в противном случае **нет**. Значением по умолчанию является **Да (/Zi)** для **отладки** конфигураций и **нет** для **выпуска** конфигурации.  
  
 **Тип шейдера**  
 Указывает тип шейдера. Различные виды шейдеров реализовывать различные части графического конвейера. Некоторые виды шейдеров доступны только в более последними моделями шейдеров (которого задаются **Shader Model** свойство) — например, вычислительные шейдеры впервые появились в модель шейдера 5.  
  
 Это свойство соответствует **[type]** часть **/T [type] _ [модель]** аргумент командной строки для компилятора HLSL. **Моделями шейдеров** указывает свойство **[модель]** часть аргумента.  
  
 **Модель шейдера**  
 Указывает модель шейдера. Шейдер различных моделей имеют разные возможности. Как правило более последними моделями шейдеров предоставляют расширенные возможности, но требует более современного графического оборудования для выполнения кода шейдера. Некоторые виды шейдеров (которого задаются **построителей текстур** свойства), доступны только в более последними моделями шейдеров — например, вычислительные шейдеры впервые появились в модель шейдера 5.  
  
 Это свойство соответствует **[модель]** часть **/T [type] _ [модель]** аргумент командной строки для компилятора HLSL. **Построителей текстур** указывает свойство **[type]** часть аргумента.  
  
 **Определения препроцессора**  
 Добавляет одно или несколько определений препроцессора для применения в файле исходного кода HLSL. Используйте точки с запятой для разделения определений символов.  
  
 Это свойство соответствует **/D [определения]** аргумент командной строки для компилятора HLSL.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств HLSL](../ide/hlsl-property-pages.md)   
 [Страницы свойств HLSL: Дополнительно](../ide/hlsl-property-pages-advanced.md)   
 [Страницы свойств HLSL: выходные файлы](../ide/hlsl-property-pages-output-files.md)