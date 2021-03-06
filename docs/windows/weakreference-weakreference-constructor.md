---
title: Конструктор WeakReference::WeakReference | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference, constructor
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e60b23a0c63ce1415765dd1f94863540849f975
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="weakreferenceweakreference-constructor"></a>Конструктор WeakReference::WeakReference
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр [класс WeakReference](../windows/weakreference-class1.md).  
  
 Указатель строгую ссылку для объекта WeakReference инициализируется `nullptr`, и число строгую ссылку устанавливается равным 1.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
    
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)