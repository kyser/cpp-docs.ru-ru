---
title: Предупреждение (уровень 1) C4129 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc095a32e5cb0d5a0bf240282e11c3fa3382ffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4129"></a>Предупреждение (уровень 1) C4129 компилятора
«символ»: неизвестная escape-последовательность  
  
 `character` После обратной косой черты (\\) в символьной или строковой константы не распознан как допустимый escape-последовательность. Обратная косая черта пропускается и не печатаются. Следующий за ним знак выводится на печать.  
  
 Чтобы напечатать одну обратную косую черту, укажите две обратные косые черты (\\\\).  
  
 Стандарт языка C++, в разделе 2.13.2 рассматриваются escape-последовательности.  
  
 Следующий пример приводит к возникновению ошибки C4129:  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```