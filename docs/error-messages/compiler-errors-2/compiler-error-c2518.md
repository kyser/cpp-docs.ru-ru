---
title: Ошибка компилятора C2518 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2518
dev_langs:
- C++
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1e44a99ad49945e441e1560f296dc66568ae3f3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2518"></a>Ошибка компилятора C2518
Ключевое слово «ключевое_слово» в списке базовых классов; обрабатывается  
  
 Ключевые слова `class` и `struct` не должны отображаться в списке базовых классов.  
  
 Следующий пример приводит к возникновению ошибки C2518:  
  
```  
// C2518.cpp  
// compile with: /c  
class B {};  
class C : public class B {};   // C2518  
class D: public B {};   // OK  
```