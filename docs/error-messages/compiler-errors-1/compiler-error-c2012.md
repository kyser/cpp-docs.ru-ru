---
title: Ошибка компилятора C2012 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2012
dev_langs:
- C++
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e52b08d7a7d93682e1750ae545183195fc563734
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2012"></a>Ошибка компилятора C2012
отсутствует имя после "<"  
  
 В директиве `#include` отсутствует требуемое имя файла.  
  
 Следующий пример приводит к возникновению ошибки C2012:  
  
```  
// C2012.cpp  
#include <   // C2012 include the filename to resolve  
```  
  
 Возможное решение  
  
```  
// C2012b.cpp  
// compile with: /c  
#include <stdio.h>  
```