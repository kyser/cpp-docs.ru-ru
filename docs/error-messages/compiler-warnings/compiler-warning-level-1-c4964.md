---
title: Предупреждение (уровень 1) C4964 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98226b2da465d2301356939273d370d76edcb64e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4964"></a>Предупреждение компилятора (уровень 1) C4964
Параметры оптимизации не указаны; сведения о профиле не будут собраны.  
  
 [/GL](../../build/reference/gl-whole-program-optimization.md) и [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) были указаны, но оптимизация не потребовалось, так что никаких PGC-файлов будет создаваться и, таким образом, нет профильной оптимизации невозможны.  
  
 Если нужно, чтобы PGC-файлы создаются при запуске приложения, укажите один из [/o](../../build/reference/o-options-optimize-code.md) параметры компилятора.  
  
 Следующий пример приводит к возникновению ошибки C4964:  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```