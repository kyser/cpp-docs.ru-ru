---
title: Устранение потенциальных проблем при работе с многопотоковыми программами | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af4c1ca6a86b2cff457aee12e8337103ce7f42d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Устранение потенциальных проблем при работе с многопотоковыми программами
Существует несколько проблем, которые могут возникнуть при создании, связывание или выполнении многопотоковой программы на C. В следующей таблице описываются некоторые из наиболее распространенных проблем. (Обсуждение аналогичные с точки зрения MFC см. в разделе [Многопоточность: советы про программированию](../parallel/multithreading-programming-tips.md).)  
  
|Проблема|Возможная причина|  
|-------------|--------------------|  
|Можно получить, показывающая, что программа нарушения защиты в окне сообщения.|Многие ошибки программирования Win32 вызвать нарушение защиты. Основной причиной нарушения защиты является неявное присваивание данных пустому указателю. Так как это приведет к программа пытается получить доступ к памяти, который не принадлежит к нему, выдается нарушение защиты.<br /><br /> Для компиляции программы с отладочной информацией и запустите его с помощью отладчика среды Visual C++ является простой способ определения причины нарушения защиты. В случае нарушения защиты Windows передает управление отладчику и курсор располагается на строке, в которой она вызвана.|  
|В программе возникает множество ошибок компиляции и связывания.|Многие потенциальные проблемы можно устранить путем установки один из наибольших значений уровня предупреждений компилятора и просматривайте предупреждающие сообщения. С помощью уровень 3 или параметры уровня предупреждение уровня 4, можно обнаружить непреднамеренные преобразования данных, отсутствующие прототипы функций и использование функций, не удовлетворяющую стандарту ANSI.|  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)