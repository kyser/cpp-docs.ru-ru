---
title: Ошибка компилятора C2857 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2857
dev_langs:
- C++
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bb2ec5047646bea420bf109f18a72d87a8f7c44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2857"></a>Ошибка компилятора C2857
"#include" инструкция, указанная с Ycfilename командной строки не найден в исходном файле  
  
 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) параметр задает имя включаемого файла, который не включен в исходный файл, при компиляции.  
  
 Эта ошибка может быть вызвана `#include` оператор в блоке условной компиляции, который не компилируется.