---
title: Ошибка BSCMAKE BK1509 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825d1e1e119aa80445c5ae15804bbdde4a3d8bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1509"></a>Ошибка BSCMAKE BK1509
хватает размера кучи  
  
 BSCMAKE не хватило памяти, включая виртуальной памяти.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Освободите место на диске.  
  
2.  Увеличьте размер файла подкачки.  
  
3.  Увеличьте размер файла подкачки Windows.  
  
4.  Уменьшить размер памяти, требуемой BSCMAKE, с помощью параметров /Ei или/ES, чтобы исключить некоторые входные файлы или /Em, чтобы удалить тело макроса.