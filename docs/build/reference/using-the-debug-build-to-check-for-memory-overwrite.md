---
title: Использование отладочного построения для проверки затирания памяти | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c89242a63484eaccd0330eddac28c4e543ec61b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Использование отладочного построения для проверки затирания памяти
Использование отладочного построения для проверки затирания памяти, то необходимо перестроить проект для отладки. Перейдите в самом начале приложения `InitInstance` функции и добавьте следующую строку:  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 Механизм распределения отладочной памяти устанавливает контрольные байты всех операций выделения памяти. Тем не менее, их защиты байт не принесет пользы, пока не проверите ли они были изменены (что указывает затирания памяти). В противном случае это просто предоставляет буфер, возможно на самом деле позволяет обойтись без перезаписи памяти.  
  
 Включив `checkAlwaysMemDF`, будет принудительно MFC, позволяющий вызвать `AfxCheckMemory` работать при каждом вызове **новый** или **удалить** выполняется. Если обнаружено затирания памяти, он создает сообщение ТРАССИРОВКИ, похожее на следующее:  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 Если отображается одно из следующих сообщений, необходимо пошаговое выполнение кода для определения, где произошло повреждение. Чтобы изолировать точнее перезаписи памяти возникновения, можно указать явные вызовы к `AfxCheckMemory` самостоятельно. Пример:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 Если выполняется оператор Assert в МЕТОДЕ, а вторая завершился неудачно, это означает, что происходит перезаписи памяти между этими двумя вызовами функции.  
  
 В зависимости от характера приложения, может оказаться, что `afxMemDF` программа работает слишком медленно для теста. `afxMemDF` Переменная `AfxCheckMemory` вызываться для каждого вызова, чтобы создать и удалить. В этом случае следует Точечная диаграмма собственные вызовы `AfxCheckMemory`(), как показано выше и попробуйте изолировать память перезаписать таким образом.  
  
## <a name="see-also"></a>См. также  
 [Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)