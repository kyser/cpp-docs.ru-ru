---
title: Предупреждение (уровень 4) C4634 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4634
dev_langs:
- C++
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b19a4d0cbbb7b2b8fce0035698add596a445d3c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4634"></a>Предупреждение компилятора (уровень 4) C4634
Комментарий XML-документа: применить невозможно: причина  
  
 Теги XML-документации могут применяться не ко всем конструкциям C++.  Например, нельзя добавить комментарий документации к пространству имен или шаблону.  
  
 Дополнительные сведения см. в разделе [XML Documentation](../../ide/xml-documentation-visual-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4634.  
  
```  
// C4634.cpp  
// compile with: /W4 /doc /c  
/// This is a namespace.   // C4634  
namespace hello {  
   class MyClass  {};  
};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4634.  
  
```  
// C4634_b.cpp  
// compile with: /W4 /doc /c  
/// This is a template.   // C4634  
template <class T>  
class MyClass  {};  
```