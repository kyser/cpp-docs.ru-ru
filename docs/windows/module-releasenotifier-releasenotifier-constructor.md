---
title: 'Конструктор Module::releasenotifier:: releasenotifier | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbf21e1abc88c0fac0b9d20653fdb45c3706466d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Конструктор Module::ReleaseNotifier::ReleaseNotifier
Инициализирует новый экземпляр класса Module::ReleaseNotifier.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `release`  
 `true` Удаление этого экземпляра при вызове метода Release; `false` не удалить этот экземпляр.  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)