---
title: Класс _bstr_t | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bea9f863df08342f17419a16b14579fa6a257b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bstrt-class"></a>Класс _bstr_t
**Блок, относящийся только к системам Microsoft**  
  
 Объект `_bstr_t` объект инкапсулирует [данные типа BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228). Этот класс управляет выделением и освобождением посредством вызовов функций для ресурсов **SysAllocString** и **SysFreeString** и других `BSTR` API-интерфейсы, когда это необходимо. Класс `_bstr_t` использует подсчет ссылок во избежание слишком большой нагрузки.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Создает объект `_bstr_t`.|  
  
### <a name="operations"></a>Операции  
  
|||  
|-|-|  
|[Назначение](../cpp/bstr-t-assign.md)|Копирует строку `BSTR` в строку `BSTR`, инкапсулированную объектом `_bstr_t`.|  
|[Attach](../cpp/bstr-t-attach.md)|Связывает упаковщик `_bstr_t` со строкой `BSTR`.|  
|[copy](../cpp/bstr-t-copy.md)|Создает копию инкапсулированного объекта `BSTR`.|  
|[Detach](../cpp/bstr-t-detach.md)|Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|Указывает на строку `BSTR`, инкапсулированную объектом `_bstr_t`.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.|  
|[length](../cpp/bstr-t-length.md)|Возвращает число символов в объекте `_bstr_t`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../cpp/bstr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_bstr_t`.|  
|[оператор +=](../cpp/bstr-t-operator-add-equal-plus.md)|Добавляет символы в конец объекта `_bstr_t`.|  
|[Оператор +](../cpp/bstr-t-operator-add-equal-plus.md)|Объединяет две строки.|  
|[Оператор !](../cpp/bstr-t-operator-logical-not.md)|Проверяет, если инкапсулированный `BSTR` — **NULL** строки.|  
|[оператор ==,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|Сравнивает два объекта `_bstr_t`.|  
|[оператор wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Извлекает указатели на инкапсулированный объект Юникода или многобайтовый объект `BSTR`.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<comutil.h >  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)