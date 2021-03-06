---
title: Использование стека | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6f711636089a6f2966002002220aac88cebe17a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="stack-usage"></a>Использование стека
Все памяти за пределами текущего адреса RSP считаются временными: операционная система или отладчик, могут быть перезаписаны эта память во время сеанса отладки пользователя или обработчик прерываний. Таким образом RSP всегда должен иметь значение перед попыткой чтения или записи значения в кадре стека.  
  
 В этом разделе описывается порядок выделения места в стеке для локальных переменных и **alloca** встроенная функция.  
  
-   [Выделение памяти в стеке](../build/stack-allocation.md)  
  
-   [Динамическое создание параметра области стека](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Типы функций](../build/function-types.md)  
  
-   [Выравнивание с помощью функции malloc](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)