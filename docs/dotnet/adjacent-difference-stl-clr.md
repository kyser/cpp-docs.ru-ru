---
title: adjacent_difference (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::adjacent_difference
dev_langs:
- C++
helpviewer_keywords:
- adjacent_difference function
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fe926d375103ef0f9d1ac5afa56a52742512ace7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adjacentdifference-stlclr"></a>adjacent_difference (STL/CLR)
Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в диапазон назначения или вычисляет результат обобщенной процедуры, где операция разности заменена другой определенной бинарной операцией.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как числовая функция стандартной библиотеки C++ `adjacent_difference`. Дополнительные сведения см. в разделе [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/numeric >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)