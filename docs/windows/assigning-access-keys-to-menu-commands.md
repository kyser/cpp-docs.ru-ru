---
title: Назначение клавиш доступа командам меню | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44a21e5930d0d8f2fcaad79cc5cef5bc984ad8b5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="assigning-access-keys-to-menu-commands"></a>Назначение клавиш доступа командам меню
Командам меню и самим меню можно назначить клавиши доступа, позволяющие выбирать элементы меню с клавиатуры.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Назначение клавиши доступа (сочетания клавиш) команде меню  
  
1.  Перед буквой в имени меню или команды меню введите амперсанд (**&**), чтобы обозначить таким образом букву, с которой будет связана клавиша доступа. Например, "&Файл" означает, что сочетание ALT+Ф будет выполнять роль клавиши доступа к меню "Файл" в приложениях для Microsoft Windows.  
  
     Буква, с которой связана клавиша доступа, обычно наглядно обозначена в элементе меню. Как правило, буква, следующая за символом амперсанда, отображается как подчеркнутая (везде в рамках одной ОС).  
  
    > [!NOTE]
    >  Чтобы убедиться в том, что клавиши доступа не повторяются в рамках одного меню, щелкните меню правой кнопкой мыши и выберите в контекстном меню команду **Проверить назначенные клавиши** .  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор меню](../windows/menu-editor.md)