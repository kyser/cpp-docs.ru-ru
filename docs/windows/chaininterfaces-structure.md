---
title: Структура ChainInterfaces | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18814a4ad87cefa39201d369926c0778931d4d64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces - структура
Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `I0`  
 (Обязательно) Интерфейс с Идентификатором 0.  
  
 `I1`  
 (Обязательно) Идентификатор интерфейса 1.  
  
 `I2`  
 (Необязательно) Интерфейс с Идентификатором 2.  
  
 `I3`  
 (Необязательно) Идентификатор интерфейса 3.  
  
 `I4`  
 (Необязательно) Идентификатор интерфейса 4.  
  
 `I5`  
 (Необязательно) Идентификатор интерфейса 5.  
  
 `I6`  
 (Необязательно) Идентификатор интерфейса 6.  
  
 `I7`  
 (Необязательно) Идентификатор интерфейса 7.  
  
 `I8`  
 (Необязательно) Идентификатор интерфейса 8.  
  
 `I9`  
 (Необязательно) Идентификатор интерфейса 9.  
  
 `DerivedType`  
 Производный тип.  
  
 `BaseType`  
 Базовый тип производного типа.  
  
 `hasImplements`  
 Логическое значение, если `true`, значит, нельзя использовать [MixIn](../windows/mixin-structure.md) структуры с классом, который является производным от [реализует](../windows/implements-structure.md) структура.  
  
## <a name="members"></a>Участники  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ChainInterfaces::CanCastTo](../windows/chaininterfaces-cancastto-method.md)|Указывает ли идентификатор указанный интерфейс может быть приведен к каждой специализации, определяемая параметрами ChainInterface шаблона.|  
|[Метод ChainInterfaces::CastToUnknown](../windows/chaininterfaces-casttounknown-method.md)|Приводит указатель интерфейса типа, определяемого `I0` параметр шаблона в указатель на IUnknown.|  
|[Метод ChainInterfaces::FillArrayWithIid](../windows/chaininterfaces-fillarraywithiid-method.md)|Сохраняет идентификатор интерфейса определяются `I0` параметр шаблона в указанном месте в указанном массиве идентификаторов интерфейсов.|  
|[Метод ChainInterfaces::Verify](../windows/chaininterfaces-verify-method.md)|Проверяет, чтобы каждый интерфейс определены параметры шаблона `I0` через `I9` наследует от IUnknown или IInspectable и который `I0` наследует от `I1` через `I9`.|  
  
### <a name="protected-constants"></a>Защищенные константы  
  
|name|Описание|  
|----------|-----------------|  
|[Константа ChainInterfaces::IidCount](../windows/chaininterfaces-iidcount-constant.md)|Общее количество идентификаторов, содержащихся в интерфейсах, заданные параметры шаблона интерфейса `I0` через `I9`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)