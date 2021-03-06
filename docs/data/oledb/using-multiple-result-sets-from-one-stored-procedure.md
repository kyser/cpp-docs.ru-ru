---
title: Использование нескольких результирующих наборов одной хранимой процедуры | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6393901839e8450ebc45b11f1d4bd2250da2ca56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Использование нескольких результирующих наборов одной хранимой процедуры
Большинство хранимых процедур возвращают несколько результирующих наборов. Хранимые процедуры обычно включают одну или несколько инструкций select. Потребитель должен учитывать для обработки всех результирующих наборов.  
  
### <a name="to-handle-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
  
1.  Создание `CCommand` класса `CMultipleResults` в качестве аргумента шаблона и методом доступа по своему усмотрению. Как правило это динамический или ручной метод доступа. Если вы используете другой тип метода доступа, не можно определить выходных столбцов для каждого набора строк.  
  
2.  Выполните хранимую процедуру в обычном режиме и привяжите столбцы (в разделе [инструкции по выполнению выборки данных?](../../data/oledb/fetching-data.md)).  
  
3.  Используйте данные.  
  
4.  Вызовите `GetNextResult` на `CCommand` класса. Если доступен другой результирующий набор строк, `GetNextResult` возвращает значение S_OK и вы связывание столбцов при использовании метода доступа вручную. Если `GetNextResult` возвращает сообщение об ошибке существует результирующих наборов больше нет доступных.  
  
## <a name="see-also"></a>См. также  
 [Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)