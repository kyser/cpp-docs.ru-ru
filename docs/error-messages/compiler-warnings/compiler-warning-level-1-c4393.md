---
title: Предупреждение (уровень 1) C4393 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59a1022f54d22e97a11c0970cad6bcd8918c7190
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4393"></a>Предупреждение компилятора (уровень 1) C4393
«переменная»: const не влияет на данные-член литерала; обрабатывается  
  
 Объект [литерала](../../windows/literal-cpp-component-extensions.md) элемент данных был задан как const.  Так как данные-член литерала подразумевает const, не необходимо добавить к объявлению.  
  
 Следующий пример приводит к возникновению ошибки C4393:  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```