---
title: Создание значка или другого изображения (редактор изображений для значков) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resource toolbars
- resources [Visual Studio], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2138e32b18f2e15de027e3cc04fb1bd7ee46ecd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>Создание значка или другого изображения (редактор изображений для значков)
Можно создать новое изображение (растровое изображение, значок, курсор или панель инструментов), а затем использовать редактор изображений для настройки внешнего вида. Можно также создать новый растровое изображение на основе [шаблона](../windows/how-to-use-resource-templates.md).  
  
### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Чтобы добавить новый ресурс изображения в неуправляемый проект C++  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл, а затем выберите **Вставка ресурса** в контекстном меню. (При наличии существующего ресурса изображения в RC-файле, такие как курсор, можно просто щелкнуть **курсор** папку и выберите **вставить курсор** в контекстном меню.)  
  
    > [!NOTE]
    >  **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [Вставка ресурса-диалоговое окно](../windows/add-resource-dialog-box.md), выберите тип ресурса изображения, которые вы хотите создать (**растрового изображения**, например) нажмите кнопку **New**.  
  
     Если знак плюс (**+**) отображается рядом с типом ресурса изображения в **Вставка ресурса** диалоговое окно, это означает, что доступны шаблоны. Щелкните знак «плюс», чтобы развернуть список шаблонов, выберите шаблон и нажмите кнопку **New**.  
  
### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Чтобы добавить новый ресурс изображения в проект на языке программирования .NET  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши папку проекта (например, **WindowsApplication1**).  
  
2.  В контекстном меню щелкните **добавить**, затем выберите **Добавление нового элемента**.  
  
3.  В **категории** области, разверните **элементы локального проекта** папку, нажмите кнопку **ресурсов**.  
  
4.  В **шаблоны** области, выберите тип ресурса, который вы хотите добавить в проект.  
  
     Ресурс будет добавлен в проект в обозревателе решений и ресурс откроется в [редактора изображений](../windows/image-editor-for-icons.md). Теперь все средства, доступные в редакторе изображений можно использовать для изменения изображения. Дополнительные сведения о добавлении изображений в управляемый проект см. в разделе [загрузка рисунка во время разработки](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).  
  
    > [!NOTE]
    >  Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов. Дополнительные сведения см. в разделе [Создание файлов ресурсов](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) в *руководства разработчика .NET Framework*.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Преобразование растровых изображений в панель инструментов](../windows/converting-bitmaps-to-toolbars.md)   
 [Создание новых панелей инструментов](../windows/creating-new-toolbars.md)   
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Редактор изображений для значков](../windows/image-editor-for-icons.md)

