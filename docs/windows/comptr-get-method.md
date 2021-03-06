---
title: Метод ComPtr::Get | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Get
dev_langs:
- C++
helpviewer_keywords:
- Get method
ms.assetid: 078eee51-7bca-4924-a74b-cd4f6a05de31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da8c4446d10f87514ec49feef95d05df2de721f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptrget-method"></a>Метод ComPtr::Get
Извлекает указатель на интерфейс, который связан с данным объектом ComPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T* Get() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, связанный с данным объектом ComPtr.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)