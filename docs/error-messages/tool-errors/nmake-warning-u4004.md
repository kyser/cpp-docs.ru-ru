---
title: Предупреждение программы NMAKE U4004 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532abf2f62616d6e748c9a4e34f5c983f0853276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-warning-u4004"></a>Предупреждение программы NMAKE U4004
слишком много правил для целевого «targetname»  
  
 Было указано более одного блока описания для заданного целевого объекта с использованием одиночных двоеточий (**:**) в качестве разделителей. NMAKE выполнения команды первого блока описания и не последующих блоков.  
  
 Чтобы указать одного целевого объекта в несколько зависимостей, следует использовать двойные двоеточия (`::`) в качестве разделителя в каждой строке зависимости.