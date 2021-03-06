---
title: Параметры приложения, ATL мастера проекта | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47fbf95451834e5f8c41e8b6d7e5af7a9746bb85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="application-settings-atl-project-wizard"></a>Параметры приложений, мастер проектов ATL
Используйте **параметры приложения** мастера проекта ATL для создания и добавления основных функций в новый проект ATL.  
  
## <a name="server-type"></a>Тип сервера  
 Выберите один из трех типов серверов:  
  
 **Библиотека динамической компоновки (DLL)**  
 Выберите для создания внутрипроцессного сервера.  
  
 **Исполняемый файл (EXE)**  
 Выберите, чтобы создать локальный сервер out of process. Этот параметр не позволяет поддержку MFC или COM + 1.0. Он не допускает слияние кода прокси/заглушки.  
  
 **Службы (EXE)**  
 Выберите, чтобы создать приложение Windows, который выполняется в фоновом режиме при запуске Windows. Этот параметр не позволяет поддержку MFC или COM + 1.0 или не допускает слияние кода прокси/заглушки.  
  
## <a name="additional-options"></a>Дополнительные параметры  
  
> [!NOTE]
>  Все дополнительные параметры доступны только для проектов DLL.  
  
 **Разрешить объединение кода прокси и заглушки**  
 Выберите **Разрешить объединение кода прокси/заглушки** флажок для удобства при необходимости маршалинг интерфейсов. Этот параметр помещает созданный MIDL код прокси и заглушки в том же исполняемый файл, что и сервер.  
  
 **Поддержка MFC**  
 Выберите, чтобы указать, что объект включает поддержку MFC. Этот параметр связывает проект библиотеки MFC, так что можно использовать все классы и функции, которые они содержат.  
  
 **Поддержка COM + 1.0**  
 Выберите, чтобы изменить параметры сборки проекта для поддержки компонентов COM + 1.0. В дополнение к стандартному списку библиотек мастер добавляет comsvcs.lib библиотеки зависящие от компонента COM + 1.0  
  
 Кроме того mtxex.dll — загруженную на хост-системе, при запуске приложения с задержкой.  
  
-   **Поддерживает регистрации компонента** ATL-проект включает в себя поддержку для компонентов COM + 1.0, установка этого параметра. Регистрации компонента позволяет объекту COM + 1.0 получить список компонентов, регистрировать компоненты или отменять регистрацию компонентов (по отдельности или все одновременно).  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

