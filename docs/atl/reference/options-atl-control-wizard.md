---
title: Параметры, мастер элементов управления ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1062d32aadc2ec4af68cda8bca02ac1a45a526
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="options-atl-control-wizard"></a>Параметры, мастер элементов управления ATL
Вставьте здесь «Результаты поиска» сводки.  
  
 Эта страница мастера позволяет определить тип элемента управления, который вы создаете и уровень поддержки интерфейса, содержащихся в нем.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Тип элемента управления**  
 Тип элемента управления, который требуется создать.  
  
-   **Стандартный элемент управления: элемент управления ActiveX.**  
  
-   **Составной элемент управления**: элемент управления ActiveX, может содержать (аналогично диалоговое окно) другие элементы управления ActiveX или элементы управления Windows. Составной элемент управления включает следующее:  
  
    -   Шаблон для диалогового окна, который реализует составного элемента управления.  
  
    -   Настраиваемый ресурс РЕЕСТРА, который автоматически регистрирует составной элемент управления при вызове.  
  
    -   Класс C++, который реализует составного элемента управления.  
  
    -   COM-интерфейса, предоставляемые составного элемента управления.  
  
    -   Тестовая страница HTML содержащий составного элемента управления.  
  
     По умолчанию этот элемент управления задает [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) в значение true, чтобы указать, что это оконный элемент управления. Он реализует приемником сопоставления. Дополнительные сведения см. в разделе [поддержка элементов управления DHTML](../../atl/atl-support-for-dhtml-controls.md).  
  
-   **Элемент управления DHTML**: элемент управления ATL DHTML задает пользовательский интерфейс, с помощью HTML. Класс пользовательского интерфейса DHTML содержит карту COM. По умолчанию этот элемент управления задает [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) в значение true, чтобы указать, что это оконный элемент управления.  
  
     Дополнительные сведения см. в разделе [определения элементов управления DHTML проекта](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
 **Минимальный элемент управления**  
 Поддерживает только те интерфейсы, которые абсолютно необходимы большинству контейнеров. Можно задать **минимальный элемент управления** для перечисленных типов элементов управления: можно создать минимальный стандартный элемент управления, минимальный составной элемент управления или минимальный элемент управления DHTML.  
  
 **Статистическая обработка**  
 Добавляет поддержку статистической обработки для элемента управления, который вы создаете. Дополнительные сведения см. в разделе [статистической обработки](../../atl/aggregation.md).  
  
-   **Да**: Создание элемента управления, могут быть агрегированными.  
  
-   **Не**: Создание элемента управления, невозможно выполнить статистическую обработку.  
  
-   **Только**: Создание элемента управления, могут быть созданы только путем агрегирования.  
  
 **Модель потоков**  
 Указывает, что потоковая модель, используемые элементом управления.  
  
-   **Один**: элемент управления будет запускаться только в основном потоке COM.  
  
-   **Подразделения**: элемент управления можно создать в любом однопотоковом подразделении. По умолчанию.  
  
 **Interface**  
 Тип интерфейса данного элемента управления предоставляет доступ к контейнеру.  
  
-   **Двойная**: создает интерфейс, который предоставляет свойства и методы через `IDispatch` и напрямую через VTBL.  
  
-   **Настраиваемый**: создает интерфейс, который предоставляет методы посредством VTBL.  
  
     При выборе **настраиваемый**, то можно указать, что элемент управления является **совместимый автоматизации**. При выборе **совместимый автоматизации**, то мастер добавляет [oleautomation](../../windows/oleautomation.md) атрибут интерфейса в IDL-ФАЙЛ, и интерфейс может быть маршалирован универсальным упаковщиком в библиотеках oleaut32.dll. В разделе [сведения о маршалинге](http://msdn.microsoft.com/library/windows/desktop/ms692621) в Windows SDK для получения дополнительной информации.  
  
     Кроме того при выборе **совместимый автоматизации**, а затем все параметры для всех методов в элементе управления должны быть **VARIANT** совместимый.  
  
 **Поддержка**  
 Задает дополнительную поддержку для элемента управления.  
  
-   **Точки подключения**: включает точки подключения для объекта, делая являются производными от класса объекта [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) и разрешить его для предоставления интерфейса источника.  
  
-   **Лицензия**: Добавляет поддержку для элемента управления для [лицензирования](http://msdn.microsoft.com/library/windows/desktop/ms690543). Лицензированные элементы управления можно размещать только в том случае, если клиентский компьютер имеет правильные лицензии.  
  
## <a name="see-also"></a>См. также  
 [Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md)

