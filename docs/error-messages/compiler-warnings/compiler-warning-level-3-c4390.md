---
title: Предупреждение (уровень 3) C4390 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d052a1fa6124aa1518cddec00566e14668fe111d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4390"></a>Предупреждение компилятора (уровень 3) C4390
";": обнаружен; пустой управляющий оператор Это правильно?  
  
 После оператора управления, который не содержит инструкции обнаружено точкой с запятой.  
  
 Если C4390 возникает в результате использования макроса, следует использовать [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить предупреждение C4390 в модуль, содержащий макрос.  
  
 Следующий пример приводит к возникновению ошибки C4390:  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```