---
title: -HIGHENTROPYVA (поддержка 64-разрядную Технологию) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de2487cbeff97ded6e95a36393fbbcfbd510e6d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR)
Указывает, что исполняемый образ использует 64-разрядную технологию ASLR с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию параметр /HIGHENTROPYVA включен для 64-разрядных исполняемых образов. Он неприменим к 64-разрядным исполняемым образам. Для включения этого параметра нужно включить /DYNAMICBASE.  
  
 Параметр /HIGHENTROPYVA изменяет заголовок DLL- или EXE-файла, указывая, поддерживается ли ASLR с 64-разрядными адресами. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **командной строки** страницу свойств.  
  
5.  В **Дополнительные параметры**, введите `/HIGHENTROPYVA` или `/HIGHENTROPYVA:NO`.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)