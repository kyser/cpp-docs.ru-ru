---
title: Неустранимая ошибка C1045 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78ff500d050fbb646dd97fc898279712fb750d9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1045"></a>Неустранимая ошибка C1045
ограничение компилятора: недопустимая степень вложения спецификаций компоновки  
  
 Превышено ограничение компилятора, касающееся вложенных внешних компонентов. Вложение внешних компонентов допускается для типов внешней компоновки, например `extern` "C++". Чтобы устранить эту ошибку, уменьшите число вложенных внешних компонентов.