---
title: Неустранимая ошибка C1126 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3ff02d69679074186e593d5e1c16bdf56d1052
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1126"></a>Неустранимая ошибка C1126
«Идентификатор»: автоматическое выделение памяти превышает размер  
  
 Место, выделенное для локальных переменных функции (а также ограниченный объем пространства, используемого компилятором, такие как дополнительные 20 б для изменяемых функций) превышает предел.  
  
 Чтобы исправить эту ошибку, используйте `malloc` или `new` для выделения больших объемов данных.