---
title: Целевые объекты в нескольких блоках описания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- blocks, multiple description
- multiple description blocks
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b88c98fa3debc7bd5cc6a21d1bc9440e9386b988
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="targets-in-multiple-description-blocks"></a>Целевые объекты в нескольких блоках описания
Чтобы обновить целевой объект в нескольких блоках описания, использующих различные команды, укажите два последовательных двоеточия (:) между целевым и зависимым.  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)