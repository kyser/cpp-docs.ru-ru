---
title: Предупреждение (уровень 2) C4094 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9deae6a0e21fcb7dd4f09de07e65445dc9595932
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4094"></a>Предупреждение (уровень 2) C4094 компилятора
без тега «лексема» не объявлены символы  
  
 Компилятор обнаружил пустое объявление с помощью непомеченный структуры, объединения или класса. Объявление учитывается.  
  
## <a name="example"></a>Пример  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 Это условие приведет к ошибке в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).