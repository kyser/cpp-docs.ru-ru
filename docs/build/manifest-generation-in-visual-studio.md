---
title: Создание манифестов в Visual Studio | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5cbe631d078dd6ee27b4f7e0a97503c36638b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="manifest-generation-in-visual-studio"></a>Создание манифестов в Visual Studio
Создание файла манифеста для конкретного проекта можно управлять в проекте **страницы свойств** диалогового окна. На **свойства конфигурации** щелкните **компоновщика**, затем **файл манифеста**, затем **создать манифест**. По умолчанию свойства проекта новых проектов присваивается создать файл манифеста. Однако можно отключить создание манифеста для проекта с помощью **создать манифест** свойство проекта. Если значение этого свойства **Да**, создания манифеста для этого проекта. В противном случае Компоновщик игнорирует информацию сборки при разрешении зависимостей в коде приложения и не создает манифест.  
  
 Система сборки в Visual Studio позволяет манифест внедрен в итоговые двоичные файлы приложения, то создается как внешний файл. Это поведение управляется **внедренный манифест** в диалоговом окне **свойства проекта** диалогового окна. Чтобы задать это свойство, откройте **инструмент манифеста** узел, затем выберите **входных и выходных**. Если манифест не внедрен, он создается как внешний файл и сохранить в том же каталоге, что конечный двоичный файл. Если манифест внедрен, Visual Studio внедряет итоговые манифесты следующим образом:  
  
1.  После компиляции исходного кода в объектные файлы, компоновщик собирает сведения зависимой сборки. При связывании в конечный двоичный файл, компоновщик создает промежуточный манифест, впоследствии используется для создания итогового манифеста.  
  
2.  После завершения промежуточного манифеста и компоновка инструмент манифеста будет выполняться для формирования итогового манифеста и сохраните его в виде внешнего файла.  
  
3.  Проект создания системы, а затем определяет, содержит ли манифест, созданный инструментом манифеста данные, отличные от уже внедрены в двоичный файл манифеста.  
  
4.  Если манифест внедрен в двоичный файл отличается от манифеста, созданного инструментом манифеста или двоичный файл не содержит внедренный манифест, Visual Studio запустит компоновщик еще раз для внедрения в двоичный файл как внешний файл манифеста ресурс.  
  
5.  Если манифест внедрен в двоичный файл, то же, что манифест, созданный инструментом манифеста сборки будет продолжать дальнейшие действия построения.  
  
 Манифест внедрен в конечный двоичный файл как ресурс текста и его можно просмотреть, открыв в конечный двоичный файл как файл в Visual Studio. Чтобы обеспечить манифест, на который указывает нужные библиотеки, выполните действия, описанные в [основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) или следовать указаниям, приведенным в [Устранениенеполадок](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) раздела.  
  
## <a name="see-also"></a>См. также  
 [Как: встраивания манифеста приложения C/C++](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [О закрытые сборки](http://msdn.microsoft.com/library/ff951638)   
 [Инструмент манифеста](http://msdn.microsoft.com/library/aa375649)   
 [Основные сведения о создании манифестов для программ на C/C++](../build/understanding-manifest-generation-for-c-cpp-programs.md)