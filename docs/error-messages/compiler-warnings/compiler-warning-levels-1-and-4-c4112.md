---
title: Предупреждение (уровни 1 и 4) C4112 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43718511af0d85f0c9026fe70b4749c4e3d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Предупреждение компилятора (уровни 1 и 4) C4112
\#строки требуется целое число между 1 и числом  
  
 Директива [#Line](../../preprocessor/hash-line-directive-c-cpp.md) указывает целочисленный параметр, который не входит в допустимый диапазон.  
  
 Если указанный параметр имеет значение меньше 1, счетчик строк сбрасывается до 1. Если указанный параметр больше, чем *номер*, представляющий определенный компилятором предел, то счетчик строк не изменяется. Это предупреждение уровня 1 в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение уровня 4 в расширениях Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C4112:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```