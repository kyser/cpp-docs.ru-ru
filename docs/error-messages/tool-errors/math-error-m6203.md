---
title: Математическая ошибка M6203 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6203
dev_langs:
- C++
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7660284f9e5e69b53f3289eaa1aa424944bbecb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6203"></a>Математическая ошибка M6203
«функция»: ошибка _OVERFLOW  
  
 Результат заданной функции слишком велико для представления.  
  
 Эта ошибка вызывает `_matherr` функция с именем функции, ее аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок во время выполнения вычисления с плавающей запятой.