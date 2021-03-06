---
title: Структура RuntimeClassBaseT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ea147ebddff03401f6151bcdc44d96efb233f90
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclassbaset-structure"></a>Структура RuntimeClassBaseT
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `RuntimeClassTypeT`  
 Поле флагов, которое указывает один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.  
  
## <a name="remarks"></a>Примечания  
 Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.  
  
## <a name="members"></a>Участники  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `RuntimeClassBaseT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Справочник (библиотека среды выполнения Windows)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)