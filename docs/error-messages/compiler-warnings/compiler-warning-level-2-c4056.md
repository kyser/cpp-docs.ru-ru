---
title: Предупреждение (уровень 2) C4056 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf5a5855d0b4291105826679e2ae81ed6d69e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4056"></a>Предупреждение (уровень 2) C4056 компилятора
переполнение в число с плавающей точкой арифметических операциях с константой  
  
 Арифметических операциях с константой с плавающей запятой приводит к возникновению ошибки результат, который превышает максимальное допустимое значение.  
  
 Это предупреждение может быть вызвано оптимизацией компилятора, выполняемой при арифметических операциях с константой. Можно спокойно проигнорировать это предупреждение, если оно исчезает при выключении оптимизации ([/Od](../../build/reference/od-disable-debug.md)).  
  
 Следующий пример приводит к возникновению ошибки C4056:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```