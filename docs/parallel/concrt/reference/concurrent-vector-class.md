---
title: Класс concurrent_vector | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e120e072fb3f56788cbf39fbbc3887f5c816f4ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentvector-class"></a>Класс concurrent_vector
Класс `concurrent_vector` представляет собой класс контейнера последовательности, обеспечивающий доступ к элементам в случайном порядке. Позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
 private details::_Concurrent_vector_base_v4;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных элементов, хранимых в векторе.  
  
 `_Ax`  
 Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для параллельного вектора. Этот аргумент является необязательным, и значением по умолчанию является `allocator<T>`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельного вектора.|  
|`const_iterator`|Тип, предоставляющий итератор произвольного доступа, который может читать `const` элемент в параллельном векторе.|  
|`const_pointer`|Тип, предоставляющий указатель на `const` элемент в параллельном векторе.|  
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент, хранящийся в параллельном векторе для чтения и выполнения `const` операций.|  
|`const_reverse_iterator`|Тип, предоставляющий итератор произвольного доступа, который может читать любой `const` элемент в параллельном векторе.|  
|`difference_type`|Тип, предоставляющий расстояние со знаком между двумя элементами в параллельном векторе.|  
|`iterator`|Тип, предоставляющий итератор произвольного доступа, который может читать любой элемент в параллельном векторе. Изменение элемента с помощью итератора не является параллельно безопасно.|  
|`pointer`|Тип, предоставляющий указатель на элемент в параллельном векторе.|  
|`reference`|Тип, предоставляющий ссылку на элемент, хранящийся в параллельном векторе.|  
|`reverse_iterator`|Тип, предоставляющий итератор произвольного доступа, который может читать любой элемент в обратном параллельном векторе. Изменение элемента с помощью итератора не является параллельно безопасно.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельном векторе.|  
|`value_type`|Тип, представляющий тип данных, хранящихся в параллельном векторе.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[concurrent_vector](#ctor)|Перегружен. Создает параллельный вектор.|  
|[~ concurrent_vector деструктор](#dtor)|Удаляет все элементы и уничтожает параллельный вектор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[assign](#assign)|Перегружен. Удаляет элементы параллельного вектора и присваивает ему либо `_N` копий `_Item`, или значения, заданные диапазоном итератора [ `_Begin`, `_End`). Этот метод не является безопасным в режиме параллелизма.|  
|[at](#at)|Перегружен. Предоставляет доступ к элементу по указанному индексу в параллельном векторе. Данный метод безопасен в режиме параллелизма для операций чтения, а также при росте вектора, при условии, что гарантирует, что значение `_Index` меньше, чем размер параллельного вектора.|  
|[back](#back)|Перегружен. Возвращает ссылку или `const` ссылки на последнюю элемент в параллельном векторе. Если параллельный вектор пуст, возвращаемое значение не определено. Данный метод безопасен в режиме параллелизма.|  
|[begin](#begin)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.|  
|[capacity](#capacity)|Возвращает максимальный размер, до которого может расти параллельный вектор без необходимости выделить больше памяти. Данный метод безопасен в режиме параллелизма.|  
|[cbegin](#cbegin)|Возвращает итератор типа `const_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.|  
|[cend](#cend)|Возвращает итератор типа `const_iterator` конец параллельный вектор. Данный метод безопасен в режиме параллелизма.|  
|[clear](#clear)|Удаляет все элементы в параллельном векторе. Этот метод не является безопасным в режиме параллелизма.|  
|[crbegin](#crbegin)|Возвращает итератор типа `const_reverse_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.|  
|[crend](#crend)|Возвращает итератор типа `const_reverse_iterator` конец параллельный вектор. Данный метод безопасен в режиме параллелизма.|  
|[empty](#empty)|Проверяет, если параллельный вектор пуст во время этот метод вызывается. Данный метод безопасен в режиме параллелизма.|  
|[end](#end)|Перегружен. Возвращает итератор типа `iterator` или `const_iterator` в конец параллельный вектор. Данный метод безопасен в режиме параллелизма.|  
|[front](#front)|Перегружен. Возвращает ссылку или `const` ссылку на первый элемент в параллельном векторе. Если параллельный вектор пуст, возвращаемое значение не определено. Данный метод безопасен в режиме параллелизма.|  
|[get_allocator](#get_allocator)|Возвращает копию распределителя, используемого для создания параллельного вектора. Данный метод безопасен в режиме параллелизма.|  
|[grow_by](#grow_by)|Перегружен. Увеличивает данный параллельный вектор с `_Delta` элементов. Данный метод безопасен в режиме параллелизма.|  
|[grow_to_at_least](#grow_to_at_least)|Увеличивает данный параллельный вектор, пока он имеет по крайней мере `_N` элементов. Данный метод безопасен в режиме параллелизма.|  
|[max_size](#max_size)|Возвращает максимальное количество элементов, которые может вместить параллельный вектор. Данный метод безопасен в режиме параллелизма.|  
|[push_back](#push_back)|Перегружен. Добавляет заданный элемент в конец параллельного вектора. Данный метод безопасен в режиме параллелизма.|  
|[rbegin](#rbegin)|Перегружен. Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.|  
|[rend](#rend)|Перегружен. Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` в конец параллельный вектор. Данный метод безопасен в режиме параллелизма.|  
|[reserve](#reserve)|Выделяет достаточно места для увеличения параллельного вектора до размера `_N` без необходимости выделить больше памяти позднее. Этот метод не является безопасным в режиме параллелизма.|  
|[resize](#resize)|Перегружен. Изменяет размер параллельного вектора до запрошенного размера, удалении или добавлении элементов при необходимости. Этот метод не является безопасным в режиме параллелизма.|  
|[shrink_to_fit](#shrink_to_fit)|Сжимает внутреннее представление параллельного вектора, чтобы снизить уровень фрагментации и оптимизировать использование памяти. Этот метод не является безопасным в режиме параллелизма.|  
|[size](#size)|Возвращает число элементов в параллельном векторе. Данный метод безопасен в режиме параллелизма.|  
|[swap](#swap)|Меняет местами содержимое двух параллельных векторов. Этот метод не является безопасным в режиме параллелизма.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор]](#operator_at)|Перегружен. Предоставляет доступ к элементу по указанному индексу в параллельном векторе. Данный метод безопасен в режиме параллелизма для операций чтения, а также при росте вектора, при условии, что гарантирует, что значение `_Index` меньше, чем размер параллельного вектора.|  
|[оператор=](#operator_eq)|Перегружен. Назначает содержимое другой `concurrent_vector` этого объекта. Этот метод не является безопасным в режиме параллелизма.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о `concurrent_vector` см. в описании [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concurrent_vector.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="assign"></a> Назначение 

 Удаляет элементы параллельного вектора и присваивает ему либо `_N` копий `_Item`, или значения, заданные диапазоном итератора [ `_Begin`, `_End`). Этот метод не является безопасным в режиме параллелизма.  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>Параметры  
 `_InputIterator`  
 Тип указанного итератора.  
  
 `_N`  
 Число элементов для копирования в параллельный вектор.  
  
 `_Item`  
 Ссылка на значение, используемое для заполнения параллельного вектора.  
  
 `_Begin`  
 Итератор на первый элемент из исходного диапазона.  
  
 `_End`  
 Итератор, следующую за последним элементом в исходном диапазоне.  
  
### <a name="remarks"></a>Примечания  
 `assign` не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методы на параллельный вектор при вызове этого метода.  
  
##  <a name="at"></a> в 

 Предоставляет доступ к элементу по указанному индексу в параллельном векторе. Данный метод безопасен в режиме параллелизма для операций чтения, а также при росте вектора, при условии, что гарантирует, что значение `_Index` меньше, чем размер параллельного вектора.  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента, который требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент с указанным индексом.  
  
### <a name="remarks"></a>Примечания  
 Версия функции `at` , возвращающий значение, отличное от `const` ссылка не может использоваться для параллельной записи в элемент из разных потоков. Другой объект синхронизации должен использоваться для синхронизации параллельных чтения и операции записи в один и тот же элемент данных.  
  
 Метод создает `out_of_range` Если `_Index` больше или равен размеру параллельный вектор и `range_error` Если индекс создан для неисправной вектора. Сведения о том, как вектор могут стать неработоспособными. в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="back"></a> Назад 

 Возвращает ссылку или `const` ссылки на последнюю элемент в параллельном векторе. Если параллельный вектор пуст, возвращаемое значение не определено. Данный метод безопасен в режиме параллелизма.  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку или `const` ссылки на последнюю элемент в параллельном векторе.  
  
##  <a name="begin"></a> начать 

 Возвращает итератор типа `iterator` или `const_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` параллельный вектор в начало.  
  
##  <a name="capacity"></a> Емкость 

 Возвращает максимальный размер, до которого может расти параллельный вектор без необходимости выделить больше памяти. Данный метод безопасен в режиме параллелизма.  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальный размер, до которого может расти параллельный вектор без необходимости выделения дополнительной памяти.  
  
### <a name="remarks"></a>Примечания  
 В отличие от стандартной библиотеки C++ `vector`, `concurrent_vector` объекта не перемещать существующие элементы, если он выделяет больше памяти.  
  
##  <a name="cbegin"></a> cbegin 

 Возвращает итератор типа `const_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `const_iterator` параллельный вектор в начало.  
  
##  <a name="cend"></a> cend 

 Возвращает итератор типа `const_iterator` конец параллельный вектор. Данный метод безопасен в режиме параллелизма.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `const_iterator` конец параллельный вектор.  
  
##  <a name="clear"></a> Снимите флажок 

 Удаляет все элементы в параллельном векторе. Этот метод не является безопасным в режиме параллелизма.  
  
```
void clear();
```  
  
### <a name="remarks"></a>Примечания  
 `clear` не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методы на параллельный вектор при вызове этого метода. `clear` Освобождает внутренних массивов. Для освобождения внутренних массивов, вызовите функцию `shrink_to_fit` после `clear`.  
  
##  <a name="ctor"></a> concurrent_vector 

 Создает параллельный вектор.  
  
```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```  
  
### <a name="parameters"></a>Параметры  
 `M`  
 Тип распределителя исходный вектор.  
  
 `_InputIterator`  
 Тип итератора ввода.  
  
 `_Al`  
 Класс распределителя для использования с данным объектом.  
  
 `_Vector`  
 Исходный объект `concurrent_vector` для копирования или перемещения элементов.  
  
 `_N`  
 Начальная производительность объекта `concurrent_vector`.  
  
 `_Item`  
 Значение элементов в сформированный объект.  
  
 `_Begin`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `_End`  
 Положение первого элемента за пределами диапазона копируемых элементов.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя `_Al` и инициализации объекта vector.  
  
 Первый конструктор укажите пустой исходный вектор и явно указывает тип распределителя. для использования.  
  
 Второй и третий конструкторы определяют копию параллельного вектора `_Vector`.  
  
 Четвертый конструктор определяет перемещение параллельного вектора `_Vector`.  
  
 Пятый конструктор задает повторение указанного числа ( `_N`) элементов со значением по умолчанию для класса `T`.  
  
 Шестой конструктор задает повторение элементов ( `_N`) элементов со значением `_Item`.  
  
 Последний конструктор определяет значения, предоставленные диапазоном итератора [ `_Begin`, `_End`).  
  
##  <a name="dtor"></a> ~ concurrent_vector 

 Удаляет все элементы и уничтожает параллельный вектор.  
  
```
~concurrent_vector();
```  
  
##  <a name="crbegin"></a> crbegin 

 Возвращает итератор типа `const_reverse_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `const_reverse_iterator` параллельный вектор в начало.  
  
##  <a name="crend"></a> crend 

 Возвращает итератор типа `const_reverse_iterator` конец параллельный вектор. Данный метод безопасен в режиме параллелизма.  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `const_reverse_iterator` конец параллельный вектор.  
  
##  <a name="empty"></a> пустой 

 Проверяет, если параллельный вектор пуст во время этот метод вызывается. Данный метод безопасен в режиме параллелизма.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если вектор пуст в момент вызова функции, `false` в противном случае.  
  
##  <a name="end"></a> Конец 

 Возвращает итератор типа `iterator` или `const_iterator` в конец параллельный вектор. Данный метод безопасен в режиме параллелизма.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `iterator` или `const_iterator` в конец параллельный вектор.  
  
##  <a name="front"></a> Передний план 

 Возвращает ссылку или `const` ссылку на первый элемент в параллельном векторе. Если параллельный вектор пуст, возвращаемое значение не определено. Данный метод безопасен в режиме параллелизма.  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку или `const` ссылку на первый элемент в параллельном векторе.  
  
##  <a name="get_allocator"></a> get_allocator 

 Возвращает копию распределителя, используемого для создания параллельного вектора. Данный метод безопасен в режиме параллелизма.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копию распределителя, используемого для создания `concurrent_vector` объекта.  
  
##  <a name="grow_by"></a> grow_by 

 Увеличивает данный параллельный вектор с `_Delta` элементов. Данный метод безопасен в режиме параллелизма.  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>Параметры  
 `_Delta`  
 Количество элементов для добавления в объект.  
  
 `_Item`  
 Значение для инициализации новых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор на первый элемент, добавленный.  
  
### <a name="remarks"></a>Примечания  
 Если `_Item` не указан, новые элементы создаются по умолчанию.  
  
##  <a name="grow_to_at_least"></a> grow_to_at_least 

 Увеличивает данный параллельный вектор, пока он имеет по крайней мере `_N` элементов. Данный метод безопасен в режиме параллелизма.  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>Параметры  
 `_N`  
 Новый минимальный размер `concurrent_vector` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий начало присоединенных последовательности или элемент с индексом `_N` Если элементы не были добавлены.  
  
##  <a name="max_size"></a> max_size 

 Возвращает максимальное количество элементов, которые может вместить параллельный вектор. Данный метод безопасен в режиме параллелизма.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число элементов `concurrent_vector` могут храниться в объекте.  
  
##  <a name="operator_eq"></a> оператор = 

 Назначает содержимое другой `concurrent_vector` этого объекта. Этот метод не является безопасным в режиме параллелизма.  
  
```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```  
  
### <a name="parameters"></a>Параметры  
 `M`  
 Тип распределителя исходный вектор.  
  
 `_Vector`  
 Исходный объект `concurrent_vector`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `concurrent_vector` объекта.  
  
##  <a name="operator_at"></a> оператор] 

 Предоставляет доступ к элементу по указанному индексу в параллельном векторе. Данный метод безопасен в режиме параллелизма для операций чтения, а также при росте вектора, при условии, что гарантирует, что значение `_Index` меньше, чем размер параллельного вектора.  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента, который требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент с указанным индексом.  
  
### <a name="remarks"></a>Примечания  
 Версия `operator []` , возвращающий значение, отличное от `const` ссылка не может использоваться для параллельной записи в элемент из разных потоков. Другой объект синхронизации должен использоваться для синхронизации параллельных чтения и операции записи в один и тот же элемент данных.  
  
 Проверка выполняется, чтобы убедиться, что границ не `_Index` является допустимым индексом в параллельном векторе.  
  
##  <a name="push_back"></a> push_back 

 Добавляет заданный элемент в конец параллельного вектора. Данный метод безопасен в режиме параллелизма.  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>Параметры  
 `_Item`  
 Добавляемое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Добавить итератор для элемента.  
  
##  <a name="rbegin"></a> rbegin 

 Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` параллельный вектор в начало. Данный метод безопасен в режиме параллелизма.  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `reverse_iterator` или `const_reverse_iterator` параллельный вектор в начало.  
  
##  <a name="rend"></a> rend 

 Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` в конец параллельный вектор. Данный метод безопасен в режиме параллелизма.  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор типа `reverse_iterator` или `const_reverse_iterator` в конец параллельный вектор.  
  
##  <a name="reserve"></a> Резерв 

 Выделяет достаточно места для увеличения параллельного вектора до размера `_N` без необходимости выделить больше памяти позднее. Этот метод не является безопасным в режиме параллелизма.  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>Параметры  
 `_N`  
 Число элементов для резервирования пространства.  
  
### <a name="remarks"></a>Примечания  
 `reserve` не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методы на параллельный вектор при вызове этого метода. Емкость параллельного вектора после возврата метода может быть больше запрошенного резервирования.  
  
##  <a name="resize"></a> Изменение размеров 

 Изменяет размер параллельного вектора до запрошенного размера, удалении или добавлении элементов при необходимости. Этот метод не является безопасным в режиме параллелизма.  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>Параметры  
 `_N`  
 Новый размер concurrent_vector.  
  
 `val`  
 Значение новых элементов, добавленных в вектор, если новый размер больше исходного. Если значение задано, новые объекты назначаются по умолчанию для их типа.  
  
### <a name="remarks"></a>Примечания  
 Если размер контейнера меньше запрошенного размера, элементы добавляются в вектор, пока не достигнет требуемого размера. Если размер контейнера больше запрошенного размера, ближайший к концу контейнера элементы будут удалены, пока не достигнет размера контейнера `_N`. Если текущий размер контейнера совпадает с запрошенным, никакие действия не выполняются.  
  
 `resize` не является параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методы на параллельный вектор при вызове этого метода.  
  
##  <a name="shrink_to_fit"></a> shrink_to_fit 

 Сжимает внутреннее представление параллельного вектора, чтобы снизить уровень фрагментации и оптимизировать использование памяти. Этот метод не является безопасным в режиме параллелизма.  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод будет внутренне перераспределять элементы перемещения памяти, что делает недействительными все итераторы. `shrink_to_fit` не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, вызывающих методы на параллельный вектор при вызове этой функции.  
  
##  <a name="size"></a> Размер 

 Возвращает число элементов в параллельном векторе. Данный метод безопасен в режиме параллелизма.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в этом `concurrent_vector` объекта.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый размер гарантированно включить все элементы, добавленные вызовами функции `push_back`, операциями, выполненными до вызова этого метода. Тем не менее, он также может включать элементы, которые выделяются, но по-прежнему собираются параллельными вызовами методов увеличения.  
  
##  <a name="swap"></a> Поменять местами 

 Меняет местами содержимое двух параллельных векторов. Этот метод не является безопасным в режиме параллелизма.  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>Параметры  
 `_Vector`  
 `concurrent_vector` Объекта для обмена содержимым.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)



