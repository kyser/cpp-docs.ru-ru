---
title: Предупреждение (уровень 2) C4285 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4366142c14ec77c1c344312e50e7295c71ca93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4285"></a>Предупреждение компилятора (уровень 2) C4285
Тип возвращаемого значения для «identifier::operator ->» является рекурсивным, если используется инфиксная запись  
  
 Указанный **operator -> ()** функция не может возвращать тип, для которого она определена, или ссылку на тип, в котором они определены.  
  
 Следующий пример приводит к возникновению ошибки C4285:  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```