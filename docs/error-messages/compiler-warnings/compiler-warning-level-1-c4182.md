---
title: Предупреждение (уровень 1) C4182 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4182
dev_langs:
- C++
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e86076a9d8218d08bd7437e2a06878b6ee91ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4182"></a>Предупреждение компилятора (уровень 1) C4182
\#включает уровень вложенности составляет «число»; возможна бесконечная рекурсия  
  
 Компилятору недостаточно места в куче из-за количества вложенных файлов include. Файл include является вложенным, когда он включается из другого файла include.  
  
 Это сообщение является информационным и предшествует ошибке [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md).