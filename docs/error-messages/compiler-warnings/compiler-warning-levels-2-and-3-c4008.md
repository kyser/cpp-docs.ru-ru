---
title: Предупреждение (уровни 2 и 3) C4008 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cdc88f222f9e5ce3829a63c131c955ce2abdd7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Предупреждение компилятора (уровни 2 и 3) C4008
"идентификатор": атрибут "атрибут" игнорируется  
  
 Компилятор игнорировал атрибут `__fastcall`, **static**или **inline** для функции (предупреждение уровня 3) или данных (предупреждение уровня 2).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Атрибут`__fastcall` с данными.  
  
2.  Атрибут**static** или **inline** с функцией **main** .