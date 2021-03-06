---
title: 'Локализованные ресурсы в приложениях MFC: вспомогательные библиотеки DLL | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0740f567f17c8d44069211274ab1a4c66da311c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>Локализованные ресурсы в приложениях MFC. Вспомогательные библиотеки DLL
MFC версии 7.0 и более поздних версий обеспечивает расширенную поддержку спутниковой связи DLL и функцию, которая позволяет создавать приложения, локализированные на различные языки. Вспомогательная DLL — [Библиотеку ресурсов](../build/creating-a-resource-only-dll.md) , содержащий ресурсы приложения, локализованные для определенного языка. При запуске приложения с помощью MFC автоматически загружает локализованные ресурсы, соответствующие для среды. Например можно создать приложение с ресурсами на английском языке две вспомогательные библиотеки DLL, одна из которых содержит перевода для французского языка ресурсы, а в другом немецкого языков. При запуске приложения в системе английского языка, он использует ресурсы на английском языке. Если запустить в системе, он использует французские ресурсы; Если запустить немецком системе, он использует ресурсы на немецком языке.  
  
 Для поддержки локализованных ресурсов в приложениях MFC, попытки загрузить вспомогательную библиотеку DLL MFC которые содержат ресурсы, локализованные для конкретного языка. Вспомогательные DLL именуются *ApplicationNameXXX*DLL-файлы, где *ApplicationName* имя .exe или .dll, использующих MFC, и *XXX* трехбуквенный код для языка ресурсы (например, «ENU» или «DEU»).  
  
 MFC пытается загрузить DLL-Библиотеки ресурсов для каждого из языков в следующем порядке, найденная в одно:  
  
1. Текущий пользователь по умолчанию язык пользовательского интерфейса, возвращенный из GetUserDefaultUILanguage() Win32 API.  
  
2.  Язык пользовательского интерфейса по умолчанию текущего пользователя без конкретного варианта (то есть ENC [канадского английского] становится ENU [США На русском языке]).  
  
3.  Системный язык по умолчанию пользовательского интерфейса, возвращенный из GetSystemDefaultUILanguage() API. На других платформах это значение соответствует языку самой операционной системы.  
  
4.  Системный язык по умолчанию пользовательского интерфейса, без конкретного варианта.  
  
5.  Фиктивный язык с 3-буквенный код параметра LOC.  
  
 Если MFC не удается найти вспомогательные библиотеки DLL, в нем любые ресурсы, входящие в самом приложении.  
  
 Например предположим, что приложение LangExample.exe использует MFC и выполняется в системе с несколькими пользовательского интерфейса; Системный язык пользовательского интерфейса ― ENU [США На английском языке] и FRC [французский (Канада)] установлен язык пользовательского интерфейса текущего пользователя. MFC ищет следующие библиотеки DLL в следующем порядке:  
  
1.  LangExampleFRC.dll (язык интерфейса пользователя).  
  
2.  LangExampleFRA.dll (язык пользовательского интерфейса без конкретного варианта языка, в этом примере французский (Франция).  
  
3.  LangExampleENU.dll (языка пользовательского интерфейса системы).  
  
4.  LangExampleLOC.dll.  
  
 Если ни один из этих библиотек DLL не найдены, MFC использует ресурсы в LangExample.exe.  
  
## <a name="see-also"></a>См. также  
 [Библиотеки DLL в Visual C++](../build/dlls-in-visual-cpp.md)   
 [TN057. Локализация компонентов MFC](../mfc/tn057-localization-of-mfc-components.md)