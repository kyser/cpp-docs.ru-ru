---
title: Flush (OpenMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Flush
dev_langs:
- C++
helpviewer_keywords:
- flush OpenMP directive
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6933c5d74e1277b209d15aefb93a159d55f93dd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="flush-openmp"></a>flush (OpenMP)
Указывает, что все потоки имеют одинаковое представление в памяти для всех общих объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp flush [(var)]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var` (необязательно)  
 Список разделенных запятыми переменные, представляющие объекты, которые требуется синхронизировать. Если `var` не указан, записываемых всю память.  
  
## <a name="remarks"></a>Примечания  
 **Flush** директива поддерживает без предложения OpenMP.  
  
 Дополнительные сведения см. в разделе [2.6.5 директива flush](../../../parallel/openmp/2-6-5-flush-directive.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
```Output  
Thread 0: read data  
Thread 1: process data  
data = 2  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)