---
title: Ошибка компилятора C3360 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3360
dev_langs:
- C++
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8e361b81a2b61f2695a9d47dbcca39bec367bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3360"></a>Ошибка компилятора C3360
"строка": невозможно создать имя  
  
 Значение, переданное в атрибут [uuid](../../windows/uuid-cpp-attributes.md) , недопустимо.  
  
 При компиляции следующего примера возникнет ошибка C3360:  
  
```  
// C3360.cpp  
[ uuid("1") ]  
// try this line instead  
// [ uuid("12341234-1234-1234-1234-123412341234") ]  
struct A   // C3360  
{  
};  
  
int main()  
{  
}  
```