---
title: Функция начала | Документы Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1a8c09e43613014b43ef4e3c075a54cdd90e08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="begin-function"></a>begin - функция
Возвращает итератор, указывающий на начало коллекции, для доступа к которой используется указанный параметр интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Коллекция вектора\<T > или VectorView\<T > объекты, к которым обращаются IVector\<T > или IVectorView\<T > интерфейса.  
  
 `i`  
 Коллекция произвольных объектов среды выполнения Windows, к которым обращаются IIterable\<T > интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, который указывает на начало коллекции.  
  
### <a name="remarks"></a>Примечания  
 Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.  
  
 Объект VectorIterator, который возвращается методом begin, является итератором прокси-сервера, хранящего элементы типа VectorProxy\<T >. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation:: Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)