---
title: Метод Semaphore::LOCK | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b4db212236da6c9fb320ff5a5e04f4e9f4a4c6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="semaphorelock-method"></a>Метод Semaphore::Lock
Ожидает, пока текущий объект или объект семафора, связанный с указанным дескриптором, не будет находиться в сигнальном состоянии или указанный интервал времени ожидания истечет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `milliseconds`  
 Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.  
  
 `h`  
 Дескриптор объекта семафора.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Details::SyncLockWithStatusT\<HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
[Класс Semaphore](../windows/semaphore-class.md)
 