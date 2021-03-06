---
title: Предупреждение средств компоновщика LNK4092 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72edd9e75dbc781355396e38f767a64c1ded3aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4092"></a>Предупреждение средств компоновщика LNK4092
Общий доступный для записи раздел «раздел» содержит перемещения; образ может неправильно выполняться  
  
 Компоновщик выдает это предупреждение, если у вас есть общий раздел, чтобы сообщить о потенциальных проблемах.  
  
 Для передачи данных между несколькими процессами можно отметить раздел как «общий». Однако создание раздела как общего может вызвать проблемы. Например имеется библиотеку DLL, которая содержит объявления в разделе общих данных:  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 Компоновщик не может разрешить `pvar` , так как его значение зависит от того, когда библиотека DLL загружается в память, следовательно, помещает запись о перемещении в библиотеку DLL. Если библиотека DLL загружается в память, адрес `var` может быть разрешено и `pvar` назначен. Если другой процесс загружает ту же библиотеку DLL, но не удается загрузить ее в то же адрес, перемещение адреса `var` будет обновлено для второго процесса и пространство адресов первого процесса будут указывать на неправильный адрес.