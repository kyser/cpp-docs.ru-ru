---
title: преобразование (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::transform
dev_langs:
- C++
helpviewer_keywords:
- transform function [STL/CLR]
ms.assetid: 08940969-6d10-40e4-a35b-68dd801b3949
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2301cfbdcd60d60541c0240ced59d44a844b502f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transform-stlclr"></a>transform (STL/CLR)
Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и копирует возвращаемые значения объекта функции в диапазон назначения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `transform`. Дополнительные сведения см. в разделе [преобразования](../standard-library/algorithm-functions.md#transform).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)