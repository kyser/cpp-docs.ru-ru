---
title: Функция to_vector | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c345b594c284c1273a080d979cd9588aff350d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tovector-function"></a>Функция to_vector
Возвращает объект `std::vector`, значение которого совпадает с коллекцией, лежащей в основе указанного параметра IVector или IVectorView.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T>  
inline ::std::vector<T> to_vector(IVector<T>^ v); 
 
template <typename T>  
inline ::std::vector<T> to_vector(IVectorView<T>^ v);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Интерфейс IVector или IVectorView, который предоставляет доступ к базовому объекту Vector или VectorView.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation:: Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)