---
title: Метод VerifyInheritanceHelper::Verify | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 879f5fa117f0f2bc444243f540925d64a2b824b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="verifyinheritancehelperverify-method"></a>Метод VerifyInheritanceHelper::Verify
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static void Verify();  
```  
  
## <a name="remarks"></a>Примечания  
 Проверяет два интерфейса, указанный параметрами шаблона и определяет, является ли один интерфейс является производным от другого.  
  
 Если это условие не выполняется, выдается ошибка.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Verifyinheritancehelper-структура](../windows/verifyinheritancehelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)