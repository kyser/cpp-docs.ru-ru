---
title: Предупреждение (уровень 3) C4622 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b82e87f37b50b8df727d043889cb35ca02d3f78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4622"></a>Предупреждение компилятора (уровень 3) C4622
перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"  
  
 Информация CodeView в указанном файле была утеряна при выполнении компиляции с параметром [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (использование предкомпилированных заголовков).  
  
 Переименуйте объектный файл (с использованием параметра [/Fo](../../build/reference/fo-object-file-name.md)) при создании или использовании файла предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.