---
title: Добавление объектов и элементов управления в проект ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.controls
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a6f9102aeebd0cc60765c70cf74fb2329bc801f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Добавление объектов и элементов управления в проект ATL
Один из мастеров кода ATL можно использовать для добавления элемента управления или объекта для проектов на базе ATL и MFC. Для каждого COM-объект или элемент управления добавляется, мастер создает .cpp и h-файлы, а также RGS-файл для поддержки реестра на основе сценария. В Visual Studio доступны следующие мастера кода ATL:  
  
||||  
|-|-|-|  
|[Простой объект ATL](../../atl/reference/atl-simple-object-wizard.md)|[Диалоговое окно ATL](../../atl/reference/atl-dialog-wizard.md)|[Элемент управления ATL](../../atl/reference/atl-control-wizard.md)|  
|[Страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)|[Компонентов страницы активного сервера ATL](../../atl/reference/atl-active-server-page-component-wizard.md)|[Потребителя ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[Добавление в MFC поддержки ATL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[Мастер компонентов ATL COM+ 1.0](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[Поставщик OLE DB ATL](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Прежде чем добавить объект ATL в проект, необходимо ознакомиться с подробные сведения и требования к объекту в соответствующих разделах справки.  
  
### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Чтобы добавить объект или элемент управления с помощью мастера элементов управления ATL  
  
1.  В обозревателе решений щелкните правой кнопкой мыши узел проекта и нажмите кнопку **добавить** в контекстном меню. Нажмите кнопку **добавьте класс**.  
  
     [Добавить класс](../../ide/add-class-dialog-box.md) откроется диалоговое окно.  
  
2.  Выбрав папку ATL в области категорий выберите объект для вставки из панели «шаблоны». Нажмите кнопку **откройте**. Откроется мастер кода для выбранного объекта.  
  
    > [!NOTE]
    >  Если вы хотите добавить объект ATL в проект MFC, необходимо добавить поддержку ATL к существующему проекту. Это можно сделать, следуя инструкциям в разделе [Добавление поддержки ATL в проект MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     Кроме того при попытке добавить объект ATL в проект MFC без ранее Добавление поддержки ATL, Visual Studio предлагает возможность указать, следует ли поддержку ATL к проекту. Нажмите кнопку **Да** Добавление поддержки ATL в проект и открыть выбранный мастер ATL.  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

