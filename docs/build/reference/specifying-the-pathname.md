---
title: Указание пути | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dd121909fbe0aa2f9305b7bd5779b995a69719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-the-pathname"></a>Указание пути
Каждый параметр выходного файла принимает *pathname* аргумент, который можно указать расположение и имя для выходного файла. Аргумент может включать имя диска, каталог и имя файла. Пробелы между параметром и аргумента.  
  
 Если *pathname* включает имя файла без расширения, компилятор выдает выходные данные расширение по умолчанию. Если *pathname* включает каталог, но без имени файла, компилятор создает файл с именем по умолчанию в указанном каталоге. Имя по умолчанию основано на базовое имя исходного файла и расширение по умолчанию, в зависимости от типа выходного файла. Если не ставятся *pathname* полностью, компилятор создает файл с именем по умолчанию в каталоге по умолчанию.  
  
 Кроме того *pathname* аргумент может быть имя устройства (AUX, CON, PRN или NUL) вместо имени файла. Не используйте пробел между параметром и имя устройства или запятой как часть имени устройства.  
  
|Имя устройства|Представляет|  
|-----------------|----------------|  
|AUX|Дополнительное устройство|  
|CON|Консоль|  
|PRN|Принтер|  
|NUL|NULL-устройство (файл не создается)|  
  
## <a name="example"></a>Пример  
 Следующая командная строка отправляет файл сопоставления принтера:  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)