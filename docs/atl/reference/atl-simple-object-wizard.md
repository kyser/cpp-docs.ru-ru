---
title: Мастер простых объектов ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff9648cfc350f724a333e38622d082d8d399b3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-simple-object-wizard"></a>Мастер простых объектов ATL
Этот мастер вставляет в проект минимальный COM-объект. Эта страница мастера для указания имен, которые идентифицируют класс C++ и файлы для объекта и его функциональные возможности модели COM.  
  
 Используйте [параметры](../../atl/reference/options-atl-simple-object-wizard.md) поддержки этого мастера, чтобы указать потоковую модель объекта, его статистической обработки, и поддерживает ли он сдвоенные интерфейсы и автоматизацию. Можно также задать поддержку интерфейса информации об ошибках, точек соединения, поддержки Internet Explorer и свободнопоточный маршалинга.  
  
## <a name="remarks"></a>Примечания  
 Начиная с Visual Studio 2008, регистрации сценарий, созданные с помощью этого мастера будет регистрировать его COM-компонентов в группе **HKEY_CURRENT_USER** вместо **HKEY_LOCAL_MACHINE**. Чтобы изменить это поведение, задайте **компонент регистра для всех пользователей** параметр мастера ATL.  
  
## <a name="names"></a>Имена  
 Укажите имена для объектов, интерфейс и классы для добавления в проект. За исключением **короткое имя**, все поля можно изменять независимо от других. Если изменить текст для **короткое имя**, это изменение отражается в имена всех других полей на этой странице. При изменении **Coclass** имя в разделе COM, это изменение отражается в **тип** и **ProgID** диалоговые окна, но **интерфейс** имя не изменяется. Эти принципы именования позволяют легко определить по вы все имена разработки элементов управления.  
  
> [!NOTE]
>  **Компонентный класс** можно изменять только для проектов без атрибутов. Если атрибуты проекта, нельзя изменить **компонентного класса**.  
  
## <a name="c"></a>C++  
 Сведения о классе C++, созданном для объекта.  
  
 **Краткое имя**  
 Задает сокращенное имя для объекта. Имя, которое определяет `Class` и **Coclass** имена, **CPP-файл** и **h-файл** имена, **интерфейс**имя **тип** имена и **ProgID**, если не изменить значения этих полей по отдельности.  
  
 **h-файл**  
 Задает имя файла заголовка для нового объекта класса. По умолчанию это имя основано на имени, указанному в **короткое имя**. Нажмите кнопку с многоточием, чтобы сохранить файл в выбранное расположение или добавить объявление класса в существующий файл. При выборе существующего файла не он будет сохранен в выбранном месте пока вы щелкните **Готово** в мастере.  
  
 Мастер не перезаписывает файл. Если выбрать имя существующего файла, после нажатия **Готово**, мастер предложит указать, следует ли добавить объявление класса к содержимому файла. Нажмите кнопку **Да** для добавления в файл; щелкните **нет** вернуться в мастер и укажите другое имя файла.  
  
 **Класс**  
 Задает имя создаваемого класса. Это имя основано на имени, указанному в **короткое имя**, предшествует «C» — типичный префикс имени класса.  
  
 **CPP-файл**  
 Задает имя файла реализации для нового объекта класса. По умолчанию это имя основано на имени, указанному в **короткое имя**. Нажмите кнопку с многоточием, чтобы сохранить имя файла в папку по своему усмотрению. Файл не сохранен в выбранном месте до нажатия кнопки **Готово** в мастере.  
  
 Мастер не перезаписывает файл. Если выбрать имя существующего файла, после нажатия **Готово**, мастер предложит указать, следует ли добавить реализацию класса к содержимому файла. Нажмите кнопку **Да** для добавления в файл; щелкните **нет** вернуться в мастер и укажите другое имя файла.  
  
 **Атрибут**  
 Указывает, использует ли объект атрибуты. При добавлении объекта атрибутами проекта ATL, этот параметр установлен и недоступен для изменения. То есть только атрибутами объекты можно добавлять в проект с поддержкой атрибутов.  
  
 Объект с атрибутами можно добавлять только в проект ATL, использующего атрибуты. При выборе этого параметра для проекта ATL, не поддерживает атрибуты, мастер предложит указать, следует ли добавить поддержку атрибутов в проект.  
  
 По умолчанию все объекты, которые добавляются после установки этого параметра обозначаются как атрибутивного (флажок). Можно снять этот флажок, чтобы добавить объект, который не использует атрибуты.  
  
 В разделе [параметры приложения, мастер проектов ATL](../../atl/reference/application-settings-atl-project-wizard.md) и [основные механизмы атрибуты](../../windows/basic-mechanics-of-attributes.md) для получения дополнительной информации.  
  
## <a name="com"></a>COM  
 Предоставляет сведения о функциях COM для объекта.  
  
 **Компонентный класс**  
 Задает имя класса компонента, содержащего список интерфейсов, поддерживаемое объектом.  
  
> [!NOTE]
>  Если вы создаете проект, использующий атрибуты, или если на этой странице мастера указывается, что объект использует атрибуты, не может изменить этот параметр, поскольку ATL не включает `coclass` атрибута.  
  
 **Type**  
 Задает описание объекта, которое будет отображаться в реестре  
  
 **Interface**  
 Задает интерфейс, который создается для объекта. Этот интерфейс содержит пользовательские методы.  
  
 **Идентификатор progID**  
 Задает имя, которое может использоваться контейнерами вместо CLSID объекта.  
  
## <a name="see-also"></a>См. также  
 [Простой объект ATL](../../atl/reference/adding-an-atl-simple-object.md)

