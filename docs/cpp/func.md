---
title: __Func__ | Документы Microsoft
ms.custom: ''
ms.date: 10/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __func__
dev_langs:
- C++
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d78a249fe5b111c17c29895edcdc3fa5ba2f27a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="func"></a>__func__

**(C ++ 11)**  Предопределенный идентификатор &#95; &#95;func&#95; &#95; неявно определяется как строка, которая содержит неполное и недекорируемое имя внешней функции. &#95;&#95;Func&#95; &#95; является обязательным компонентом стандарта C++ и не является расширением Майкрософт.

## <a name="syntax"></a>Синтаксис

```cpp
__func__
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает символом null const char массив символов, содержащий имя функции.

## <a name="example"></a>Пример

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>Требования

C++11