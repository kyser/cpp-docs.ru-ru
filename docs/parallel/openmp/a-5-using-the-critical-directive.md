---
title: Критические директива Using а.5 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a5---using-the-critical-directive"></a>A.5   Использование директивы critical
Следующий пример включает несколько `critical` директивы ([раздел 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) на странице 18). В примере демонстрируется очереди модели, в котором задачи из очереди и работали. Чтобы защититься от нескольких потоков локальности ту же задачу, dequeuing операция должна быть в `critical` раздела. Две очереди в этом примере независимы, они будут защищены `critical` директив с разными именами *xaxis* и *ось y*.  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```