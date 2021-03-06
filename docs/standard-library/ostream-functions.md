---
title: Функции &lt;ostream&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: e85ce2728aaaa8ae9b23067bfb1dcbb3ff2db7d0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="ltostreamgt-functions"></a>Функции &lt;ostream&gt;

Это глобальный шаблон функции, определенные в &lt;ostream&gt;. Для функций-членов, в разделе [класс basic_ostream](basic-ostream-class.md) документации.

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

Завершает строку и очищает буфер.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem* тип элемента.

*Ostr* объект типа **basic_ostream**.

*TR* признаки символов.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ Увеличьте ширину](../standard-library/basic-ios-class.md#widen)(«\n»)), а затем вызывает *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

### <a name="example"></a>Пример

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>концы

Завершает строку.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem* тип элемента.

*Ostr* объект типа **basic_ostream**.

*TR* признаки символов.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Поместите](../standard-library/basic-ostream-class.md#put)(*Elem*(«\0»)). Он возвращает *Ostr*.

### <a name="example"></a>Пример

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

Очищает буфер.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Параметры

*Elem* тип элемента.

*Ostr* объект типа **basic_ostream**.

*TR* признаки символов.

### <a name="return-value"></a>Возвращаемое значение

Объект типа **basic_ostream**.

### <a name="remarks"></a>Примечания

Вызовы манипулятор *Ostr*.[ Очистить](../standard-library/basic-ostream-class.md#flush). Он возвращает *Ostr*.

### <a name="example"></a>Пример

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

Меняет местами значения двух **basic_ostream** объектов.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Параметры

*Elem* тип элемента.

*TR* признаки символов.

*левый* ссылка lvalue на **basic_ostream** объекта.

*правый* ссылка lvalue на **basic_ostream** объекта.

### <a name="remarks"></a>Примечания

Функция шаблона **swap** выполняет `left.swap(right)`.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)
