---
title: "-WHOLEARCHIVE (Включить всех объектных файлах библиотеки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed12541eeb0c85b2d218a7a5f3305413d4dc2ec8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (включает все файлы библиотеки объектов)
Заставляет компоновщик включать в статической библиотеки в скомпонованный исполняемый всех объектных файлах.  
  
## <a name="syntax"></a>Синтаксис  
  
> / WHOLEARCHIVE [:*библиотеки*]  
  
## <a name="remarks"></a>Примечания  
  
Параметр /WHOLEARCHIVE заставляет компоновщик включать каждого файла объекта из любой указанной статической библиотеки, или если нет библиотеки не указан, из всех статических библиотек, указанных в ссылку команд. Для указания параметра /WHOLEARCHIVE для нескольких библиотек, можно использовать более одного /WHOLEARCHIVE переключиться в командной строке компоновщика. По умолчанию компоновщик включает объектные файлы в связанных выходных данных только в том случае, если они экспортировать символы, которые ссылаются файлы других объектов в исполняемом файле. Параметр /WHOLEARCHIVE делает компоновщик обрабатывать всех объектных файлах архива в статическую библиотеку, как если бы они были заданы отдельно, в командной строке компоновщика.  
  
Повторный экспорт все символы из статической библиотеки можно использовать параметр /WHOLEARCHIVE. Это позволяет убедиться, что все библиотеки кода, ресурсы и метаданные включаются при создании компонента из более чем одной статической библиотеки. Если появится предупреждение LNK4264 при создании статической библиотеки, которая содержит компоненты среды выполнения Windows для экспорта, параметр /WHOLEARCHIVE при компоновке этой библиотеки в другую компонента или приложения.  
  
Параметр /WHOLEARCHIVE впервые появился в Visual Studio 2015 с обновлением 2.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
1.  Выберите **командной строки** страница свойств под **свойства конфигурации**, **компоновщика**.  
  
1.  Добавьте параметр /WHOLEARCHIVE **Дополнительные параметры** текстовое поле.  
  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)