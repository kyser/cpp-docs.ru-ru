---
title: Предупреждение (уровень 1) C4744 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a45207f85575c8047f673b415ce802dbac24318
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4744"></a>Предупреждение компилятора (уровень 1) C4744
«переменная» имеет различные типы в «файл1» и «файл2»: «тип1» и «тип2»  
  
 Внешняя переменная определена в двух файлах или ссылаться на имеет различные типы в этих файлах.  Чтобы решить, сделать определения типа одинаковыми или изменить имя переменной, в один из файлов.  
  
 C4744 вызывается, только в том случае, если файлы были скомпилированы с параметром/GL.  Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  C4744 обычно возникает в файлах C (C++), так как в C++ имя переменной сведения о типе.  При компиляции образца (см. ниже) как C++, возникнет ошибка компоновщика LNK2019.  
  
## <a name="example"></a>Пример  
 В этом примере содержится первое определение.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4744.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```