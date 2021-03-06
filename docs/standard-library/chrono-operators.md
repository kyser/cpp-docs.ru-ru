---
title: Операторы &lt;chrono&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 1ac1051ddaa67dc1970119586ecb9e937583c58a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ltchronogt-operators"></a>Операторы &lt;chrono&gt;

||||
|-|-|-|
|[operator modulo](#op_modulo)|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|
|[operator&gt;=](#op_gt_eq)|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|
|[оператор*](#op_star)|[operator+](#op_add)|[operator-](#operator-)|
|[оператор/](#op_div)|[оператор==](#op_eq_eq)|

## <a name="operator-"></a>  operator-

Оператор вычитания или отрицания объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);


template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

`Time` Объект `time_point` объекта.

`Dur` Объект `duration` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна разнице временных интервалов двух аргументов.

Вторая функция возвращает объект `time_point`, который представляет момент времени, полученный путем отнимания временного интервала, представленного объектом `Dur`, от момента времени, заданного объектом `Time`.

Третья функция возвращает объект `duration`, представляющий временной интервал между объектами `Left` и `Right`.

## <a name="op_neq"></a> operator!=

Оператор неравенства для объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left == Right)`.

## <a name="op_star"></a>  operator*

Оператор деления для объектов [duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);


template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>Параметры

`Dur` Объект `duration` объекта.

`Mult` Целочисленное значение.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна значению `Mult`, умноженному на длительность `Dur`.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, первая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если `is_convertible<Rep1, common_type<Rep1, Rep2>>`*не содержит значение true*, вторая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_div"></a>  operator/

Оператор деления для объектов[duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);


template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

`Dur` Объект `duration` объекта.

`Div` Целочисленное значение.

`Left` Слева `duration` объекта.

`Right` Право `duration` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает объект duration с длительностью интервала, равной длительности `Dur`, деленной на значение `Div`.

Второй оператор возвращает соотношение длительностей интервалов `Left` и `Right`.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, а `Rep2` не является экземпляром `duration`, первый оператор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_add"></a>  operator+

Добавляет объекты [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);


template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

`Time` Объект `time_point` объекта.

`Dur` Объект `duration` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration` с временным интервалом, равным сумме интервалов `Left` и `Right`.

Вторая и третья функции возвращают объект `time_point`, который представляет момент времени, отстоящий от момента времени `Time` на временной интервал `Dur`.

## <a name="op_lt"></a> operator&lt;

Определяет, справедливо ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает значение `true`, если длина интервала `Left` меньше, чем длина интервала `Right`. В противном случае функция возвращает значение `false`.

Вторая функция возвращает значение `true`, если `Left` больше `Right`. В противном случае функция возвращает значение `false`.

## <a name="op_lt_eq"></a>  operator&lt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Right < Left)`.

## <a name="op_eq_eq"></a> operator==

Определяет, справедливо ли, что два объекта `duration` представляют интервалы времени, имеющие одинаковую длину, или, что два объекта `time_point` представляют один и тот же момент времени.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает значение `true`, если `Left` и `Right` представляют интервалы времени одинаковой длины. В противном случае функция возвращает значение `false`.

Вторая функция возвращает значение `true`, если `Left` и `Right` представляют один и тот же момент времени. В противном случае функция возвращает значение `false`.

## <a name="op_gt"></a> operator&gt;

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `Right < Left`.

## <a name="op_gt_eq"></a> operator&gt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

`Left` Слева `duration` или `time_point` объекта.

`Right` Право `duration` или `time_point` объекта.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left < Right)`.

## <a name="op_modulo"></a>  operator modulo

Оператор для операций вычисления остатка от деления над объектами [duration](../standard-library/duration-class.md).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

`Dur` Объект `duration` объекта.

`Div` Целочисленное значение.

`Left` Слева `duration` объекта.

`Right` Право `duration` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна остатку от деления `Dur` на `Div`.

Вторая функция возвращает значение, представляющее остаток от деления `Left` на `Right`.

## <a name="see-also"></a>См. также

[\<chrono>](../standard-library/chrono.md)<br/>
