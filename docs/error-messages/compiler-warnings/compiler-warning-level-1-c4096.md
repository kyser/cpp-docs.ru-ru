---
title: Предупреждение (уровень 1) C4096 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4096
dev_langs:
- C++
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3787ef5482841e33658e02371fa0f6d1682612ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4096"></a>Предупреждение (уровень 1) C4096 компилятора
«»: интерфейс не является COM-интерфейсом; он не будет передан в IDL  
  
 Определение интерфейса, предназначенное для использования в качестве интерфейса COM не был определен как COM-интерфейс и поэтому он не будет передан в IDL-файл.  
  
 В разделе [атрибуты интерфейса](../../windows/interface-attributes.md) список атрибутов, который определяет интерфейс COM-интерфейса.  
  
 Следующий пример приводит к возникновению ошибки C4096:  
  
```  
// C4096.cpp  
// compile with: /W1 /LD  
#include "windows.h"  
[module(name="xx")];  
  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct b : a  
{  
};   // C4096, remove coclass or uncomment object  
```