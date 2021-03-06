---
title: Операторы ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75c9ffb8c918cce70ad1e150dd80cb07ebdd7b34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-operators"></a>Операторы ATL
В этом разделе содержатся разделы справки для глобальных операторов ATL.  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[оператор ==](#operator_eq_eq)|Сравнивает два `CSid` объектов или `SID` структуры на равенство.|  
|[оператор! =](#operator_neq)|Сравнивает два `CSid` объектов или `SID` структуры, чтобы определить их неравенство.|  
|[оператор <](#operator_lt)|Проверяет, может ли `CSid` объекта или `SID` — структура слева от оператора меньше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|  
|[оператор >](#operator_gt)|Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора больше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|  
|[оператор < =](#operator_lt__eq)|Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора меньше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|  
|[оператор > =](#operator_gt__eq)|Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора больше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h.  
  
##  <a name="operator_eq_eq"></a>  оператор ==  
 Сравнивает `CSid` объектов или `SID` структуры (идентификатором безопасности) для проверки на равенство.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны, **false** , если они не равны.  
  
##  <a name="operator_neq"></a>  оператор! =  
 Сравнивает `CSid` объектов или `SID` структуры (идентификатором безопасности) для проверки на неравенство.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты не равны, **false** если они равны.  
  
##  <a name="operator_lt"></a>  оператор <  
 Проверяет, может ли `CSid` объекта или `SID` — структура слева от оператора меньше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если адрес `lhs` меньше адрес `rhs` объекта, **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор выполняет действия по адресу `CSid` объекта или `SID` структура и реализован для обеспечения совместимости с классы коллекций стандартной библиотеки C++.  
  
##  <a name="operator_gt"></a>  оператор >  
 Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора больше, чем `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если адрес `lhs` больше, чем адрес `rhs`, **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор выполняет действия по адресу `CSid` объекта или `SID` структура и реализован для обеспечения совместимости с классы коллекций стандартной библиотеки C++.  
  
##  <a name="operator_lt__eq"></a>  оператор < =  
 Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора меньше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если адрес `lhs` меньше или равно адрес `rhs`, **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор выполняет действия по адресу `CSid` объекта или `SID` структура и реализован для обеспечения совместимости с классы коллекций стандартной библиотеки C++.  
  
##  <a name="operator_gt__eq"></a>  оператор > =  
 Проверяет, может ли `CSid` объекта или `SID` структура слева от оператора больше или равно `CSid` объекта или `SID` структура справа (для совместимости стандартной библиотеки C++).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый `CSid` объекта или `SID` структура для сравнения.  
  
 `rhs`  
 Второй `CSid` объекта или `SID` структура для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если адрес `lhs` больше или равно адрес `rhs`, **false** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор выполняет действия по адресу `CSid` объекта или `SID` структура и реализован для обеспечения совместимости с классы коллекций стандартной библиотеки C++.



