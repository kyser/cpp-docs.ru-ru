---
title: Операторы присваивания | Документы Microsoft
ms.custom: ''
ms.date: 03/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
- '&&='
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- '&&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4318d7913b180c3fbadcf9d655e402c9b0ad7ccc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="assignment-operators"></a>Операторы присваивания
## <a name="syntax"></a>Синтаксис  
  
```  
expression assignment-operator expression   
assignment-operator : one of  
   =   *=   /=   %=   +=   -=   <<=   >>=   &=   ^=   |=  &&=
```  
  
## <a name="remarks"></a>Примечания  
 Операторы присваивания сохраняют значение в объекте, обозначенном левым операндом. Существует три типа операторов присваивания: 

1. Простое присваивание, в котором хранится значение второго операнда в объект, указанный первым операндом. 1. Составное присваивание, в котором арифметические, shift или Побитовая операция выполняется перед сохранением результат.
1. какие ресурсы передаются без копирования переместите назначения (для типов классов).


Все операторы присваивания в следующей таблице, за исключением = и & & = операторы — это составные операторы присваивания.  
  
### <a name="assignment-operators"></a>Операторы присваивания  
  
|Оператор|Значение|  
|--------------|-------------|  
|**=**|Сохранение значения второго операнда в объект, указанный первым операндом (простое присваивание).|  
|**\*=**|Умножение значения первого операнда на значение второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**/=**|Деление значения первого операнда на значение второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**%=**|деление по модулю первого операнда на значение второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**+=**|Сложение значения первого операнда со значением второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**-=**|Вычитание значения второго операнда из значения первого операнда; сохранение результата в объект, указанный первым операндом.|  
|**<\<=**|Сдвиг значения первого операнда влево на количество битов, заданное значением второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**>>=**|Сдвиг значения первого операнда вправо на количество битов, заданное значением второго операнда; сохранение результата в объект, указанный первым операндом.|  
|**&=**|Выполнение операции побитового И для значений первого и второго операндов; сохранение результата в объект, указанный первым операндом.|  
|**^=**|Выполнение операции побитового исключающего ИЛИ для значений первого и второго операндов; сохранение результата в объект, указанный первым операндом.|  
|**\|=**|Выполнение операции побитового включающего ИЛИ для значений первого и второго операндов; сохранение результата в объект, указанный первым операндом.|
|**&&=**| Оператор присваивания перемещением (класс только для типов). Если второй операнд является значением rvalue, переместите его ресурсы на первый операнд (без копирования). В разделе [конструкторы перемещения и операторы присваивания с перемещением](move-constructors-and-move-assignment-operators-cpp.md) для получения дополнительной информации.|
  
 **Ключевые слова операторов**  
  
 Три составных оператора присвоения текстовые эквиваленты. Они приведены ниже.  
  
|Оператор|Эквивалент|  
|--------------|----------------|  
|**&=**|`and_eq`|  
|**\|=**|`or_eq`|  
|**^=**|`xor_eq`|  
  
 Существует два способа доступа к эти ключевые слова операторов в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```  
// expre_Assignment_Operators.cpp  
// compile with: /EHsc  
// Demonstrate assignment operators  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;  
  
   a += b;      // a is 9  
   b %= a;      // b is 6  
   c >>= 1;      // c is 5  
   d |= e;      // Bitwise--d is 0xFFFF   
  
   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl  
         << "a += b yields " << a << endl  
         << "b %= a yields " << b << endl  
         << "c >>= 1 yields " << c << endl  
         << "d |= e yields " << hex << d << endl;  
}  
```  
  
## <a name="simple-assignment"></a>Простое присваивание  
 Простой оператор присваивания (=) сохраняет значение второго операнда в объекте, указанном первым операндом. Если оба объекта имеют арифметические типы, перед сохранением значения правый операнд преобразуется к типу левого.  
  
 Объекты типов const и volatile могут присваиваться значениям l-value типов, которые являются просто volatile или не являются ни const, ни volatile.  
  
 Присваивание объектам типа класса (типы структур, объединений и классов) выполняется с помощью функции operator=. По умолчанию эта функция-оператор производит побитовое копирование; однако такое поведение можно изменить с помощью перегруженных операторов. (См. [перегруженные операторы](../cpp/operator-overloading.md) подробнее.)  
  
 Объект любого класса, однозначно производного от некоторого базового класса, можно присвоить объекту этого базового класса. Обратное неверно, поскольку существует неявное преобразование из производного класса в базовый класс, но не из базового класса в производный класс. Пример:  
  
```  
// expre_SimpleAssignment.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
class ABase  
{  
public:  
    ABase() { cout << "constructing ABase\n"; }  
};  
  
class ADerived : public ABase  
{  
public:  
    ADerived() { cout << "constructing ADerived\n"; }  
};  
  
int main()  
{  
    ABase aBase;  
    ADerived aDerived;  
  
    aBase = aDerived; // OK  
    aDerived = aBase; // C2679  
}  
```  
  
 Присваивание ссылочным типам выполняется так, как если бы выполнялось присваивание объекту, на который указывает ссылка.  
  
 Для объектов типа класса присваивание отличается от инициализации. Для иллюстрации того, насколько сильно присваивание может отличаться от инициализации, рассмотрим код  
  
```  
UserType1 A;  
UserType2 B = A;  
```  
  
 В предыдущем коде показан инициализатор; он вызывает конструктор для типа `UserType2`, который принимает аргумент типа `UserType1`. В коде  
  
```  
UserType1 A;  
UserType2 B;  
  
B = A;  
```  
  
 оператор присваивания  
  
```  
B = A;   
```  
  
 может вызывать одно из указанных ниже действий.  
  
-   Вызывать функцию operator= для типа `UserType2` при условии, что функция operator= определена для аргумента типа `UserType1`.  
  
-   Вызывать функцию явного преобразования `UserType1::operator UserType2`, если такая функция существует.  
  
-   Вызывать конструктор `UserType2::UserType2`, если он существует, принимает аргумент `UserType1` и копирует результат.  
  
## <a name="compound-assignment"></a>Составное присваивание  
 Составные операторы присваивания, указанные в таблице в [операторы присваивания](../cpp/assignment-operators.md), указанной в форме *e1* `op` =  *e2*, где *e1* является изменяемым l значением отличный от const тип и *e2* является одним из следующих:  
  
-   Арифметический тип  
  
-   Указатель, если `op` является + или -  
  
 *E1* `op` =  *e2* формы ведет себя как *e1* *= e1* `op` *e2*, но *e1* вычисляется только один раз.  
  
 Составное присваивание перечисляемому типу создает сообщение об ошибке. Если левый операнд имеет тип указателя, правый операнд должен иметь тип указателя или являться константным выражением со значением 0. Если левый операнд имеет целый тип, правый операнд должен иметь отличный от указателя тип.  
  
## <a name="result-of-assignment-operators"></a>Результат операторов присваивания  
 Операторы присваивания возвращают значение объекта, указанного левым операндом после присваивания. Результирующий тип — это тип левого операнда. Результатом выражения присваивания всегда является l-значение. Эти операторы имеют ассоциативность справа налево. Левый операнд должен быть изменяемым l-значением.  
  
 В ANSI C результатом выражения присваивания не является l-значение. Поэтому допустимое выражение `(a += b) += c` в C++ недопустимо в C.  
  
## <a name="see-also"></a>См. также  
 [Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Операторы присваивания C](../c-language/c-assignment-operators.md)