---
title: Предупреждение (уровень 4) C4242 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: befe02b363c17a670d3b33632ffa50ed8a7cb1f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4242"></a>Предупреждение компилятора (уровень 4) C4242
«Идентификатор»: преобразование из «тип1» в «тип2», возможна потеря данных  
  
 Типы различны. Преобразование типов может привести к потере данных. Компилятор выполняет преобразование типа.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Дополнительные сведения об ошибке C4242 см. в разделе [типичные ошибки компилятора](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Следующий пример приводит к возникновению ошибки C4242:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```