---
title: _HAS_ITERATOR_DEBUGGING | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab2de61df8c4e22b1955e9fd4798b5128a3e12be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Этот макрос, который был заменен макросом [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включена ли функция отладки итераторов в отладочной сборке. По умолчанию отладка итераторов включена в отладочных сборках и отключена в окончательных сборках. Дополнительные сведения см. в статье [Debug Iterator Support](../standard-library/debug-iterator-support.md) (Поддержка итераторов при отладке).

> [!IMPORTANT]
> Непосредственное использование макроса `_HAS_ITERATOR_DEBUGGING` не рекомендуется. Вместо этого, для управления параметрами отладки итераторов используйте `_ITERATOR_DEBUG_LEVEL`. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Примечания

Чтобы включить отладку итераторов в отладочных сборках, установите для макроса `_ITERATOR_DEBUG_LEVEL` значение 2. Это эквивалентно ситуации, когда для `_HAS_ITERATOR_DEBUGGING` установлено значение 1, или макрос включен:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

для `_ITERATOR_DEBUG_LEVEL` нельзя установить значение 2 (и для `_HAS_ITERATOR_DEBUGGING` нельзя установить значение 1) в коммерческих сборках.

Чтобы отключить итераторы при отладке в отладочных сборках, установите для `_ITERATOR_DEBUG_LEVEL` значение 0 или 1. Это эквивалентно ситуации, когда для `_HAS_ITERATOR_DEBUGGING` установлено значение 0, или макрос выключен:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>См. также

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
