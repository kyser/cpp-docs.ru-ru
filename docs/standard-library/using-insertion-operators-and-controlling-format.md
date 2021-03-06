---
title: Использование операторов вставки и управление форматом | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cb6d17a771b5a1e24b8d09532f432b95ce5d736
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="using-insertion-operators-and-controlling-format"></a>Использование операторов вставки и управление форматом

В этой статье описывается, как управлять форматом и как создавать операторы вставки для собственных классов. Оператор вставки (**<<**), который изначально включен во все стандартные типы данных C++, отправляет байты в объект потока вывода. Операторы вставки работают с предопределенными "манипуляторами" — элементами, которые изменяют формат целочисленных аргументов, заданный по умолчанию.

Форматом можно управлять с помощью следующих параметров:

- [Ширина выходных данных](#vclrfoutputwidthanchor3)

- [Выравнивание](#vclrfalignmentanchor4)

- [Точность](#vclrfprecisionanchor5)

- [Основание системы счисления](#vclrfradixanchor6)

## <a name="vclrfoutputwidthanchor3"></a> Ширина выходных данных

Чтобы выровнять выходные данные, нужно указать ширину выходных данных для каждого элемента, поместив в поток манипулятор `setw` или вызвав функцию-член **width**. В этом примере выравниваются по правому краю значения в столбце шириной по крайней мере 10 символов:

```cpp
// output_width.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   for( int i = 0; i < 4; i++ )
   {
      cout.width(10);
      cout << values[i] << '\n';
   }
}
```

```Output
      1.23
     35.36
     653.7
   4358.24
```

Начальные пробелы добавляются в любое значение шириной менее 10 символов.

Для заполнения поля используйте функцию-член **fill**, задающую значение символа заполнения для полей, имеющих заданную ширину. По умолчанию используется пробел. Чтобы заполнить столбец чисел звездочками, измените предыдущий цикл **for** следующим образом:

```cpp
for (int i = 0; i <4; i++)
{
    cout.width(10);
    cout.fill('*');
    cout << values[i] << endl;
}
```

Манипулятор `endl` заменяет символ перевода строки (`'\n'`). Вывод выглядит следующим образом.

```Output
******1.23
*****35.36
*****653.7
***4358.24
```

Чтобы указать ширину элементов выходных данных в той же строке, используйте манипулятор `setw`:

```cpp
// setw.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };
   for( int i = 0; i < 4; i++ )
      cout << setw( 6 )  << names[i]
           << setw( 10 ) << values[i] << endl;
}
```

Функция-член **width** объявлена в \<iostream>. Если вы используете `setw` или любой другой манипулятор с аргументами, необходимо включить \<iomanip>. В выходных данных строки выводятся в поле шириной 6, а целые числа — в поле шириной 10:

```Output
  Zoot      1.23
 Jimmy     35.36
    Al     653.7
  Stan   4358.24
```

Ни одна из функций `setw` и **width** не усекает значения. Если форматированные выходные данные превышают ширину, значения выводятся полностью в соответствии с заданной в потоке точностью. Обе функции `setw` и **width** воздействуют только на следующее поле. Для ширины поля восстанавливается значение по умолчанию (необходимая ширина) после вывода одного поля. Другие параметры форматирования потока остаются в силе, пока не будут изменены.

## <a name="vclrfalignmentanchor4"></a> Выравнивание

По умолчанию выравнивание текста в потоках вывода задано по правому краю. Чтобы выровнять имена по левому краю, а числа — по правому краю, измените цикл **for** в предыдущем примере следующим образом:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6) << names[i]
         << resetiosflags(ios::left)
         << setw(10) << values[i] << endl;
```

Вывод выглядит следующим образом.

```Output
Zoot        1.23
Jimmy      35.36
Al         653.7
Stan     4358.24
```

Флаг выравнивания по левому краю устанавливается с помощью манипулятора [setiosflags](../standard-library/iomanip-functions.md#setiosflags) с перечислителем `left`. Этот перечислитель определен в классе [ios](../standard-library/basic-ios-class.md), поэтому его ссылка должна содержать префикс **ios::**. Манипулятор [resetiosflags](../standard-library/iomanip-functions.md#resetiosflags) снимает флаг выравнивания по левому краю. В отличие от **width** и `setw`, `setiosflags` и `resetiosflags` действуют постоянно.

## <a name="vclrfprecisionanchor5"></a> Точность

По умолчанию для чисел с плавающей запятой задана точность шесть. Например, число 3466,9768 выводится как 3466,98. Чтобы изменить способ вывода этого значения, используйте манипулятор [setprecision](../standard-library/iomanip-functions.md#setprecision). Манипулятор имеет два флага: [fixed](../standard-library/ios-functions.md#fixed) и [scientific](../standard-library/ios-functions.md#scientific). Если указан флаг [fixed](../standard-library/ios-functions.md#fixed), число выводится как 3466,976800. Если указан флаг **scientific**, оно выводится как 3,4669773+003.

Чтобы отобразить числа с плавающей запятой, приведенные в разделе [Выравнивание](#vclrfalignmentanchor4), с одной значащей цифрой, измените цикл **for** следующим образом:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6)
         << names[i]
         << resetiosflags(ios::left)
         << setw(10)
         << setprecision(1)
         << values[i]
         << endl;
```

Программа выведет этот список:

```Output
Zoot          1
Jimmy     4e+01
Al        7e+02
Stan      4e+03
```

Чтобы исключить экспоненциальное представление чисел, вставьте перед циклом **for** следующий оператор:

```cpp
cout << setiosflags(ios::fixed);
```

С фиксированной нотацией программа выводит числа с одной цифрой после десятичной запятой.

```Output
Zoot         1.2
Jimmy       35.4
Al         653.7
Stan      4358.2
```

Если изменить флаг **ios::fixed** на **ios::scientific**, программа выведет следующее:

```cpp
Zoot    1.2e+00
Jimmy   3.5e+01
Al      6.5e+02
Stan    4.4e+03
```

В этом случае программа также выводит числа с одной цифрой после десятичной запятой. Если установлен любой из флагов **ios::fixed** или **ios::scientific**, значение точности определяет число знаков после десятичной запятой. Если не установлен ни один из флагов, значение точности определяет общее количество значащих цифр. Манипулятор `resetiosflags` снимает эти флаги.

## <a name="vclrfradixanchor6"></a> Основание системы счисления

Манипуляторы **dec**, **oct** и **hex** определяют основание системы счисления по умолчанию для входных и выходных данных. Например, если вы вставите в поток вывода манипулятор **hex**, объект будет корректно преобразовывать внутреннее представление целых чисел в шестнадцатеричный выходной формат. Числа отображаются с цифрами от a до f в нижнем регистре, если не установлен флаг [uppercase](../standard-library/ios-functions.md#uppercase) (по умолчанию). В противном случае они отображаются в верхнем регистре. Основание системы счисления по умолчанию — **dec** (десятичная).

## <a name="quoted-strings-c14"></a>Строки в кавычках (C++ 14)

Если вы вставляете строку в поток, вы можете легко извлечь ту же строку обратно с помощью вызова функции-члена stringstream::str(). Однако, если вы хотите использовать оператор извлечения для вставки потока в новую строку позднее, вы можете получить непредвиденный результат, потому что оператор >> по умолчанию останавливается, когда встречает первый символ пробела.

```cpp
std::stringstream ss;
std::string inserted = "This is a sentence.";
std::string extracted;

ss << inserted;
ss >> extracted;

std::cout << inserted;     //  This is a sentence.
std::cout << extracted;    //  This
```

Это поведение можно устранить вручную, но чтобы сделать обход строки более удобным, C++ 14 добавляет `std::quoted` манипулятор в потока \<iomanip >. При вставке `quoted()` окружает строку разделителями (по умолчанию — двойные кавычки «"»), а при извлечении манипулирует потоком так, чтобы извлекать все символы, пока не будет обнаружен конечный разделитель. Все вложенные кавычки экранируются с помощью escape-символа (по умолчанию — '\\\\').

Разделители присутствуют только в объекте потока; не присутствуют в извлеченной строке, но они присутствуют в строку, возвращаемую [basic_stringstream::str](../standard-library/basic-stringstream-class.md#str).

Обработка пробелов операциями вставки и извлечения не зависит от способа представления строки в коде, поэтому заключение оператора в кавычки будет полезно в любом случае, независимо от того, является входная строка необработанным строковым литералом или обычной строкой. Входная строка независимо от ее формата может иметь вложенные кавычки, разрывы строк, символы табуляции и т. д. Все они сохраняются с помощью манипулятора quoted().

Дополнительные сведения и полные примеры кода см. в разделе [в кавычках](../standard-library/iomanip-functions.md#quoted).

## <a name="see-also"></a>См. также

[Потоки вывода](../standard-library/output-streams.md)<br/>
