---
title: Предупреждение (уровень 2) C4309 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4309
dev_langs:
- C++
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cb98faf0c84210deb1a4c5164959d2ba4c08db9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4309"></a>Предупреждение компилятора (уровень 2) C4309
«Преобразование»: усечение константного значения  
  
 Преобразование типа создает константу превышает объем, выделенный. Может потребоваться использовать больший тип константы.  
  
 Следующий пример приводит к возникновению ошибки C4309:  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```