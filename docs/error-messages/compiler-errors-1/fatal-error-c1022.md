---
title: Неустранимая ошибка C1022 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1022
dev_langs:
- C++
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4a6ec241a9a8e175d542b1f3b9db9ea1cdc3ba0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1022"></a>Неустранимая ошибка C1022
непредвиденный #endif  
  
 Директива `#if`, `#ifdef`или `#ifndef` не имеет соответствующей директивы `#endif` . Убедитесь, что каждая директива `#if`, `#ifdef`или `#ifndef` имеет соответствующую директиву `#endif`.  
  
 В следующем примере возникает ошибка C1022:  
  
```  
// C1022.cpp  
#define true 1  
  
#if (true)  
#else   
#else    // C1022  
```  
  
 Возможное решение  
  
```  
// C1022b.cpp  
// compile with: /c  
#define true 1  
  
#if (true)  
#else   
#endif  
```