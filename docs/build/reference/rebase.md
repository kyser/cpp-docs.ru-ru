---
title: -REBASE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a5e2b68768b01d71532c358a14c53d8a033e1ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр задает базовые адреса для указанных файлов. EDITBIN назначает новые базовые адреса в непрерывном адресном пространстве в соответствии с размером каждого файла с округлением до ближайших 64 КБ. Дополнительные сведения о базовых адресов см. в разделе [базовый адрес](../../build/reference/base-base-address.md) (/ BASE) компоновщика.  
  
 Укажите исполняемые файлы и DLL-библиотеки в ее *файлы* аргумент в командной строке EDITBIN в порядке, в котором они будут основаны. При необходимости можно указать один или несколько *модификаторы*, разделяя их запятой (**,**):  
  
|Модификатор|Действие|  
|--------------|------------|  
|BASE **= *** адрес*|Предоставляет начальный адрес для переназначения базовых адресов в файлы. Укажите *адрес* в десятичное или нотации языка. Если BASE не указан, по умолчанию, начиная с базового адреса используется 0x400000. Если используется, БАЗОВОГО СПИСКА должен быть задан, и *адрес* задает конец диапазона базовых адресов.|  
|BASEFILE|Создает файл с именем COFFBASE. TXT, — это текстовый файл в формат, ожидаемый ссылки/BASE параметр.|  
|ВНИЗ|Указывает EDITBIN переназначить базовые адреса вниз от конечного адреса. Файлы будут переданы в порядке, указанном с помощью первый файл, расположенный в наибольший возможный адрес ниже конец диапазона адресов. BASE должен использоваться с вниз для гарантировать достаточное адресное пространство для размещения файлов. Чтобы определить адресное пространство, требуемое для указанных файлов, запустите EDITBIN с параметром/REBASE файлов и добавьте 64 КБ отображается общий размер.|  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)