---
title: 'Страница свойств шаг пользовательской сборки: Общие | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d88bd738711058794a525217ba2640e8d52356d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-build-step-property-page-general"></a>Страница свойств "Общие" пользовательского шага построения
Для каждого сочетания конфигурации проекта и целевой платформы в проекте можно определить пользовательское действие, которое будет выполняться при сборке проекта.  

Linux версию этой страницы см. в разделе [Свойства шага построения пользовательского (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Командная строка**  
 Команда, которая будет выполняться этим пользовательским действием сборки.  
  
 **Описание**  
 Сообщение, которое отображается при выполнении пользовательского действия сборки.  
  
 **Выходные данные**  
 Выходной файл, создаваемый пользовательским действием сборки. Этот параметр является обязательным для правильной работы добавочных сборок.  
  
 **Дополнительные зависимости**  
 Разделенный точками с запятой список каких-либо дополнительных входных файлов для пользовательского действия сборки.  
  
 **Выполнить после и выполнить до**  
 Эти параметры определяют, когда пользовательское действие сборки выполняется в процессе сборки относительно перечисленных целевых объектов. Наиболее часто в число целевых объектов входят BuildGenerateSources, BuildCompile и BuildLink, поскольку они представляют основные этапы процесса сборки. Другие часто используемые целевые объекты: Midl, CLCompile и Link.  
  
 Обрабатывать выходные данные как содержимое  
 Этот параметр применяется только для приложений универсальной платформы Windows или Windows Phone, включая все файлы содержимого в пакет AppX.  
  
### <a name="to-specify-a-custom-build-step"></a>Задание пользовательского действия сборки  
  
1.  В строке меню выберите **Проект**, **Свойства**. Дополнительные сведения см. в разделе [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
2.  В **страницы свойств** диалоговом окне перейдите к **свойства конфигурации**, **настраиваемый этап сборки**, **Общие** страницы.  
  
3.  Измените параметры.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)