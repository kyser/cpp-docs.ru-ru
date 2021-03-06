---
title: Класс is_error_condition_enum | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01650db9c1aec141852f66a2f4e2f09f5d5e78ac
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="iserrorconditionenum-class"></a>Класс is_error_condition_enum

Представляет тип предиката, проверяющий перечисление [error_condition](../standard-library/error-condition-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <_Enum>
class is_error_condition_enum;
```

## <a name="remarks"></a>Примечания

Экземпляр этого [предиката типа](../standard-library/type-traits.md) содержит значение true, если тип `_Enum` является значением перечисления, подходящим для хранения в объекте типа `error_condition`.

Допускается добавление специализации в этот тип для определяемых пользователем типов.

## <a name="requirements"></a>Требования

**Заголовок:** \<system_error>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
