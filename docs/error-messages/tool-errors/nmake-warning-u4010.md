---
title: Предупреждение программы NMAKE U4010 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4010
dev_langs:
- C++
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8c99bb4a9b5daf7f630771d0f240479aaf5f3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-warning-u4010"></a>Предупреждение программы NMAKE U4010
«целевой объект»: построение выполнить не удалось; Указан, продолжение...  
  
 Команда в блоке команд для данного целевого объекта вернула ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.  
  
 Если данный целевой объект сам по себе, является зависимостью для другого целевого объекта, NMAKE выдает предупреждение [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) после этого предупреждения.