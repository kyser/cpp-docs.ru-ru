---
title: 'Как: включение ресурсов во время компиляции | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 765d78ef5371015fdce3e505e7a2454c29c6c97e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-include-resources-at-compile-time"></a>Практическое руководство. Включение ресурсов во время компиляции
Как правило, удобнее всего работать с заданным по умолчанию размещением всех ресурсов в одном файле описания ресурсов (RC-файле). Тем не менее, добавлением ресурсы в других файлах в текущем проекте во время компиляции, указав их в **директивы времени компиляции** поле [включения ресурсов-диалоговое окно](../windows/resource-includes-dialog-box.md).  
  
 Существует несколько причин размещать ресурсы в отдельном файле, а не в главном RC-файле:  
  
-   Необходимость добавлять комментарии к инструкциям ресурсов, которые не будут удалены при сохранении RC-файла.  
  
     Редакторы ресурсов не читают RC-файл и файл resource.h напрямую. Компилятор ресурсов компилирует их в APS-файлы, используемые редакторами ресурсов. Этот файл представляет собой этап компиляции и содержит только символьные данные. Как и при обычном процессе компиляции, данные, не являющиеся символьными (например комментарии), удаляются во время компиляции. Каждый раз, когда APS-файл теряет синхронность с RC-файлом, RC-файл создается заново (например, при выполнении команды «Сохранить» редактор ресурсов перезаписывает RC-файл и файл resource.h). Любые изменения в самих ресурсах включаются в RC-файл, однако комментарии всегда теряются после перезаписи RC-файла.  
  
-   Необходимость включения ресурсов, которые уже были разработаны и протестированы и не требуют дальнейшего изменения. (Все включенные файлы, не имеющие расширения RC, будут недоступны для изменения с помощью редакторов ресурсов.)  
  
-   Необходимость включения ресурсов, которые используются в нескольких разных проектах или входят в систему управления версиями исходного кода и поэтому должны находиться в центральном расположении, где изменения будут применяться ко всем проектам.  
  
-   Необходимость включения ресурсов (например, ресурсов RCDATA) в нестандартном формате. Ресурсы RCDATA могут иметь особые требования. Например, нельзя использовать выражение как значение для поля nameID. Дополнительные сведения см. в документации по [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 При наличии разделов в существующих RC-файлах, удовлетворяющих любому из этих условий, следует поместить эти разделы в один или несколько отдельных RC-файлов и включить их в проект с помощью [включения ресурсов-диалоговое окно](../windows/resource-includes-dialog-box.md). *Projectname*для этой цели используется файл .rc2, создаваемый в подкаталоге "\res" нового проекта.  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>Включение ресурсов в проект во время компиляции  
  
1.  Поместите ресурсы в файл описания ресурсов с уникальным именем. Не используйте *projectname*.rc, так как это имя файла используется для главного файла описания ресурсов.  
  
2.  Щелкните правой кнопкой мыши RC-файл (в [представление ресурсов](../windows/resource-view-window.md)) и выберите **включения ресурсов** в контекстном меню.  
  
3.  В **директивы времени компиляции** добавьте [#include](../preprocessor/hash-include-directive-c-cpp.md) директивы компилятора, чтобы включить новый файл ресурсов в главный файл ресурсов в среде разработки.  
  
     Ресурсы, содержащиеся в файлах, включенных таким способом, становятся частью исполняемого файла во время компиляции. Они недоступны для изменения непосредственно при работе над главным RC-файлом проекта. При необходимости следует открывать RC-файлы отдельно. Все включенные файлы, не имеющие расширения RC, будут недоступны для изменения с помощью редакторов ресурсов.  
  

  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)