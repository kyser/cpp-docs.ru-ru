---
title: Ошибка компилятора C2383 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81624ccd7f4857cb2f7d8474d393a9743ab1a2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2383"></a>Ошибка компилятора C2383
"*символ*": аргументы по умолчанию не разрешены для этого символа  
  
 Компилятор C++ не допускает аргументы по умолчанию для указателей на функции.  
  
 Этот код был принят компилятором Visual C++ в версиях до Visual Studio 2005, но теперь он приводит к ошибке. Для кода, который работает во всех версиях Visual C++ не назначается значение по умолчанию является аргументом указателя на функцию.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2383 и показано возможное решение:  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```