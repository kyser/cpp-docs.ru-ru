---
title: 'Класс Platform::Collections:: vectorviewiterator | Документы Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e01a6235ccd898e9ae732c89b9f9885db35151cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Класс Platform::Collections::VectorViewIterator
Предоставляет итератор библиотеки стандартных шаблонов для объектов, производных от среды выполнения Windows`IVectorView` интерфейса.  
  
 `ViewVectorIterator` — это итератор прокси-сервера, который хранит элементы типа `VectorProxy<T>`. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T>  
class VectorViewIterator;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Имя типа класса шаблона VectorViewIterator.  
  
### <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`difference_type`|Различие указателя (ptrdiff_t).|  
|`iterator_category`|Категория итератора произвольного доступа (::std::random_access_iterator_tag).|  
|`pointer`|Указатель на внутренний тип, необходимый для реализации итератора VectorViewIterator.|  
|`reference`|Ссылка на внутренний тип, необходимый для реализации итератора VectorViewIterator.|  
|`value_type`|Имя типа `T` .|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[VectorViewIterator::VectorViewIterator](#ctor)|Инициализирует новый экземпляр класса VectorViewIterator.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор VectorViewIterator::operator-](#operator-minus)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|  
|[Оператор VectorViewIterator::operator--](#operator-decrement)|Выполняет уменьшение текущего итератора VectorViewIterator.|  
|[Оператор VectorViewIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект VectorViewIterator от указанного объекта VectorViewIterator.|  
|[Оператор VectorViewIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором VectorViewIterator.|  
|[VectorViewIterator::operator\[\]](#operator-at)|Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.|  
|[Оператор VectorViewIterator::operator+](#operator-plus)|Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.|  
|[Оператор VectorViewIterator::operator++](#operator-increment)|Выполняет приращение текущего итератора VectorViewIterator.|  
|[Оператор VectorViewIterator::operator+=](#operator-plus-assign)|Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.|  
|[Оператор VectorViewIterator::operator<](#operator-less-than)|Указывает, действительно ли текущий объект VectorViewIterator меньше, чем указанный объект VectorViewIterator.|  
|[VectorViewIterator::operator\<=-оператор](#operator-less-than-or-equals)|Указывает, действительно ли текущий объект VectorViewIterator меньше указанного объекта VectorViewIterator или равен ему.|  
|[Оператор VectorViewIterator::operator-=](#operator-minus-assign)|Уменьшает текущий итератор VectorViewIterator на указанную величину смещения.|  
|[Оператор VectorViewIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.|  
|[Оператор VectorViewIterator::operator>](#operator-greater-than)|Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.|  
|[Оператор VectorViewIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.|  
|[Оператор VectorViewIterator::operator>=](#operator-greater-than-or-equals)|Указывает, действительно ли текущий объект VectorViewIterator больше указанного объекта VectorViewIterator или равен ему.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `VectorViewIterator`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  

## <a name="operator-arrow"></a>  VectorViewIterator::operator -&gt; оператор
Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, на который ссылается текущий итератор VectorViewIterator.  
  
 Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.  
  


## <a name="operator-decrement"></a>  VectorViewIterator::operator --оператор
Выполняет уменьшение текущего итератора VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
VectorViewIterator& operator--();  
VectorViewIterator operator--(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет уменьшение текущего итератора VectorViewIterator.  
  
### <a name="remarks"></a>Примечания  
 Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator перед его использованием.  
  
 Второй синтаксис выполняет уменьшение текущего итератора VectorViewIterator после его использования. `int` Тип во втором синтаксисе указывает операцию уменьшения после использования, не является операндом целочисленного типа.  
  


## <a name="operator-dereference"></a>  Оператор VectorViewIterator::operator *
Извлекает ссылку на элемент, указанный текущим итератором VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, указанный текущим итератором VectorIterator.  
  


## <a name="operator-equality"></a>  VectorViewIterator::operator ==-оператор
Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator==(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorViewIterator равен объекту `other`; в противном случае `false`.  
  


## <a name="operator-greater-than"></a>  VectorViewIterator::operator&gt; оператор
Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
bool operator>(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorViewIterator больше объекта `other`; в противном случае — значение `false`.  
  


## <a name="operator-greater-than-or-equals"></a>  VectorViewIterator::operator&gt;=-оператор
Указывает, является ли текущий объект VectorViewIterator большим или равным указанному объекту VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
bool operator>=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorViewIterator больше или равен объекту `other`, в противном случае — значение `false`.  
  


## <a name="operator-increment"></a>  VectorViewIterator::operator ++-оператор
Выполняет приращение текущего итератора VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый синтаксис выполняет приращение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет приращение текущего итератора VectorViewIterator.  
  
### <a name="remarks"></a>Примечания  
 Первый синтаксис выполняет приращение текущего итератора VectorViewIterator перед его использованием.  
  
 Второй синтаксис выполняет приращение текущего итератора VectorViewIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  


## <a name="operator-inequality"></a>  VectorViewIterator::operator! =-оператор
Указывает, отличен ли текущий объект VectorViewIterator от указанного объекта VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator!=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorViewIterator не равен `other`; в противном случае `false`.  
  


## <a name="operator-less-than"></a>  VectorViewIterator::operator&lt; оператор
Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
bool operator<(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator меньше объекта `other`, в противном случае — значение `false`.  
  


## <a name="operator-less-than-or-equals"></a>  VectorViewIterator::operator&lt;=-оператор
Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
bool operator<=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `other`  
 Другой объект VectorIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущий объект VectorIterator меньше или равно `other`; в противном случае `false`.  
  


## <a name="operator-minus"></a>  VectorViewIterator::operator--оператор
Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorViewIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Количество элементов.  
  
 `other`  
 Другой объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Синтаксис первого оператора возвращает объект VectorViewIterator, количество элементов которого меньше, чем у текущего объекта VectorViewIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorViewIterator и другим объектом VectorViewIterator, заданным параметром `other`.  
  


## <a name="operator-plus-equals"></a>  VectorViewIterator::operator +=-оператор
Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
VectorViewIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный VectorViewIterator.  
  


## <a name="operator-plus"></a>  VectorViewIterator::operator +-оператор
Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorViewIterator operator+(difference_type n) const;  
  
template <typename T>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Во втором синтаксисе — имя типа объекта VectorViewIterator.  
  
 `n`  
 Целочисленная величина смещения.  
  
 `i`  
 Во втором синтаксисе — объект VectorViewIterator.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от текущего объекта VectorViewIterator.  
  
 В втором синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от начала параметра `i`.  
  


## <a name="operator-minus-assign"></a>  VectorViewIterator::operator-=-оператор
Уменьшает текущий итератор VectorIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
VectorViewIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный VectorIterator.  
  


## <a name="operator-at"></a>  VectorViewIterator::operator\[\]
Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Целочисленная величина смещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, удаленный от текущего итератора VectorViewIterator на `n`.  
  


## <a name="ctor"></a>  Vectorviewiterator::vectorviewiterator-конструктор
Инициализирует новый экземпляр класса VectorViewIterator.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
  
VectorViewIterator();  
  
explicit VectorViewIterator(  
   Windows::Foundation::Collections::IVectorView<T>^ v  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `v`  
 Интерфейс IVectorView\<T > объекта.  
  
### <a name="remarks"></a>Примечания  
 Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса является явным конструктором, используемым для создания экземпляра класса VectorViewIterator из IVectorView\<T > объекта.  
  

  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)