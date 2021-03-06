---
title: Предупреждение (уровень 4) C4625 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4625
dev_langs:
- C++
helpviewer_keywords:
- C4625
ms.assetid: 4cc99e50-846c-4784-97da-48b977067851
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9279d5a9bfa7aa80ae866d290624f1edf888e36b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4625"></a>Предупреждение компилятора (уровень 4) C4625
"производный класс": не удалось создать конструктор копии, так как конструктор копии для базового класса недоступен или удален  
  
 Конструктор копирования был удален или недоступен для базового класса, поэтому он не был создан для производного класса. Любая попытка создать объект этого типа приведет к ошибке компилятора.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C4625 и приводятся сведения по ее устранению.  
  
```  
// C4625.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4625)  
  
struct A {  
   A() {}  
  
private:  
   A(const A&) {}  
};  
  
struct C : private virtual A {};  
struct B :  C {};   // C4625 no copy constructor  
  
struct D : A {};  
struct E :  D {};   // OK  
```