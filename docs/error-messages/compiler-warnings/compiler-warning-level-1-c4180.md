---
title: Предупреждение (уровень 1) C4180 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4180
dev_langs:
- C++
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d038d09adb0ae8072ebb6d78aa3f0630b2ad425
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4180"></a>Предупреждение компилятора (уровень 1) C4180
квалификатор, примененный к типу-функции, не имеет смысла; пропуск  
  
 Квалификатор, например **const**, применен к типу функции, определенному с помощью `typedef`.  
  
## <a name="example"></a>Пример  
  
```  
// C4180.cpp  
// compile with: /W1 /c  
typedef int FuncType(void);  
  
// the const qualifier cannot be applied to the  
// function type FuncType  
const FuncType f;   // C4180  
```