---
title: Структура _ATL_WIN_MODULE70 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 587b115c428b0d82183abbec9f712ff06ea448f4
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="atlwinmodule70-structure"></a>Структура _ATL_WIN_MODULE70
Использовать в коде над окнами в ATL.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Участники  
 `cbSize`  
 Размер структуры, используемые для управления версиями.  
  
 `m_csWindowCreate`  
 Используется для сериализации доступа к коду окно регистрации. Используется внутренними механизмами ATL.  
  
 **m_pCreateWndList**  
 Используется для привязки windows в объекты. Используется внутренними механизмами ATL.  
  
 **m_rgWindowClassAtoms**  
 Используется для отслеживания регистрации класса окна, чтобы их можно было правильно отменена при завершении. Используется внутренними механизмами ATL.  
  
## <a name="remarks"></a>Примечания  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) определяется как typedef из `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../../atl/reference/atl-classes.md)





