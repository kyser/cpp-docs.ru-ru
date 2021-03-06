---
title: Класс CComSafeArray | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c7c4e0603d70513194f8672752ec704011e8326
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomsafearray-class"></a>Класс CComSafeArray
Этот класс является оболочкой для структуры **SAFEARRAY** .  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных для сохранения в массиве.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Конструктор.|  
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|Добавляет один или несколько элементов или структуру **SAFEARRAY** в `CComSafeArray`.|  
|[CComSafeArray::Attach](#attach)|Прикрепляет структуру **SAFEARRAY** к объекту `CComSafeArray` .|  
|[CComSafeArray::CopyFrom](#copyfrom)|Копирует содержимое структуры **SAFEARRAY** в объект `CComSafeArray` .|  
|[CComSafeArray::CopyTo](#copyto)|Создает копию объекта `CComSafeArray` .|  
|[CComSafeArray::Create](#create)|Создает объект `CComSafeArray`.|  
|[CComSafeArray::Destroy](#destroy)|Уничтожает объект `CComSafeArray`.|  
|[CComSafeArray::Detach](#detach)|Отсоединяет структуру **SAFEARRAY** от объекта `CComSafeArray` .|  
|[CComSafeArray::GetAt](#getat)|Получает один элемент из одномерного массива.|  
|[CComSafeArray::GetCount](#getcount)|Возвращает число элементов в массиве.|  
|[CComSafeArray::GetDimensions](#getdimensions)|Возвращает число измерений в массиве.|  
|[CComSafeArray::GetLowerBound](#getlowerbound)|Возвращает нижнюю границу заданного измерения массива.|  
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Возвращает адрес элемента данных `m_psa` .|  
|[CComSafeArray::GetType](#gettype)|Возвращает тип данных, хранящихся в массиве.|  
|[CComSafeArray::GetUpperBound](#getupperbound)|Возвращает верхнюю границу любого измерения массива.|  
|[CComSafeArray::IsSizable](#issizable)|Проверяет, можно ли изменить размер объекта `CComSafeArray` .|  
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Получает один элемент из многомерного массива.|  
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Задает значение элемента в многомерном массиве.|  
|[CComSafeArray::Resize](#resize)|Изменяет размер объекта `CComSafeArray` .|  
|[CComSafeArray::SetAt](#setat)|Задает значение элемента в одномерном массиве.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Приводит значение к указателю **SAFEARRAY** .|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Получает элемент из массива.|  
|[CComSafeArray::operator =](#operator_eq)|Оператор присвоения.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|Этот элемент данных содержит адрес структуры **SAFEARRAY** .|  
  
## <a name="remarks"></a>Примечания  
 `CComSafeArray` предоставляет оболочку для класса [SAFEARRAY Data Type](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) , упрощая создание одно- и многомерных массивов практически любого поддерживаемого типа VARIANT и управление ими.  
  
 `CComSafeArray` упрощает передачу массивов между процессами и обеспечивает дополнительную безопасность путем проверки значений индекса массива на соответствие верхней и нижней границам.  
  
 Нижняя граница `CComSafeArray` может начинаться с любого определенного пользователем значения. Однако нижняя граница массивов, доступ к которым осуществляется через C++, должна быть равна 0. В других языках, например Visual Basic, могут использоваться другие ограничивающие значения (например, от −10 до 10).  
  
 Используйте [CComSafeArray::Create](#create) для создания объекта `CComSafeArray` , и [CComSafeArray::Destroy](#destroy) — для его удаления.  
  
 `CComSafeArray` может содержать следующее подмножество типов данных VARIANT.  
  
|VARTYPE|Описание|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|указатель типа decimal|  
|VT_VARIANT|указатель типа variant|  
|VT_CY|Currency - тип данных|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsafe.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="add"></a>  CComSafeArray::Add  
 Добавляет один или несколько элементов или структуру **SAFEARRAY** в `CComSafeArray`.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `psaSrc`  
 Указатель на **SAFEARRAY** объекта.  
  
 `ulCount`  
 Количество объектов, добавляемых в массив.  
  
 *pT*  
 Указатель на один или несколько объектов, добавляемый в массив.  
  
 *t*  
 Ссылка на объект, добавляемый в массив.  
  
 `bCopy`  
 Указывает, следует ли создавать копию данных. Значение по умолчанию — **TRUE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Новые объекты добавляются в конец существующего **SAFEARRAY** объекта. При добавлении объекта многомерный массив **SAFEARRAY** объекта не поддерживается. При добавлении существующего массива объектов, оба массива должен содержать элементов того же типа.  
  
 `bCopy` Учитывается флаг при элементов типа `BSTR` или **VARIANT** добавляются в массив. Значение по умолчанию **TRUE** гарантирует новую копию данных, при добавлении элемента в массиве.  
  
##  <a name="attach"></a>  CComSafeArray::Attach  
 Прикрепляет структуру **SAFEARRAY** к объекту `CComSafeArray` .  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `psaSrc`  
 Указатель на **SAFEARRAY** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Присоединяет **SAFEARRAY** структуру `CComSafeArray` объекта, делая ее `CComSafeArray` доступные методы.  
  
##  <a name="ccomsafearray"></a>  CComSafeArray::CComSafeArray  
 Конструктор.  
  
```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `bound`  
 Объект **SAFEARRAYBOUND** структуры.  
  
 `ulCount`  
 Количество элементов в массиве.  
  
 `lLBound`  
 Значение нижней границы; то есть индекс первого элемента в массиве.  
  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** структуры.  
  
 `uDims`  
 Число измерений в массиве.  
  
 `saSrc`  
 Ссылку на **SAFEARRAY** структуры или `CComSafeArray` объекта. В любом случае конструктор использует эту ссылку для создания копии массива, поэтому после создания отсутствуют ссылки на массив.  
  
 `psaSrc`  
 Указатель на **SAFEARRAY** структуры. Конструктор использует данный адрес для создания копии массива, поэтому после создания отсутствуют ссылки на массив.  
  
### <a name="remarks"></a>Примечания  
 Создает объект `CComSafeArray`.  
  
##  <a name="dtor"></a>  CComSafeArray:: ~ CComSafeArray  
 Деструктор  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="copyfrom"></a>  CComSafeArray::CopyFrom  
 Копирует содержимое структуры **SAFEARRAY** в объект `CComSafeArray` .  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Параметры  
 `ppArray`  
 Указатель на **SAFEARRAY** для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует содержимое **SAFEARRAY** в текущий `CComSafeArray` объекта. Заменяет существующее содержимое массива.  
  
##  <a name="copyto"></a>  CComSafeArray::CopyTo  
 Создает копию объекта `CComSafeArray` .  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Параметры  
 `ppArray`  
 Указатель на расположение, в котором будет создан новый **SAFEARRAY**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует содержимое `CComSafeArray` объекта в **SAFEARRAY** структуры.  
  
##  <a name="create"></a>  CComSafeArray::Create  
 Создает объект `CComSafeArray`.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** объекта.  
  
 `uDims`  
 Число измерений в массиве.  
  
 `ulCount`  
 Количество элементов в массиве.  
  
 `lLBound`  
 Значение нижней границы; то есть индекс первого элемента в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Объект `CComSafeArray` объект может быть создан из существующего **SAFEARRAYBOUND** структуры и число измерений или путем указания числа элементов в массиве, а нижняя граница. Если массив должен быть получен из Visual C++, нижняя граница должно быть равно 0. Другие языки могут разрешить другие значения для нижней границы (например, Visual Basic поддерживает массивы с элементами в диапазоне, например 10 до 10).  
  
##  <a name="destroy"></a>  CComSafeArray::Destroy  
 Уничтожает объект `CComSafeArray`.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Удаляет существующий `CComSafeArray` объект и все данные, которые он содержит.  
  
##  <a name="detach"></a>  CComSafeArray::Detach  
 Отсоединяет структуру **SAFEARRAY** от объекта `CComSafeArray` .  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на **SAFEARRAY** объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отсоединяет **SAFEARRAY** объекта из `CComSafeArray` объекта.  
  
##  <a name="getat"></a>  CComSafeArray::GetAt  
 Получает один элемент из одномерного массива.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>Параметры  
 `lIndex`  
 Индекс в массиве, чтобы вернуть значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент массива требуется.  
  
##  <a name="getcount"></a>  CComSafeArray::GetCount  
 Возвращает число элементов в массиве.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число элементов в массиве.  
  
### <a name="remarks"></a>Примечания  
 При использовании с многомерным массивом, этот метод возвращает количество элементов в определенное измерение.  
  
##  <a name="getdimensions"></a>  CComSafeArray::GetDimensions  
 Возвращает число измерений в массиве.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число измерений в массиве.  
  
##  <a name="getlowerbound"></a>  CComSafeArray::GetLowerBound  
 Возвращает нижнюю границу заданного измерения массива.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива, для которого нужно получить нижняя граница. Если не указано, значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нижнюю границу.  
  
### <a name="remarks"></a>Примечания  
 Если нижняя граница — 0, это указывает массивом типа C, первым элементом является элемент с номером 0. В случае ошибки, например, аргумент Недопустимое измерение, этот метод вызывает метод `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
##  <a name="getsafearrayptr"></a>  CComSafeArray::GetSafeArrayPtr  
 Возвращает адрес элемента данных `m_psa` .  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на [CComSafeArray::m_psa](#m_psa) члена данных.  
  
##  <a name="gettype"></a>  CComSafeArray::GetType  
 Возвращает тип данных, хранящихся в массиве.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип данных, хранящихся в массиве, который может принимать одно из следующих типов:  
  
|VARTYPE|Описание|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|указатель типа decimal|  
|VT_VARIANT|указатель типа variant|  
|VT_CY|Currency - тип данных|  
  
##  <a name="getupperbound"></a>  CComSafeArray::GetUpperBound  
 Возвращает верхнюю границу любого измерения массива.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `uDim`  
 Измерение массива, для которого необходимо получить значение верхней границы. Если не указано, значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает верхнюю границу. Это значение является включительным, максимальный допустимый индекс для этого измерения.  
  
### <a name="remarks"></a>Примечания  
 В случае ошибки, например, аргумент Недопустимое измерение, этот метод вызывает метод `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
##  <a name="issizable"></a>  CComSafeArray::IsSizable  
 Проверяет, можно ли изменить размер объекта `CComSafeArray` .  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CComSafeArray` можно изменять, **false** Если это невозможно.  
  
##  <a name="m_psa"></a>  CComSafeArray::m_psa  
 Содержит адрес **SAFEARRAY** доступ к структуре.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt  
 Получает один элемент из многомерного массива.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>Параметры  
 `alIndex`  
 Указатель на объект vector индексов для каждого измерения в массиве. Крайний левый измерение (наиболее значимых) является `alIndex[0]`.  
  
 *t*  
 Ссылка на возвращаемые данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt  
 Задает значение элемента в многомерном массиве.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>Параметры  
 `alIndex`  
 Указатель на объект vector индексов для каждого измерения в массиве. Крайнее правое измерение (младших) является `alIndex`[0].  
  
 *T*  
 Указывает значение нового элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Это многомерный версия [CComSafeArray::SetAt](#setat).  
  
##  <a name="operator_at"></a>  CComSafeArray::operator \[\]  
 Получает элемент из массива.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>Параметры  
 *Индекс, nIndex*  
 Номер индекса обязательный элемент в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает элемент, соответствующий массив.  
  
### <a name="remarks"></a>Примечания  
 Выполняет те же функции для [CComSafeArray::GetAt](#getat), однако этот оператор работает только с одномерные массивы.  
  
##  <a name="operator_eq"></a>  CComSafeArray::operator =  
 Оператор присвоения.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `saSrc`  
 Ссылка на объект `CComSafeArray`.  
  
 `psaSrc`  
 Указатель на **SAFEARRAY** объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип данных, хранящихся в массиве.  
  
##  <a name="operator_lpsafearray"></a>  CComSafeArray::operator LPSAFEARRAY  
 Приводит значение к указателю **SAFEARRAY** .  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приводит значение к указателю **SAFEARRAY** .  
  
##  <a name="resize"></a>  CComSafeArray::Resize  
 Изменяет размер объекта `CComSafeArray` .  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pBound`  
 Указатель на **SAFEARRAYBOUND** структуру, содержащую сведения на количество элементов, а нижняя граница массива.  
  
 `ulCount`  
 Запрошенное количество объектов в массиве с измененным размером.  
  
 `lLBound`  
 Нижняя граница.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет только крайнее правое измерение. Массивы, которые возвращают размер не будет **IsResizable** как **false**.  
  
##  <a name="setat"></a>  CComSafeArray::SetAt  
 Задает значение элемента в одномерном массиве.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lIndex`  
 Номер индекса элемента в массиве.  
  
 *t*  
 Новое значение указанного элемента.  
  
 `bCopy`  
 Указывает, следует ли создавать копию данных. Значение по умолчанию — **TRUE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 `bCopy` Учитывается флаг при элементов типа `BSTR` или **VARIANT** добавляются в массив. Значение по умолчанию **TRUE** гарантирует новую копию данных, при добавлении элемента в массиве.  
  
## <a name="see-also"></a>См. также  
 [SAFEARRAY Data Type](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](#create)   
 [CComSafeArray::Destroy](#destroy)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
