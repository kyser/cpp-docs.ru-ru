---
title: Предупреждение средств компоновщика LNK4221 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4221
dev_langs:
- C++
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8906c4308b8586d5b1312739921f58063e820deb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4221"></a>Предупреждение средств компоновщика LNK4221
Этот файл объекта не определяет любые ранее неопределенные открытые символы, поэтому он не будет использоваться никакими операциями компоновки, обращающимися к этой библиотеке  
  
 Рассмотрим следующие фрагменты кода.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 Чтобы скомпилировать файлы и создать два объектных файлов, запустите **cl /c a.cpp b.cpp** в командной строке. При связывании объектных файлов, запустив **связать/lib /out:test.lib a.obj b.obj**, будет выдано предупреждение LNK4221. Если объекты компоновку с помощью команды **связать/lib /out:test.lib b.obj a.obj**, не будет выведено предупреждение.  
  
 Предупреждающее сообщение не выдается во втором сценарии, поскольку компоновщик действует по принципу последнего обслужен (LIFO). В первом сценарии b.obj обрабатывается раньше a.obj и a.obj имеет никаких новых символов для добавления. Оно указывает компоновщику на необходимость обработать файл a.obj первым, можно избежать предупреждения.  
  
 Распространенной причиной этой ошибки является при двух файлов исходного кода задайте параметр [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md) с тем же именем файла заголовка, указанного в **предварительно скомпилированный заголовочный файл** поля. Распространенной причиной этой проблемы связана с файлом stdafx.h, поскольку по умолчанию stdafx.cpp включается файл stdafx.h и не добавляются новые символы. Если в другом исходном файле включается файл stdafx.h с **/Yc** и связанный OBJ-файл обрабатывается раньше файла stdafx.obj, компоновщик выдает предупреждение LNK4221.  
  
 Один из способов устранения этой проблемы — убедитесь, что для каждого предкомпилированного заголовка, имеется только один исходный файл, включающий его с **/Yc**. Все исходные файлы необходимо использовать предварительно скомпилированные заголовки. Дополнительные сведения об изменении этого параметра см. в разделе [/Yu (использование предкомпилированных заголовков)](../../build/reference/yu-use-precompiled-header-file.md).