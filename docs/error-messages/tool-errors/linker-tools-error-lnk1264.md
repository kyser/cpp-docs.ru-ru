---
title: Ошибка средств компоновщика LNK1264 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ed21327028fc9849f6e0694bb82ae34c6084842
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264
/ LTCG: PGINSTRUMENT указано, но не требуется создание кода; не удалось выполнить инструментирование  
  
 **/ LTCG: PGINSTRUMENT** был указан, но OBJ-файлы, скомпилированные с [/GL](../../build/reference/gl-whole-program-optimization.md). Инструментирование не могут принимать месте и отказ канала. Должен существовать хотя бы один OBJ-файл в командной строке, компилируется с помощью **/GL** , чтобы инструментирование могло произойти.  
  
 Профильная оптимизация (PGO) доступен только в 64-разрядных компиляторов.