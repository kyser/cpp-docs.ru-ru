---
title: 'Класс Platform::Collections:: vectoriterator | Документы Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deaab183a092a073c6681004654312485959e924
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvectoriterator-class"></a>Класс Platform::Collections::VectorIterator
Предоставляет итератор библиотеки стандартных шаблонов для объектов, производных от интерфейса IVector среды выполнения Windows.  
  
 VectorIterator — это итератор прокси-сервера, хранящего элементы типа VectorProxy\<T >. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Имя типа класса шаблона VectorIterator.  
  
### <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`difference_type`|Различие указателя (ptrdiff_t).|  
|`iterator_category`|Категория итератора произвольного доступа (::std::random_access_iterator_tag).|  
|`pointer`|Указатель на внутренний тип, Platform::Collections::Details::VectorProxy\<T >, который требуется для реализации итератора VectorIterator.|  
|`reference`|Ссылка на внутренний тип, Platform::Collections::Details::VectorProxy\<T >,,, необходимые для реализации итератора VectorIterator.|  
|`value_type`|Имя типа `T` .|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|Инициализирует новый экземпляр класса VectorIterator.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор VectorIterator::operator-](#operator-minus)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|  
|[Оператор VectorIterator::operator--](#operator-decrement)|Выполняет уменьшение текущего итератора VectorIterator.|  
|[Оператор VectorIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.|  
|[Оператор VectorIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором VectorIterator.|  
|[VectorIterator::operator\[\]](#operator-at)|Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.|  
|[Оператор VectorIterator::operator+](#operator-plus)|Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.|  
|[Оператор VectorIterator::operator++](#operator-increment)|Выполняет увеличение текущего итератора VectorIterator.|  
|[Оператор VectorIterator::operator+=](#operator-plus-assign)|Увеличивает текущий итератор VectorIterator на указанную величину смещения.|  
|[Оператор VectorIterator::operator<](#operator-less-than)|Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.|  
|[VectorIterator::operator\<=-оператор](#operator-less-than-or-equals)|Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.|  
|[Оператор VectorIterator::operator-=](#operator-subtract-assign)|Уменьшает текущий итератор VectorIterator на указанную величину смещения.|  
|[Оператор VectorIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.|  
|[Оператор VectorIterator::operator>](#operator-greater-than)|Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.|  
|[Оператор VectorIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.|  
|[Оператор VectorIterator::operator>=](#operator-greater-than-or-equal)|Указывает, действительно ли текущий объект VectorIterator больше указанного объекта VectorIterator или равен ему.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `VectorIterator`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  

## <a name="operator-arrow"></a>  VectorIterator::operator -&gt; оператор
Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, на который ссылается текущий итератор VectorIterator.  
  
 Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.  
  


## <a name="operator-decrement"></a>  VectorIterator::operator --оператор
Выполняет уменьшение текущего итератора VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый синтаксис выполняет уменьшение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет уменьшение текущего итератора VectorIterator.  
  
### <a name="remarks"></a>Примечания  
 Первый синтаксис выполняет уменьшение текущего итератора VectorIterator перед его использованием.  
  
 Второй синтаксис выполняет уменьшение текущего итератора VectorIterator после его использования. `int` Тип во втором синтаксисе указывает операцию уменьшения после использования, не является операндом целочисленного типа.  
  


## <a name="operator-dereference"></a>  Оператор VectorIterator::operator *
Извлекает адрес элемента, указанного текущим итератором VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, указанный текущим итератором VectorIterator.  
  


## <a name="operator-equality"></a>  VectorIterator::operator ==-оператор
Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator равен объекту `other`, в противном случае — значение `false`.  
  


## <a name="operator-greater-than"></a>  VectorIterator::operator&gt; оператор
Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorIterator больше, чем `other`; в противном случае `false`.  
  


## <a name="operator-greater-than-or-equals"></a>  VectorIterator::operator&gt;=-оператор
Указывает, является ли текущий объект VectorIterator большим или равным указанному объекту VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator больше или равен объекту `other`, в противном случае — значение `false`.    


## <a name="operator-increment"></a>  Оператор VectorIterator::operator ++
Выполняет увеличение текущего итератора VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый синтаксис выполняет увеличение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет увеличение текущего итератора VectorIterator.  
  
### <a name="remarks"></a>Примечания  
 Первый синтаксис выполняет увеличение текущего итератора VectorIterator перед его использованием.  
  
 Второй синтаксис выполняет увеличение текущего итератора VectorIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  


## <a name="operator-inequality"></a>  VectorIterator::operator! =-оператор
Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorIterator не равен `other`; в противном случае `false`.  
  


## <a name="operator-less-than"></a>  VectorIterator::operator&lt; оператор
Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator меньше объекта `other`, в противном случае — значение `false`.  
  


## <a name="operator-less-than-or-equals"></a>  VectorIterator::operator&lt;=-оператор
Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorIterator меньше или равно `other`; в противном случае `false`.  
  


## <a name="operator-minus"></a>  VectorIterator::operator--оператор
Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Количество элементов.  
  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Синтаксис первого оператора возвращает объект VectorIterator, который является `n` элементов которого меньше, чем текущий объект VectorIterator. Синтаксис второго оператора возвращает количество элементов между текущим и `other` VectorIterator.  
  


## <a name="operator-plus-assign"></a>  VectorIterator::operator +=-оператор
Увеличивает текущий итератор VectorIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный VectorIterator.  
  


## <a name="operator-plus"></a>  ectorIterator::operator Operator +
Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Во втором синтаксисе — имя типа объекта VectorIterator.  
  
 `n`  
 Целочисленная величина смещения.  
  
 `i`  
 Во втором синтаксисе — объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от текущего объекта VectorIterator.  
  
 Во втором синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от начала параметра `i`.  
  
### <a name="remarks"></a>Примечания  
 Первый пример синтаксиса  
  


## <a name="operator-minus-equals"></a>  VectorIterator::operator-=-оператор
Уменьшает текущий итератор VectorIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный VectorIterator.  
  


## <a name="operator-at"></a>  VectorIterator::operator\[\]
Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, отстоящий от текущего итератора VectorIterator на `n` элементов.  
  


## <a name="ctor"></a>  Vectoriterator::vectoriterator-конструктор
Инициализирует новый экземпляр класса VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>Параметры  
 `v`  
 IVector\<T > объекта.  
  
### <a name="remarks"></a>Примечания  
 Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса является явным конструктором, используемым для создания экземпляра класса VectorIterator из IVector\<T > объекта.  
  


  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)