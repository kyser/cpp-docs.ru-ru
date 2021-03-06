---
title: Класс Module::ReleaseNotifier | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76edb403fae12dd8b6221d8bd6ec82424bc5a4f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="modulereleasenotifier-class"></a>Класс Module::ReleaseNotifier
Вызывает обработчик событий при освобождении последнего объекта в модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Деструктор Module::ReleaseNotifier::~ReleaseNotifier](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Деинициализирует текущий экземпляр класса Module::ReleaseNotifier.|  
|[Конструктор Module::ReleaseNotifier::ReleaseNotifier](../windows/module-releasenotifier-releasenotifier-constructor.md)|Инициализирует новый экземпляр класса Module::ReleaseNotifier.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Module::ReleaseNotifier::Invoke](../windows/module-releasenotifier-invoke-method.md)|При реализации вызывает обработчик событий при освобождении последнего объекта в модуле.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Удаляет текущий объект Module::ReleaseNotifier, если объект был создан с параметром `true`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)