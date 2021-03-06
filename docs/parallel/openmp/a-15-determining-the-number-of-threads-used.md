---
title: Определения количества потоков, используемых A.15 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b50858a3384fa5f8d867f13a699e1fc271c101ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Определение количества используемых потоков
Рассмотрим следующий пример неверные (для [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на странице 37):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()` Вызов возвращает значение 1 в последовательной раздел кода, таким образом *np* всегда будет равно 1 в предыдущем примере. Чтобы определить количество потоков, которые будут развернуты для параллельной области, внутри параллельной области должен быть вызов.  
  
 Приведенный ниже показано, как переписать этой программы без включения запрос для потоков:  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```