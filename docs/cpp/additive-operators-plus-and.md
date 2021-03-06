---
title: 'Аддитивные операторы: + и - | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f265bf915d9ba0c984b85235bd502d6ea0a5a77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="additive-operators--and--"></a>Аддитивные операторы: + и -
## <a name="syntax"></a>Синтаксис  
  
```  
expression + expression   
expression - expression  
```  
  
## <a name="remarks"></a>Примечания  
 Ниже перечислены аддитивные операторы.  
  
-   Сложение (**+**)  
  
-   Вычитание (**-**)  
  
 Эти бинарные операторы имеют ассоциативность слева направо.  
  
 Аддитивные операторы принимают операнды арифметических типов или типов указателей. Результатом оператора сложения (**+**) является сумма операндов. Результатом оператора вычитания (**-**) является разность операндов. Если один или оба операнда являются указателями, они должны быть указателями на объекты, а не на функции. Когда оба операнда являются указателями, результаты имеют смысл только в том случае, если оба операнда указывают на объекты в одном массиве.  
  
 Аддитивные операторы принимают операнды *арифметические*, *целый*, и *скалярные* типов. Они описаны в следующей таблице.  
  
### <a name="types-used-with-additive-operators"></a>Типы, используемые с аддитивными операторами  
  
|Тип|Значение|  
|----------|-------------|  
|*Арифметические операции*|Целочисленные типы и типы с плавающей запятой собирательно называются "арифметическими" типами.|  
|*целочисленный*|Типы char и int всех размеров (long, short), а также перечисления называются "целочисленными типами".|  
|*скалярные*|Скалярные операнды — это операнды арифметического типа или типа указателя.|  
  
 Допускаются следующие сочетания этих операторов:  
  
 *арифметические* + *арифметические*  
  
 *скалярные* + *целочисленный*  
  
 *целочисленный* + *скалярные*  
  
 *арифметические* - *арифметические*  
  
 *скалярные* - *скалярные*  
  
 Обратите внимание, что сложение и вычитание не являются эквивалентными операциями.  
  
 Если оба операнда имеют арифметический тип, преобразования, описанные в [стандартные преобразования](standard-conversions.md) применяются к операндам, и это является результатом к преобразованному типу.  
  
## <a name="example"></a>Пример  
  
```  
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## <a name="pointer-addition"></a>Добавление указателей  
 Если один из операндов в операции сложения является указателем на массив объектов, другой должен иметь целочисленный тип. Результатом является указатель, имеющий тот же тип, что и исходный указатель, и указывающий на другой элемент массива. Эта концепция проиллюстрирована в следующем фрагменте кода.  
  
```  
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 Несмотря на то что целочисленное значение 1 добавляется в `pIntArray`, это не означает "добавить 1 к адресу"; скорее, это означает "скорректировать указатель так, чтобы он указывал на следующий объект в массиве", то есть через 2 байта (или `sizeof( int )`).  
  
> [!NOTE]
>  Код формы `pIntArray = pIntArray + 1` редко можно найти в программах на C++; чтобы выполнить пошаговое увеличение, предпочтительно использовать следующие формы: `pIntArray++` или `pIntArray += 1`.  
  
## <a name="pointer-subtraction"></a>Вычитание указателей  
 Если оба операнда являются указателями, то результатом вычитания будет число элементов массива, находящихся между операндами. Выражение вычитания результатом знаком целочисленного типа ptrdiff_t (определен в стандартном включаемом файле \<stddef.h >).  
  
 Второй операнд может иметь целочисленное значение. Результат вычитания имеет тот же тип, что и исходный указатель. Значением вычитания является указателем на (*n* - *я*) элемент массива номер, где *n* элемент указывает исходный указатель и *я* — целочисленное значение второго операнда.  
  
## <a name="see-also"></a>См. также  
 [Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Аддитивные операторы в C](../c-language/c-additive-operators.md)
