---
title: Ошибка средств компоновщика LNK1106 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3dedaa2bd500b11f06f9cfa98802fdd6ca84534
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1106"></a>Ошибка средств компоновщика LNK1106
Недопустимый файл или нет места на диске: не удается обратиться к расположению  
  
 Средство не удалось чтение или запись `location` в файле памяти.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Диск заполнен.  
  
     Освободите место на диске и связывать их еще раз.  
  
2.  Попытка выполнить компоновку по сети.  
  
     Некоторые сети не полностью поддерживают сопоставленные в памяти файлы, используемые компоновщиком. Попытайтесь выполните компоновку на локальном диске.  
  
3.  Поврежденный блок на диске.  
  
     Несмотря на то, что операционная система и оборудование диска должны обнаруживать такие ошибки, можно запустить программу проверки диска.  
  
4.  Недостаточно места в куче.  
  
     В разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) для получения дополнительной информации.