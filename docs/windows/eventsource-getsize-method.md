---
title: Метод EventSource::GetSize | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::GetSize
dev_langs:
- C++
helpviewer_keywords:
- GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60c52c711c85caa64c289937f39fe50ec18e1839
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="eventsourcegetsize-method"></a>Метод EventSource::GetSize
Возвращает число обработчиков событий, связанных с текущим объектом EventSource  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Количество обработчиков событий в [targets_](../windows/eventsource-targets-data-member.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс EventSource](../windows/eventsource-class.md)