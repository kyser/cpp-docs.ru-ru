---
title: 'Пошаговое руководство: Построение проекта (C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c8d04dc3692076b867302af0e793eaac7ed25cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-building-a-project-c"></a>Пошаговое руководство. Построение проекта (C++)
В этом пошаговом руководстве в код на языке Visual C++ умышленно вводится синтаксическая ошибка, чтобы ознакомиться с тем, как проявляется ошибка компиляции и как ее можно исправить. При компиляции проекта выдается сообщение об ошибке, указывающее на ее характер и место возникновения.  
  
## <a name="prerequisites"></a>Необходимые компоненты  
  
-   Это пошаговое руководство предполагает знание основ языка C++.  
  
-   Кроме того, предполагается, что вы выполнили ранее связанных пошаговых руководств, перечисленных в [с помощью интегрированной среды разработки Visual Studio для разработки классических приложений C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-compilation-errors"></a>Исправление ошибок компиляции  
  
1.  В файле TestGames.cpp удалите точку с запятой в последней строке, чтобы она выглядела следующим образом:  
  
     `return 0`  
  
2.  В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
3.  Сообщения в **список ошибок** окна указывает, что в сборке проекта произошла ошибка. Описание ошибки выгладит следующим образом:  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Чтобы просмотреть справочные сведения об этой ошибке, выделите его в **список ошибок** окно и нажмите клавишу F1.  
  
4.  Верните точку с запятой в конец строки с синтаксической ошибкой:  
  
     `return 0;`  
  
5.  В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
     Сообщения в **вывода** окна указывает, что проект успешно скомпилирован.  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>Следующие шаги  
 **Предыдущие:** [Пошаговое руководство: работа с проектами и решениями (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **далее:**[Пошаговое руководство: тестирование проекта (C++)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Сборка программ C/C++](../build/building-c-cpp-programs.md)