---
title: Ошибка компилятора C3740 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3740
dev_langs:
- C++
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53004e1a26fc0ead32680ac9b37b2e9aaa13087e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3740"></a>Ошибка компилятора C3740
шаблоны не источниками или приемниками событий  
  
 Класс-шаблон или структура не могут содержать [события](../../cpp/event-handling.md).  
  
 Следующий пример приводит к возникновению ошибки C3740:  
  
```  
// C3740.cpp  
template <typename T>   // Delete the template specification  
struct E {  
   __event void f();   // C3740  
};  
  
int main() {  
}  
```