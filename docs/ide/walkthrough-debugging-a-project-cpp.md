---
title: 'Пошаговое руководство: Отладка проекта (C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-a-project-c"></a>Пошаговое руководство. Отладка проекта (C++)
В этом пошаговом руководстве рассматривается изменение программы для устранения проблем, обнаруженных при проверке проекта.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Это пошаговое руководство предполагает знание основ языка C++.  
  
-   Кроме того, предполагается, что вы выполнили ранее связанных пошаговых руководств, перечисленных в [с помощью интегрированной среды разработки Visual Studio для разработки классических приложений C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>Чтобы устранить это программа, которая содержит ошибку  
  
1.  Чтобы увидеть, что происходит при `Cardgame` объект уничтожается, рассмотрите деструктор `Cardgame` класса.  
  
     В строке меню выберите **представление**, **представление классов**.  
  
     В **представление классов** окна, разверните **игры** дерева проекта и выберите **Cardgame** класса для отображения членов класса и его методы.  
  
     Откройте контекстное меню для **~Cardgame(void)** деструктор и выберите **перейти к определению**.  
  
2.  Чтобы уменьшить `totalParticipants` при завершении Cardgame, добавьте следующий код между открывающей и закрывающей фигурными скобками `Cardgame::~Cardgame` деструктор.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Файл Cardgame.cpp должен выглядеть после его изменения:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
5.  После завершения построения запустите его в режиме отладки, выбрав **отладки**, **начать отладку** в строке меню или нажав клавишу F5. Программа останавливается на первой точки останова.  
  
6.  Для пошагового выполнения программы, в строке меню выберите **отладки**, **шаг с обходом**, или нажмите клавишу F10.  
  
     Обратите внимание, что после выполнения каждого конструктора Cardgame значение `totalParticipants` увеличивается. Когда `PlayGames` функции и, как каждый экземпляр Cardgame выходит за пределы области и удаляется (деструктор вызывается) `totalParticipants` уменьшается. Непосредственно перед `return` выполняется инструкция, `totalParticipants` равен 0.  
  
7.  Выполните шаг с заходом в программе до ее завершения, или оставить его запустить, выбрав **отладки**, **запуска** в строке меню или нажав клавишу F5.  
  
## <a name="next-steps"></a>Следующие шаги  
 **Предыдущие:** [Пошаговое руководство: тестирование проекта (C++)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **далее:**[Пошаговое руководство: развертывание программы (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Сборка программ C/C++](../build/building-c-cpp-programs.md)