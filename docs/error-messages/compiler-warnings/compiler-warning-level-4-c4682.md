---
title: Предупреждение компилятора предупреждение (уровень 4) C4682 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076e8de6cbffa1f531cec875fd682a1daee42e74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4682"></a>Предупреждение компилятора (уровень 4) C4682
"параметр": не указан атрибут параметра направления, по умолчанию принимается [in]  
  
 Метод параметра в интерфейсе с атрибутами не содержит атрибута направления [in](../../windows/in-cpp.md) или [out](../../windows/out-cpp.md). По умолчанию принимается атрибут in.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Следующий пример приводит к возникновению предупреждения C4682:  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```