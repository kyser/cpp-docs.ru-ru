---
title: Файлы, создаваемые для проектов CLR | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d66c3f55164a743bc395dc5e9b48f8bcd57654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="files-created-for-clr-projects"></a>Файлы, создаваемые для проектов CLR
При использовании шаблонов Visual C++ для создания проектов, создаются несколько файлов, в зависимости от того, какой из шаблонов использования. В следующей таблице перечислены все файлы, созданные шаблоны проектов для проектов .NET Framework.  
  
|Имя файла|Описание файла|  
|---------------|----------------------|  
|AssemblyInfo.cpp|Файл, содержащий сведения (то есть атрибуты, файлы, ресурсы, типы, сведения об управлении версиями, подписи сведения и т. д) для изменения метаданных сборки проекта. Дополнительные сведения см. [основные понятия сборки](/dotnet/framework/app-domains/assembly-contents).|  
|*ProjName*.asmx|Текстовый файл со ссылками на управляемые классы, инкапсулирующие функциональные возможности веб-службу XML.|  
|*ProjName*.cpp|Главный исходный файл и точка входа в приложение, созданное для вас Visual Studio. Идентифицирует DLL-файл проекта и пространство имен проекта. В этом файле содержится разработанный вами код.|  
|*ProjName*.vsdisco|Файл развертывания XML, содержащий ссылки на другие ресурсы, описывающие веб-службу XML.|  
|*ProjName*.h|Главный файл заголовка для проекта, который содержит все объявления, глобальные символы, и `#include` директивы для других файлов заголовков.|  
|*ProjName*.sln|Файл решения, используемый в среде разработки для организации всех элементов проекта в единое решение.|  
|*ProjName*.suo|Файл параметров решения, используемый в среде разработки.|  
|*ProjName*VCXPROJ-файл|Файл проекта, используется в среде разработки, который хранит информацию, относящуюся к данному проекту.|  
|ReadMe.txt|Файл, описывающий каждый файл в проект, использующий фактические имена файлов, создаваемых в шаблоне.|