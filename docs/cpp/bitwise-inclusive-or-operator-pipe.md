---
title: 'Побитовое включительно или оператор: || Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc43460bc2c20262156bfdc6bd7f69a693c222f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bitwise-inclusive-or-operator-"></a>Битовый оператор ИЛИ (включительно): |
## <a name="syntax"></a>Синтаксис  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>Примечания  
 Оператора побитового или (**&#124;**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если любой из битов равен единице, соответствующий бит результата устанавливается равным единице, а в противном случае — нулю.  
  
 Оба операнда оператора побитового ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md) применяются к операндам.  
  
## <a name="operator-keyword-for-124"></a>Ключевое слово оператора&#124;  
 `bitor` Оператор является текстовым эквивалентом **&#124;**. Существует два способа доступа к `bitor` оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Побитовые операторы в C](../c-language/c-bitwise-operators.md)

