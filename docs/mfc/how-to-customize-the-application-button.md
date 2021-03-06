---
title: 'Как: Настройка кнопки приложения | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application button [MFC], customizing
ms.assetid: ebb11180-ab20-43df-a234-801feca9eb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 828886e6a5c4891e1fd7e1d820ee00542e052cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-the-application-button"></a>Практическое руководство. Настройка кнопки приложения
При нажатии кнопки приложения отображается меню команд. Как правило, меню содержит команды, связанной с файлом, например **откройте**, **Сохранить**, **печати**, и **выхода**.  
  
 ![Кнопка приложения на ленте MFC](../mfc/media/application_button.png "application_button")  
  
 Настройка кнопки приложения, откройте его в **свойства** окна, измените его свойства, а затем просмотреть элемент управления на ленте.  
  
### <a name="to-open-the-application-button-in-the-properties-window"></a>Чтобы открыть кнопка «приложение» в окне «Свойства»  
  
1.  В Visual Studio на **представление** меню, нажмите кнопку **представление ресурсов**.  
  
2.  В **представление ресурсов**, дважды щелкните ресурс ленты, чтобы отобразить ее в рабочей области конструирования.  
  
3.  На поверхности разработки, щелкните правой кнопкой мыши кнопку меню приложения и нажмите кнопку **свойства**.  
  
## <a name="application-button-properties"></a>Свойства кнопок приложения  
 Следующая таблица определяет свойства кнопки приложения.  
  
|Свойство.|Определение|  
|--------------|----------------|  
|**Кнопки**|Содержит коллекцию до трех кнопок, отображаемых в нижнем правом углу меню приложения.|  
|**Подпись**|Задает текст элемента управления. В отличие от других элементов ленты кнопку приложения не отображает текст заголовка. Вместо этого текст используется для специальных возможностей.|  
|**Изображение HDPI**|Указывает идентификатор высокой точек на дюйм (HDPI) приложение значок кнопки. При запуске приложения на монитор высокой DPI, **изображение HDPI** используется вместо **изображения**.|  
|**Большие изображения HDPI**|Указывает идентификатор высоким DPI больших изображений. При запуске приложения на монитор высокой DPI, **большие изображения HDPI** используется вместо **большие изображения**.|  
|**Маленькие изображения HDPI**|Указывает идентификатор высокой маленькие изображения точек на ДЮЙМ. При запуске приложения на монитор высокой DPI, **маленькие изображения HDPI** используется вместо **маленькие изображения**.|  
|**ID**|Задает идентификатор элемента управления.|  
|**Изображение**|Задает идентификатор значка для кнопки приложения. Значок, битовая карта 26 x 26 32 бита, имеет альфа-прозрачность. Прозрачные значок выделяются при нажатии кнопки приложения или прохождении курсора над.|  
|**Ключи**|Задает строку, которая отображается, если включена навигация совет ключ. Навигации совет ключ включен, при нажатии клавиши ALT.|  
|**Большие изображения**|Указывает идентификатор образа, который содержит набор значков 32 x 32. Значки используются кнопки в главном элементов коллекции.|  
|**Главные элементы**|Содержит коллекцию пунктов меню, отображаемых в меню приложения.|  
|**Заголовок MRU**|Задает текст, отображаемый на панели списка последних.|  
|**Маленькие изображения**|Указывает идентификатор образа, который содержит набор значков 16 x 16. Значки используются кнопок в коллекции кнопок.|  
|**Используйте**|Включает или отключает панель список последних. Список последних панели отображается меню приложения.|  
|**Ширина**|Задает ширину в пикселях на панели «список последних».|  
  
 В меню приложения не отображается в области конструктора. Чтобы просмотреть его, необходимо просмотреть ленту или запустите приложение.  
  
#### <a name="to-preview-the-ribbon-control"></a>Для предварительного просмотра элемента управления ленты  
  
-   На **панель инструментов редактора ленты**, нажмите кнопку **проверить ленту**.  
  
## <a name="see-also"></a>См. также  
 [Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)

