---
title: Класс SafeIntException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 961fc2f2050336469f5944f603c0db3c6291a176
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="safeintexception-class"></a>Класс SafeIntException
`SafeInt` Класс использует `SafeIntException` чтобы определить, почему математические операции невозможно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class SafeIntException;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 Создает объект `SafeIntException`.  
  
## <a name="remarks"></a>Примечания  
 [Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует `SafeIntException` класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [Класс SafeIntException](../windows/safeintexception-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)