---
title: Ошибка компилятора C3141 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3141
dev_langs:
- C++
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a394fb06fce8f482f42271052a3cf97b3711eaf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3141"></a>Ошибка компилятора C3141
'interface_name': интерфейсы поддерживают только открытое наследование  
  
 Интерфейсы, определенные при [interface (или __interface)](../../cpp/interface.md) ключевое слово поддерживают только открытое наследование.  
  
 Следующий пример приводит к возникновению ошибки C3141:  
  
```  
// C3141.cpp  
__interface IBase {};  
__interface IDerived1 : protected IBase {};  // C3141  
__interface IDerived2 : private IBase {};    // C3141  
```