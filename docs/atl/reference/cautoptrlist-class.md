---
title: Класс CAutoPtrList | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9101d66de6782d1a060a8acdfb0d02e9971bb9c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cautoptrlist-class"></a>Класс CAutoPtrList
Этот класс предоставляет методы, используемые при построении списка интеллектуальных указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Параметры  
 `E`  
 Тип указателя.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет конструктор и наследует методы из [CAtlList](../../atl/reference/catllist-class.md) и [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) для упрощения создания списка объектов хранения интеллектуальные указатели. Класс [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) предоставляет аналогичные функции для объекта array.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="cautoptrlist"></a>  CAutoPtrList::CAutoPtrList  
 Конструктор.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока по умолчанию 10.  
  
### <a name="remarks"></a>Примечания  
 Размер блока — это мера, объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlList](../../atl/reference/catllist-class.md)   
 [Класс CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
