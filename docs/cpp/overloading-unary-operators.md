---
title: Перегрузка унарных операторов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f242fac0d81c6d46c2d810bf07459fde2fb2ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="overloading-unary-operators"></a>Перегрузка унарных операторов
Перегрузке могут быть подвергнуты следующие унарные операторы.  
  
1.  `!` ([логическое не](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&` ([взятия адреса](../cpp/address-of-operator-amp.md))  
  
3.  `~` ([дополнения до единицы](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*` ([разыменование указателя](../cpp/indirection-operator-star.md))  
  
5.  `+` ([унарный плюс](../cpp/additive-operators-plus-and.md))  
  
6.  `-` ([Унарное отрицание](../cpp/additive-operators-plus-and.md))  
  
7.  `++` ([приращения](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--` ([уменьшения](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. операторы преобразования  
  
 Постфиксного оператора инкремента и декремента (`++` и **--**) рассматриваются отдельно в [увеличения и уменьшения](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Операторы преобразования также рассматриваются в отдельном разделе; в разделе [преобразования определяемого пользователем типа](../cpp/user-defined-type-conversions-cpp.md).  
  
 Следующие правила распространяются на все остальные унарные операторы. Чтобы объявить функцию унарного оператора как нестатический член, необходимо объявить ее в форме  
  
 `ret-type operator` `op` `()`  
  
 где `ret-type` — возвращаемый тип, а `op` — один из операторов, перечисленных в предыдущей таблице.  
  
 Чтобы объявить функцию унарного оператора как глобальную функцию, необходимо объявить ее в форме  
  
 `ret-type operator` `op` (`arg` )  
  
 где `ret-type` и `op` соответствуют описанию для функций-членов операторов, а `arg` — аргумент типа класса, с которым необходимо выполнить операцию.  
  
> [!NOTE]
>  Не существует ограничения на возвращаемые типы унарных операторов. Например, логическому НЕ (`!`) имеет смысл возвращать целочисленное значение, однако это не реализовано принудительно.  
  
## <a name="see-also"></a>См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)