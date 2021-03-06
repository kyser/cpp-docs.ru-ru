---
title: Семантика выражений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- grammar, expressions
- expressions [C++], semantics
- expression evaluation
- expression evaluation, about expression evaluation
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8419ea4e446c8bf2f555c680079ccb91cc26afb5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="semantics-of-expressions"></a>Семантика выражений
Выражения оцениваются по приоритетности и группировке операторов. ([Приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md) в [лексические соглашения](../cpp/lexical-conventions.md), показаны отношения C++ операторы налагают на выражения.)  
  
## <a name="order-of-evaluation"></a>Порядок вычислений  
 Рассмотрим следующий пример.  
  
```cpp  
// Order_of_Evaluation.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
    int a = 2, b = 4, c = 9;  
  
    cout << a + b * c << "\n";  
    cout << a + (b * c) << "\n";  
    cout << (a + b) * c << "\n";  
}  
```  
  
```Output  
38  
38  
54  
```  
  
 ![Порядок вычисления в выражении](../cpp/media/vc38zv1.gif "vc38ZV1")  
Порядок вычисления выражений  
  
 Порядок, в котором оценивается выражение, показанное на рисунке выше, определяется приоритетностью и ассоциативностью операторов.  
  
1.  Умножение (\*) имеет наибольший приоритет в этом выражении; следовательно, выражение `b * c` оценивается первым.  
  
2.  Сложение (+) имеет следующий наибольший приоритет, поэтому `a` добавляется к произведению `b` и `c`.  
  
3.  Левый перенос (<<) имеет самый низкий приоритет в выражении, однако существует два вхождения. Поскольку оператор левого переноса группирует выражение слева направо, левое вложенное выражение оценивается первым, а затем — правое.  
  
 Если для группировки вложенных выражений используются скобки, они меняют приоритет и порядок оценки выражения, как показано на следующем рисунке.  
  
 ![Порядок вычисления выражения со скобками](../cpp/media/vc38zv2.gif "vc38ZV2")  
Порядок вычисления выражений со скобками  
  
 Выражения, такие как на рисунке выше, оцениваются исключительно для побочного эффекта, в данном случае — для переноса информации на стандартное устройство вывода.  
  
## <a name="notation-in-expressions"></a>Нотация в выражениях  
 В языке C++ определен ряд параметров совместимости, действующих при указании операндов. Следующая таблица показывает типы операндов допустимых операторов, которые требуются операнды типа *типа*.  
  
### <a name="operand-types-acceptable-to-operators"></a>Типы операндов, допустимые для операторов  
  
|Требуется тип|Допускаются типы|  
|-------------------|-------------------|  
|*type*|`const` *Тип*<br /> `volatile` *Тип*<br /> *Тип*&<br /> `const` *Тип*&<br /> `volatile` *Тип*&<br /> `volatile const` *Тип*<br /> `volatile const` *Тип*&|  
|*Тип*\*|*Тип*\*<br /> `const` *Тип*\*<br /> `volatile` *Тип*\*<br /> `volatile const` *Тип*\*|  
|`const` *Тип*|*type*<br /> `const` *Тип*<br />`const` *Тип*&|  
|`volatile` *Тип*|*type*<br /> `volatile` *Тип*<br /> `volatile` *Тип*&|  
  
 Поскольку перечисленные выше правила всегда могут сочетаться друг с другом, то в тех операторах, в которых требуется указатель, можно задавать указатель с модификатором const на объект с модификатором volatile.  
  
## <a name="ambiguous-expressions"></a>Неоднозначные выражения  
 Значение некоторых выражений неоднозначно. Такие выражения чаще всего встречаются, если значение объекта несколько раз изменяется в одном выражении. Подобные выражения зависят от конкретного порядка вычисления, когда этот порядок не определяется языком. Рассмотрим следующий пример.  
  
```  
int i = 7;  
  
func( i, ++i );  
```  
  
 Язык C++ не гарантирует порядок, в котором вычисляются аргументы при вызове функции. Поэтому в предыдущем примере в функцию `func` могут быть переданы значения параметров 7 и 8 или 8 и 8, в зависимости от порядка вычисления параметров — слева направо или справа налево.  
  
## <a name="c-sequence-points-microsoft-specific"></a>Точки следования C++ (только для систем Майкрософт)  
 Выражение может изменить значение объекта только один раз между следующими друг за другом точками следования.  
  
 В языке C++ в настоящее время точки следования не определены. В Microsoft C++ для любого выражения, содержащего операторы C и не содержащего перегруженные операторы, используются те же точки следования, что и в ANSI C. Когда операторы перегружены, семантика изменяется с последовательности операторов на последовательность вызовов функций. В Microsoft C++ используются следующие точки следования.  
  
-   Левый операнд оператора логического И (&&). Перед продолжением полностью вычисляется левый операнд оператора логического И и учитываются все побочные эффекты. Гарантии вычисления правого операнда оператора логического И нет.  
  
-   Левый операнд оператора логического или (&#124;&#124;). Перед продолжением полностью вычисляется левый операнд оператора логического ИЛИ и учитываются все побочные эффекты. Гарантии вычисления правого операнда оператора логического ИЛИ нет.  
  
-   Левый операнд оператора запятой. Перед продолжением полностью вычисляется левый операнд оператора запятой и учитываются все побочные эффекты. Оба операнда оператора запятой вычисляются всегда.  
  
-   Оператор вызова функции. До входа в функцию вычисляются выражение вызова функции и все ее аргументы, включая аргументы по умолчанию, а также учитываются все побочные эффекты. Порядок вычисления аргументов и выражения вызова функции не определен.  
  
-   Первый операнд условного оператора. Перед продолжением полностью вычисляется первый операнд условного оператора и учитываются все побочные эффекты.  
  
-   Конец полного выражения инициализации, например конец инициализации в операторе объявления.  
  
-   Выражение в операторе выражения. Операторы выражения состоят из необязательного выражения с последующей точкой с запятой (;). Выражение полностью вычисляется для учета его побочных эффектов.  
  
-   Управляющее выражение в операторе выбора (if или switch). До выполнения кода, зависящего от сделанного выбора, полностью вычисляется выражение и учитываются все побочные эффекты.  
  
-   Управляющее выражение оператора while или do. До выполнения любых операторов в следующей итерации цикла while или do полностью вычисляется выражение и учитываются все побочные эффекты.  
  
-   Каждое из трех выражений оператора for. До перехода к следующему выражению полностью вычисляется каждое выражение и учитываются все побочные эффекты.  
  
-   Выражение в операторе return. До возврата управления в вызывающую функцию полностью вычисляется выражение и учитываются все побочные эффекты.  
  
## <a name="see-also"></a>См. также  
 [Выражения](../cpp/expressions-cpp.md)