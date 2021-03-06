---
title: Поддержка COM + 1.0 в проектах ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3440d3ed2e3244b35588d5c07fd181f1ad2f082
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="com-10-support-in-atl-projects"></a>Поддержка COM + 1.0 в проекты ATL
Можно использовать [мастер проектов ATL](../../atl/reference/creating-an-atl-project.md) для создания проекта с базовой поддержкой компонентов COM + 1.0.  
  
 COM + 1.0 предназначена для разработки распределенных приложений, основанных на компонентах. Он также обеспечивает инфраструктуру времени выполнения для развертывания и управления этими приложениями.  
  
 При выборе **поддержка COM + 1.0** флажок установлен, мастер изменяет скрипт построения на этапе связывания. В частности COM + 1.0 проект ссылки на следующие библиотеки:  
  
-   Comsvcs.lib  
  
-   Mtxguid.lib  
  
 При выборе **поддержка COM + 1.0** флажок, вы также можете выбрать **поддержку регистрации компонента**. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменять регистрацию компонентов (по отдельности или все одновременно).  
  
## <a name="see-also"></a>См. также  
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

