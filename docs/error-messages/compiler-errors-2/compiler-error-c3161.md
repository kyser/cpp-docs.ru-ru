---
title: Ошибка компилятора C3161 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2d7aff3eb41c03f5be774704922340ac54126fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161
«интерфейс»: вложенный класс, структура, объединение или интерфейс в интерфейсе недопустимы; недопустимо вложение интерфейса в класс, структура или объединение  
  
 [__Interface](../../cpp/interface.md) может появиться только в глобальной области видимости в пределах пространства имен. Класс, структура или объединение не может присутствовать в интерфейсе.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3161.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```