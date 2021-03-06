---
title: _variant_t::Detach | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53d6dc51117ffe9b82511c6084e36bc49873b88
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Блок, относящийся только к системам Microsoft**  
  
 Отключает инкапсулированный **VARIANT** объекта из этого `_variant_t` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Инкапсулированный **VARIANT**.  
  
## <a name="remarks"></a>Примечания  
 Извлекает и возвращает инкапсулированный **VARIANT**, а затем очищает данный `_variant_t` объект без его удаления. Эта функция-член удаляет **VARIANT** из инкапсуляции и задает **VARTYPE** этого `_variant_t` объект `VT_EMPTY`. Можно освободить возвращаемый **VARIANT** путем вызова [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) функции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)