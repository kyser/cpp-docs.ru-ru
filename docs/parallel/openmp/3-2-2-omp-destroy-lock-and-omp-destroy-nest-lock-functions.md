---
title: 3.2.2 функции omp_destroy_lock и omp_destroy_nest_lock функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33c21ec9ca07651480748ac705ea6b9e4dcf8e94
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 Функции omp_destroy_lock и omp_destroy_nest_lock
Эти функции убедитесь, что указывает на блокировку переменной *блокировки* не инициализирован. Он следующий:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Он не соответствует требованиям для вызова одной из этих подпрограмм блокировку переменной, которая является не инициализирован или разблокировать.