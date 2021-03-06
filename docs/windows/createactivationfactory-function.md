---
title: Функция CreateActivationFactory | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e842a13461757e26dd1aed663c590df4c1ba6c74
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory - функция
Создает фабрику, производящую экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 Сочетание одного или нескольких [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значений перечисления.  
  
 `entry`  
 Указатель на [CreatorMap](../windows/creatormap-structure.md) , содержащий сведения о параметра инициализации и регистрации `riid`.  
  
 `riid`  
 Ссылка на идентификатор интерфейса.  
  
 `ppFactory`  
 Если эта операция завершается успешно, указатель на фабрику активации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Если выдается ошибка утверждения параметр шаблона `Factory` не является производным от интерфейса представляет интерфейс IActivationFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)