---
title: Ошибка компилятора C3354 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3354
dev_langs:
- C++
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b4bcc36580a453932068350f01b53c5f09f2d69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3354"></a>Ошибка компилятора C3354
"функция": функция, используемая для создания делегата, не может иметь тип возврата "тип"  
  
 Следующие типы недопустимы в качестве типов возврата для `delegate`:  
  
-   Указатель на функцию  
  
-   Указатель на член  
  
-   Указатель на функцию-член  
  
-   Ссылка на функцию  
  
-   Ссылка на функцию-член  
  
 В следующем примере возникает ошибка C3354:  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  
