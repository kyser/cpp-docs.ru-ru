---
title: Ошибка компилятора C2598 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2598
dev_langs:
- C++
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb41e0072f319c701f5f0cf13670a5f8f7051a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2598"></a>Ошибка компилятора C2598
компоновки должен определяться в глобальной области видимости  
  
 Спецификатор компоновки объявляется в локальной области видимости.  
  
 Следующий пример приводит к возникновению ошибки C2598:  
  
```  
// C2598.cpp  
// compile with: /c  
void func() {  
   extern "C" int func2();   // C2598  
}  
  
extern "C" int func( int i );  
```