---
title: Ошибка компилятора C3610 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f58d66e9d3dacfa2c0b38eb84fe51e0813a892d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3610"></a>Ошибка компилятора C3610
«тип_значения»: тип значения должен быть «упакован» перед вызовом метода «метод» может быть  
  
 По умолчанию тип значения не в управляемой куче. Перед вызовом методов из классов среды выполнения .NET, такие как `Object`, необходимо переместить тип значения в управляемую кучу.  
  
 C3610 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  
