---
title: Освобождение ресурсов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 960e19400ae1d00108d57eb85d3df01ebf1dbc33
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cleaning-up-resources"></a>Освобождение ресурсов
Во время выполнения обработчика завершения не всегда известно, какие ресурсы фактически выделены, прежде чем не будет вызван обработчик завершения. Возможно, блок операторов `__try` был интерпретирован до распределения всех ресурсов, поэтому не все ресурсы были открыты.  
  
 Таким образом, в целях безопасности прежде чем продолжить очистку обработки завершения, необходимо проверить, какие ресурсы фактически открыты. Ниже описана рекомендованная процедура.  
  
1.  Инициализируйте дескрипторы со значением null.  
  
2.  Распределите ресурсы в блоке операторов `__try`. Для дескрипторов устанавливается положительные значения по мере распределения ресурсов.  
  
3.  В блоке операторов `__finally` освободите все ресурсы, соответствующий дескриптор или переменная флага которых является ненулевыми или отличными от NULL.  
  
## <a name="example"></a>Пример  
 Например, в следующем коде используется обработчик завершения, чтобы закрыть три файла и блок памяти, выделенные в блоке операторов `__try`. Перед очисткой ресурса код сначала проверяет, был ли ресурс распределен.  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика завершения](../cpp/writing-a-termination-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)