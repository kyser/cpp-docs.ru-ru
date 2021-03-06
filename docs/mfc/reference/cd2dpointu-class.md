---
title: Класс CD2DPointU | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91496e96763ab8c79ae1c71d68b9ae8f8db15e50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dpointu-class"></a>Класс CD2DPointU
Программа-оболочка для `D2D1_POINT_2U`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Перегружен. Создает `CD2DPointU` из объекта `D2D1_POINT_2U` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPointU::operator CPoint](#operator_cpoint)|Преобразует `CD2DPointU` для `CPoint` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU  
 Создает объект CD2DPointU из объекта класса CWnd.  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Исходная точка  
  
 `uX`  
 Источник X  
  
 `uY`  
 Источник Y  
  
##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint  
 Преобразует CD2DPointU CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение точки D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
