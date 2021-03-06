---
title: Класс time_put | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fbd4cf162ba16ac5c9ae9c6bf018be2988507bcb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="timeput-class"></a>Класс time_put

Данный класс шаблона описывает объект, который можно использовать как аспект языкового стандарта для управления преобразованием значений времени в последовательности типа `CharType`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

`CharType` Тип, используемый внутри программы для кодирования символов.

`OutputIterator` Тип итератора, куда помещает функции записывают свои выходные данные.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[time_put](#time_put)|Конструктор для объектов типа `time_put`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.|
|[put](#put)|Выводит информацию о времени и дате в виде последовательности `CharType`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="char_type"></a>  time_put::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра-шаблона **CharType**.

## <a name="do_put"></a>  time_put::do_put

Виртуальная функция, выводящая информацию о времени и дате в виде последовательности объектов **CharType**.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Параметры

`next` Итератор вывода, где последовательность символов, представляющих даты и времени должны быть вставлены.

`_Iosbase` Не используется.

`_Pt` Данные даты и времени, выходные данные.

`_Fmt` Формат выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

`_Mod` Модификатор форматирования. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Примечания

Виртуально защищенная функция-член создает последовательные элементы, начиная с `next` со значений времени, сохраненных в объекте \* `_Pt` типа **tm**. Функция возвращает итератор, обозначающий следующую позицию для вставки элемента после сформированного вывода.

Вывод создается по тем же правилам, которые используются `strftime`, с последним аргументом `_Pt`, для создания серии элементов `char` в массиве. Предполагается, что каждый такой элемент `char` подбирается к эквивалентному элементу типа **CharType** с помощью простого соответствия "один к одному". Если `_Mod` равно нулю, эффективный формат имеет вид "%F", где F заменяется `_Fmt`. В противном случае эффективный формат имеет вид "%MF", где M заменяется `_Mod`.

### <a name="example"></a>Пример

См. пример для метода [put](#put), который вызывает `do_put`.

## <a name="iter_type"></a>  time_put::iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом параметра-шаблона **OutputIterator**.

## <a name="put"></a>  time_put::put

Выводит информацию о времени и дате в виде последовательности объектов **CharType**.

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

`next` Итератор вывода, где последовательность символов, представляющих даты и времени должны быть вставлены.

`_Iosbase` Не используется.

`_Fill` Символ типа **CharType** применяется для интервала.

`_Pt` Данные даты и времени, выходные данные.

`_Fmt` Формат выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

`_Mod` Модификатор форматирования. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

`first` Начало строки форматирования для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

`last` Конец строки формата для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает значения [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`). Вторая функция-член копирует в \* `next` ++ любой элемент в интервале [ `first`, `last`), отличный от процента (%). Что касается процента, за которым следует символ *C* в интервале [ `first`, `last`), функция вместо этого оценивает `next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) и пропускает *C*. Однако если *C* является символом квалификатора из набора EOQ#, за которым следует символ `C2` в интервале [ `first`, `last`), функция вместо этого оценивает `next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) и пропускает `C2`.

### <a name="example"></a>Пример

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_put"></a>  time_put::time_put

Конструктор для объектов типа `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

`_Refs` Целочисленное значение используется для указания типа управление памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения параметра `_Refs` и их важность:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \> 1: эти значения не определены.

Конструктор инициализирует его базовым объектом с [locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)<br/>
[Класс time_base](../standard-library/time-base-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
