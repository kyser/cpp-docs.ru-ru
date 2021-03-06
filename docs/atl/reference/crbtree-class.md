---
title: Класс CRBTree | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b15ddf62545d5926faf75af760ed52219f1cb03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="crbtree-class"></a>Класс CRBTree
Этот класс предоставляет методы для создания и использования дерева красный-черный.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
```  
  
#### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа элемента.  
  
 *V*  
 Тип значения элемента.  
  
 `KTraits`  
 Код, используемый для копирования или перемещения элементов ключа. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значение.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента.|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|Тип, используемый при возврате ключ в виде выходного аргумент.|  
|[CRBTree::VINARGTYPE](#vinargtype)|Тип, используемый, когда значение передается в качестве входного аргумента.|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|Тип, используемый при передаче значения в виде выходного аргумент.|  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс CRBTree::CPair](#cpair_class)|Класс, содержащий ключ и значение элементов.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBTree:: ~ CRBTree](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Вызовите этот метод, чтобы определить позицию элемента, который использует следующего доступного ключа.|  
|[CRBTree::GetAt](#getat)|Этот метод вызывается для возвращения элемента в заданном положении в дереве.|  
|[CRBTree::GetCount](#getcount)|Этот метод вызывается для получения количества элементов в дереве.|  
|[CRBTree::GetHeadPosition](#getheadposition)|Вызовите этот метод, чтобы получить значение с расположением элемента на корневой узел дерева.|  
|[CRBTree::GetKeyAt](#getkeyat)|Этот метод используется для получения ключа из указанного положения в дереве.|  
|[CRBTree::GetNext](#getnext)|Этот метод вызывается для получения указателя на элемент, хранящийся в `CRBTree` объекта и перейти к следующему элементу позицию.|  
|[CRBTree::GetNextAssoc](#getnextassoc)|Этот метод вызывается для получения ключа и значения элементов, которые хранятся в схеме и перейти к следующему элементу позицию.|  
|[CRBTree::GetNextKey](#getnextkey)|Этот метод вызывается для получения ключа на элемент, хранящийся в дереве и перейти к следующему элементу позицию.|  
|[CRBTree::GetNextValue](#getnextvalue)|Этот метод вызывается для получения значения на элемент, хранящийся в дереве и перейти к следующему элементу позицию.|  
|[CRBTree::GetPrev](#getprev)|Этот метод вызывается для получения указателя на элемент, хранящийся в `CRBTree` объекта, а затем обновите положение до предыдущего элемента.|  
|[CRBTree::GetTailPosition](#gettailposition)|Вызовите этот метод, чтобы получить значение позиции элемента в конце дерева.|  
|[CRBTree::GetValueAt](#getvalueat)|Этот метод вызывается для получения значения, хранящиеся в заданном положении в `CRBTree` объекта.|  
|[CRBTree::IsEmpty](#isempty)|Этот метод используется для проверки дерева пустой объект.|  
|[CRBTree::RemoveAll](#removeall)|Этот метод вызывается для удаления всех элементов из **CRBTree** объекта.|  
|[CRBTree::RemoveAt](#removeat)|Этот метод вызывается для удаления элемента в заданном положении в **CRBTree** объекта.|  
|[CRBTree::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CRBTree` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Красный-Черный дерево является дерево двоичного поиска, которое использует дополнительный бита информации на узел, чтобы убедиться, что оно остается «,», является, то высота дерева не увеличиваться непропорционально большим и повлиять на производительность.  
  
 Этот класс шаблона предназначен для использования [CRBMap](../../atl/reference/crbmap-class.md) и [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Большая часть методы, которые составляют эти производные классы, предоставляемые `CRBTree`.  
  
 Более полное описание различных классов коллекций и их возможности и характеристики производительности см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cpair_class"></a>  Класс CRBTree::CPair  
 Класс, содержащий ключ и значение элементов.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс используется с помощью методов [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), и [CRBTree::GetPrev](#getprev) для доступа к элементам ключ и значение, хранящееся в структуре дерева.  
  
 Существуют следующие элементы.  
  
|||  
|-|-|  
|`m_key`|Элемент данных хранения ключа элемента.|  
|`m_value`|Элемент данных хранения значение элемента.|  
  
##  <a name="dtor"></a>  CRBTree:: ~ CRBTree  
 Деструктор  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные. Вызовы [CRBTree::RemoveAll](#removeall) для удаления всех элементов.  
  
##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter  
 Вызовите этот метод, чтобы определить позицию элемента, который использует следующего доступного ключа.  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Значение ключа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение позиции элемента, который использует следующего доступного ключа. Если нет дополнительных элементов, возвращается значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет проходить по дереву без необходимости заранее вычислить значения позиции.  
  
##  <a name="getat"></a>  CRBTree::GetAt  
 Этот метод вызывается для возвращения элемента в заданном положении в дереве.  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение позиции.  
  
 `key`  
 Переменная, получающая ключ.  
  
 *значение*  
 Переменная, принимающая значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первые две формы возвращают указатель на [CPair](#cpair_class). Третья форма получает ключ и значение для заданной позиции.  
  
### <a name="remarks"></a>Примечания  
 Значение позиции может быть ранее определено посредством вызова метода такие как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::GetTailPosition](#gettailposition).  
  
 В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
##  <a name="getcount"></a>  CRBTree::GetCount  
 Этот метод вызывается для получения количества элементов в дереве.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов (каждая пара ключ значение является один элемент), хранящихся в дереве.  
  
##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition  
 Вызовите этот метод, чтобы получить значение с расположением элемента на корневой узел дерева.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение позиции для элемента в корневой узел дерева.  
  
### <a name="remarks"></a>Примечания  
 Значение, возвращаемое `GetHeadPosition` можно использовать с методами таких как [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetNext](#getnext) для прохода по дереву и извлечения значений.  
  
##  <a name="getkeyat"></a>  CRBTree::GetKeyAt  
 Этот метод используется для получения ключа из указанного положения в дереве.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение позиции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ключ, хранящийся в позиции `pos` в дереве.  
  
### <a name="remarks"></a>Примечания  
 Если `pos` значение не является допустимой позицией, результаты будут непредсказуемыми. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
##  <a name="getnext"></a>  CRBTree::GetNext  
 Этот метод вызывается для получения указателя на элемент, хранящийся в `CRBTree` объекта и перейти к следующему элементу позицию.  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на следующий [CPair](#cpair_class) значение в дереве.  
  
### <a name="remarks"></a>Примечания  
 `pos` Позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в дереве `pos` имеет значение NULL.  
  
##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc  
 Этот метод вызывается для получения ключа и значения элементов, которые хранятся в схеме и перейти к следующему элементу позицию.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 `key`  
 Параметр шаблона, указывающий тип ключа дерева.  
  
 *значение*  
 Параметр шаблона, указывающий тип значения дерева.  
  
### <a name="remarks"></a>Примечания  
 `pos` Позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в дереве `pos` имеет значение NULL.  
  
##  <a name="getnextkey"></a>  CRBTree::GetNextKey  
 Этот метод вызывается для получения ключа на элемент, хранящийся в дереве и перейти к следующему элементу позицию.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на следующий ключ в дереве.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если нет дополнительных записей в дереве, счетчик позиции будет равно NULL.  
  
##  <a name="getnextvalue"></a>  CRBTree::GetNextValue  
 Этот метод вызывается для получения значения на элемент, хранящийся в дереве и перейти к следующему элементу позицию.  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на следующее значение в дереве.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если нет дополнительных записей в дереве, счетчик позиции будет равно NULL.  
  
##  <a name="getprev"></a>  CRBTree::GetPrev  
 Этот метод вызывается для получения указателя на элемент, хранящийся в `CRBTree` объекта, а затем обновите положение до предыдущего элемента.  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущий [CPair](#cpair_class) значения, хранящегося в дереве.  
  
### <a name="remarks"></a>Примечания  
 Обновляет текущий счетчик позиции `pos`. Если нет дополнительных записей в дереве, счетчик позиции будет равно NULL.  
  
##  <a name="gettailposition"></a>  CRBTree::GetTailPosition  
 Вызовите этот метод, чтобы получить значение позиции элемента в конце дерева.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение позиции элемента в конце дерева.  
  
### <a name="remarks"></a>Примечания  
 Значение, возвращаемое `GetTailPosition` можно использовать с методами таких как [CRBTree::GetKeyAt](#getkeyat) или [CRBTree::GetPrev](#getprev) для прохода по дереву и извлечения значений.  
  
##  <a name="getvalueat"></a>  CRBTree::GetValueAt  
 Этот метод вызывается для получения значения, хранящиеся в заданном положении в `CRBTree` объекта.  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на значение, хранящееся в заданном положении в `CRBTree` объекта.  
  
##  <a name="isempty"></a>  CRBTree::IsEmpty  
 Этот метод используется для проверки дерева пустой объект.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если дерево не указано, **false** в противном случае.  
  
##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE  
 Тип, используемый при передаче ключа в качестве входного аргумента.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE  
 Тип, используемый при возврате ключ в виде выходного аргумент.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CRBTree::RemoveAll  
 Этот метод вызывается для удаления всех элементов из `CRBTree` объекта.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Очищает `CRBTree` объект, память, используемую для хранения элементов.  
  
##  <a name="removeat"></a>  CRBTree::RemoveAt  
 Этот метод вызывается для удаления элемента в заданном положении в **CRBTree** объекта.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="remarks"></a>Примечания  
 Удаляет пара ключ значение, хранящиеся в указанной позиции. Память, используемая для сохранения элемента освобождается. ПОЗИЦИЯ ссылается `pos` становится недействительным, а пока положения других элементов в дереве остается действительным, это не обязательно хранить том же порядке.  
  
##  <a name="setvalueat"></a>  CRBTree::SetValueAt  
 Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CRBTree` объекта.  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Счетчик позиции, возвращенных предыдущего вызова методов, таких как [CRBTree::GetHeadPosition](#getheadposition) или [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 *значение*  
 Значение для добавления `CRBTree` объекта.  
  
### <a name="remarks"></a>Примечания  
 Изменяет значение элемента, хранимых в заданном положении в `CRBTree` объекта.  
  
##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE  
 Тип, используемый, когда значение передается в качестве входного аргумента.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE  
 Тип, используемый при передаче значения в виде выходного аргумент.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
