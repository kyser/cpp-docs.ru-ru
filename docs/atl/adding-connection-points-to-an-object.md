---
title: Добавление точек подключения объекта | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f9d136ccdeded02303894195c7b8126acafd9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-connection-points-to-an-object"></a>Добавление точек подключения к объектам
[Учебник по ATL](../atl/active-template-library-atl-tutorial.md) показано, как создать элемент управления с поддержкой точек подключения, как добавлять события и как реализовать точку подключения. ATL реализует точки подключения с [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) класса.  
  
 Чтобы реализовать точку подключения, есть два варианта:  
  
-   Реализуйте собственные исходящих источник события путем добавления точки подключения для элемента управления или объекта.  
  
-   Повторное использование интерфейса точки подключения, определенные в другую библиотеку типов.  
  
 В любом случае мастер реализации точек подключения использует библиотеку типов для выполнения своей работы.  
  
### <a name="to-add-a-connection-point-to-a-control-or-object"></a>Добавление точки подключения в элемент управления или объект  
  
1.  Определите disp-интерфейса в блоке библиотеку IDL-файла. Если вы включили поддержку для точек подключения, при создании элемента управления с помощью мастера элементов управления ATL, диспетчерский интерфейс уже создается. Если вы не включили поддержку для точки подключения при создании элемента управления, необходимо вручную добавить disp-интерфейса в IDL-файл. Ниже приведен пример диспетчерский интерфейс. Исходящих интерфейсов не обязательно должны быть интерфейса диспетчеризации, но многие языки сценариев, таких как VBScript и JScript это требуется, поэтому в этом примере используется два диспетчера интерфейсов:  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]  
  
     Программа uuidgen.exe, либо guidgen.exe для создания идентификатора GUID.  
  
2.  Disp-интерфейса, как добавить `[default,source]` интерфейс в компонентном классе для объекта в IDL-файл проекта. Опять же, если вы включили поддержку для точек подключения, при создании элемента управления, мастер элементов управления ATL создаст `[default,source`] операция. Чтобы вручную добавить эту запись, добавьте строку полужирным шрифтом:  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]  
  
     IDL-файла в разделе [Circ](../visual-cpp-samples.md) образца ATL в качестве примера.  
  
3.  Представление классов можно используйте для добавления методы и свойства для интерфейса события. Класс в представлении классов щелкните правой кнопкой мыши **добавить** в контекстном меню, а затем нажмите кнопку **добавить точку подключения**.  
  
4.  В **интерфейсов источника** список мастер реализации точек подключения, выберите **интерфейсах проекта**. Если выбрана интерфейс для управления и нажмите клавишу **ОК**, мы затронем следующие вопросы:  
  
    -   Создание файла заголовка с прокси-класса событий, реализующий код, который будет отправлять исходящие вызовы, для события.  
  
    -   Добавьте запись для сопоставление точки подключения.  
  
     Также появится список всех библиотек типов, на компьютере. Только один из этих других библиотеках типов следует использовать для определения нужной точки подключения, если нужно реализовать же исходящий интерфейс в другую библиотеку типов.  
  
### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Для повторного использования интерфейса точки подключения, определенные в другую библиотеку типов  
  
1.  В представлении классов щелкните правой кнопкой мыши класс, реализующий **BEGIN_COM_MAP** макрос пункты **добавить** в контекстном меню, а затем нажмите кнопку **добавить точку подключения**.  
  
2.  В мастер реализации точек подключения, выберите библиотеку типов и интерфейс в библиотеке типов и нажмите кнопку **добавить**.  
  
3.  Изменение IDL-файла, либо:  
  
    -   Скопируйте disp-интерфейса из IDL-файла, для которого источник события используется объект.  
  
    -   Используйте **importlib** инструкций для этой библиотеки типов.  
  
## <a name="see-also"></a>См. также  
 [Точка подключения](../atl/atl-connection-points.md)

