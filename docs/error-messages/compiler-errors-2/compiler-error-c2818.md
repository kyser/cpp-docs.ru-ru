---
title: Ошибка компилятора C2818 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10d7f419d528fcd2445b82e29d92442002624909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818
Применение перегруженного «operator ->» является рекурсивным через тип «тип»  
  
 Переопределение оператор доступа к членам класса содержится рекурсивный `return` инструкции. Чтобы переопределить `->` оператор, необходимо переместить рекурсивную подпрограмму в отдельную функцию, которая вызывается из оператора переопределить функцию.