---
title: Неустранимая ошибка C1510 | Документы Microsoft
ms.custom: ''
ms.date: 04/11/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1510
dev_langs:
- C++
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f39a609e1621dab404ff79e49ade56a88277aa80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1510"></a>Неустранимая ошибка C1510
Не удается открыть языковой ресурс clui.dll  
  
 Компилятору не удается загрузить DLL языковой ресурс.  
  
Существуют две распространенные причины этой проблемы. При использовании 32-разрядный компилятор и средства, появится это сообщение об ошибке для крупных проектов, использующих более 2 ГБ памяти во время компоновки. Возможное решение на 64-разрядных системах Windows — использовать собственный 64-разрядный или кросс-компилятор и средства для создания кода. Это дает техническое преимущество больше памяти для 64-разрядных приложений. Если необходимо использовать 32-разрядный компилятор, так как выполняются в 32-разрядной системе, в некоторых случаях можно увеличить объем памяти, чтобы компоновщик 3 ГБ. Дополнительные сведения см. в разделе [настройки 4 ГБ: BCDEdit и Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) и [BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) команды.  

Другой распространенной причиной является установкой Visual Studio прервана или неполна. В этом случае запустите установщик еще раз для восстановления или переустановки Visual Studio.  
  