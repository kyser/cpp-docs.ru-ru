---
title: Метод ActivationFactory::GetRuntimeClassName | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
dev_langs:
- C++
helpviewer_keywords:
- GetRuntimeClassName method
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6db270c88b4335be48016ff2b8bdcf2b5e3951cd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactorygetruntimeclassname-method"></a>Метод ActivationFactory::GetRuntimeClassName
Возвращает имя класса среды выполнения объекта, который создает экземпляр текущего ActivationFactory.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### <a name="parameters"></a>Параметры  
 `runtimeName`  
 После завершения этой операции представляет дескриптор строка, содержащая имя класса среды выполнения объекта, который создает экземпляр текущего ActivationFactory.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)