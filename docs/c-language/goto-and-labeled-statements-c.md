---
title: Оператор goto и помеченные операторы в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf56a409f9a76cdf401323d1425ee28fc6cf286b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="goto-and-labeled-statements-c"></a>goto и помеченные операторы (C)
Оператор `goto` передает управление метке. Данная метка должна находиться в той же функции и может присутствовать только перед одним ее оператором.  
  
## <a name="syntax"></a>Синтаксис  
 *statement*:  
 *labeled-statement*  
  
 *jump-statement*  
  
 *оператор-перехода*:  
 **goto**  *identifier*  **;**  
  
 *labeled-statement*:  
 *identifier*  **:**  *statement*  
  
 Метка оператора значима только для оператора `goto`; в любом другом контексте оператор с меткой выполняется независимо от нее.  
  
 *jump-statement* должен находиться в той же функции и может присутствовать только перед одним ее оператором. Набор имен *identifier* после оператора `goto` имеет свое собственное пространство имен, поэтому эти имена не конфликтуют с другими идентификаторами. Повторное объявление меток невозможно. Дополнительные сведения см. в статье [Пространства имен](../c-language/name-spaces.md).  
  
 Хорошим стандартом в программировании следует считать применение **break**, **continue** и `return` вместо `goto` во всех случаях, когда это возможно. Поскольку оператор **break** выполняет выход только из одного уровня вложенности, для глубоко вложенных циклов может потребоваться оператор `goto`.  
  
 В следующем примере показано использование оператора `goto`.  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 В этом примере оператор `goto` передает управление в точку с меткой `stop`, когда значение переменной `i` равно 5.  
  
## <a name="see-also"></a>См. также  
 [Операторы](../c-language/statements-c.md)