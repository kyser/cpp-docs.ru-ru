---
title: Предупреждение компилятора (уровень 1) C4399 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aedad6aed07a6056f74ad338037a7268c722627f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703724"
---
# <a name="compiler-warning-level-1-c4399"></a>Предупреждение компилятора (уровень 1) C4399

> "*символ*": символ для каждого процесса не следует помечать с помощью __declspec(dllimport) при компиляции с параметром/clr: pure

## <a name="remarks"></a>Примечания

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

Данные из образа в машинном коде с или изображение машинного кода и конструкции среды CLR не будут импортированы в чистом образе. Чтобы устранить это предупреждение, компиляция с **/CLR** (не **/CLR: pure**) или удалить `__declspec(dllimport)`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4399.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```