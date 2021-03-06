---
title: ComPtr::operator -&gt; оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3cb3571207f328ad044ffd3f2f9b83bcebc7677e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-gt-operator"></a>ComPtr::operator -&gt; оператор
Извлекает указатель на тип, заданный текущим параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на тип, заданный текущим именем типа шаблона.  
  
## <a name="remarks"></a>Примечания  
 Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция делает типы IUnknown частными вместо виртуальных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)