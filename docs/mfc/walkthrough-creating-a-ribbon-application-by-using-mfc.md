---
title: 'Пошаговое руководство: Создание приложения ленты с помощью MFC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f715830c110f03811202d2e98dc097bfe712208
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>Пошаговое руководство. Создание приложения ленты с помощью MFC
В этом пошаговом руководстве показано, как использовать **мастер приложений MFC** для создания приложения с лентой по умолчанию. Затем мы расширим ленту, добавив **настраиваемый** категорией, которая имеет **Избранное** панели и добавим некоторые часто используемые команды на панель.  
  
## <a name="prerequisites"></a>Предварительные требования  
 В этом пошаговом руководстве предполагается, что вы указали [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] использовать **обычные параметры разработки**. Если вы используете другие параметры, некоторые из элементов пользовательского интерфейса, упоминаемые в приведенных ниже инструкциях, могут не отображаться. Сведения об изменении параметров см. в разделе [как: Reset Your параметры](http://msdn.microsoft.com/en-us/c95c51be-e609-4769-abba-65e6beedec76).  
  
### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>Создание приложения MFC с лентой  
  
1.  Используйте **мастер приложений MFC** Создание приложения MFC с лентой. Чтобы запустить мастер, на **файл** последовательно выберите пункты **New**и нажмите кнопку **проекта**.  
  
2.  В **новый проект** диалогового окна разверните **Visual C++** узле **установленные шаблоны**выберите **MFC**и выберите  **Приложение MFC**. Введите имя проекта, например `MFCRibbonApp`, а затем нажмите кнопку **ОК**.  
  
3.  На первой странице **мастер приложений MFC**, нажмите кнопку **Далее**.  
  
4.  На **тип приложения** в разделе **визуальный стиль и цвета**выберите **Office 2007 (синяя тема)**. Остальные параметры не изменяйте. Нажмите кнопку **Далее**.  
  
5.  На **поддержка составных документов** убедитесь, что **нет** выбран, а затем нажмите кнопку **Далее**.  
  
6.  На **свойства шаблона документа** страницы в **расширение файла** введите расширение имени файла для документов, например, это приложение создает `mfcrbnapp`. Нажмите кнопку **Далее**.  
  
7.  На **Поддержка баз данных** убедитесь, что **нет** выбран, а затем нажмите кнопку **Далее**.  
  
8.  На **возможности пользовательского интерфейса** убедитесь, что **использовать ленту** выбран. Нажмите кнопку **Далее**.  
  
9. По умолчанию **мастер приложений MFC** добавляет поддержку нескольких закрепляемых областей. Поскольку в этом руководстве рассматривается только лента, эти компоненты можно удалить из приложения. На **дополнительные функции** снимите все флажки. Нажмите кнопку **Далее**.  
  
10. На **классы, создаваемые** щелкните **Готово** Создание приложения MFC.  
  
11. Чтобы убедиться, что приложение успешно создано, соберите и запустите его. Для сборки приложения, в **построения** меню, нажмите кнопку **построить решение**. Если сборка приложения прошла успешно, запустите его, выбрав **начать отладку** на **отладки** меню.  
  
     Мастер автоматически создает ленту с одной категорией, которая называется **Главная**. Эта лента содержит три панели ленты, которые называются **буфер обмена**, **представление**, и **окна**.  
  
### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>Добавление категории и панели на ленту  
  
1.  Чтобы открыть созданный мастером, в ресурс ленты **представление** последовательно выберите пункты **другие окна** и нажмите кнопку **представление ресурсов**. В **представление ресурсов**, нажмите кнопку **ленты** и дважды щелкните **IDR_RIBBON**.  
  
2.  Сначала добавьте на ленту пользовательскую категорию, дважды щелкнув **категории** в **элементов**.  
  
     Категории, подпись **Категория1** создается. По умолчанию категория содержит одну панель.  
  
     Щелкните правой кнопкой мыши **Категория1** и нажмите кнопку **свойства**. В **свойства** измените **заголовок** для `Custom`.  
  
     **Большие изображения** и **маленькие изображения** задают точечные рисунки, используются в качестве значков для элементов ленты в этой категории. Поскольку создание пользовательских точечных рисунков выходит за рамки этого руководства, просто используйте точечные рисунки, созданные мастером. Маленькие точечные рисунки имеют размер 16 пикселей на 16 пикселей. Используйте в качестве маленьких изображений точечные рисунки, доступ к которым осуществляется по идентификатору ресурса IDB_FILESMALL. Большие точечные рисунки имеют размер 32 пикселей на 32 пикселей. Используйте в качестве больших изображений точечные рисунки, доступ к которым осуществляется по идентификатору ресурса IDB_FILELARGE.  
  
    > [!NOTE]
    >  На HDPI-мониторах автоматически используются HDPI-версии изображений.  
  
3.  Теперь необходимо настроить панель. Панели используются для группирования элементов, логически связанных друг с другом. Например, на **Главная** вкладка этого приложения **Вырезать**, **копирования**, и **вставить** команды расположены в  **Буфер обмена** панель. Чтобы настроить панель, щелкните правой кнопкой мыши **Panel1** и нажмите кнопку **свойства**. В **свойства** измените **заголовок** для `Favorites`.  
  
     Можно указать **индекс образа** для панели. Это число определяет значок, который отображается при добавлении панели ленты **панель быстрого доступа**. На самой панели ленты значок не отображается.  
  
4.  Чтобы убедиться, что категория и панель ленты успешно созданы, просмотрите элемент управления "лента". На **панель инструментов редактора ленты**, нажмите кнопку **проверить ленту** кнопки. Объект **настраиваемый** вкладку и **Избранное** панели должны отображаться на ленте.  
  
### <a name="to-add-elements-to-the-ribbon-panels"></a>Добавление элементов на панели ленты  
  
1.  Чтобы добавить элементы на панель, созданную в предыдущей процедуре, перетащите элементы управления из **редактора ленты** раздел **элементов** панель в представлении конструирования.  
  
2.  Сначала добавьте **печати** кнопки. **Печати** кнопка будет иметь подменю, содержащее **Быстрая печать** команду, которая выводит документ на принтер по умолчанию. Обе эти команды уже определены для этого приложения. Они находятся в меню приложения.  
  
     Для создания **печати** кнопку, перетащите на панель инструмент "Кнопка".  
  
     В **свойства** измените **идентификатор** свойства **ID_FILE_PRINT**, который должен быть уже определен. Изменение **заголовок** для `Print`. Изменение **изображения индекс** для `4`.  
  
     Для создания **Быстрая печать** кнопку, щелкните столбец значения свойства рядом с **пунктов меню**и нажмите кнопку с многоточием (**...** ). В **редактор элементов**, нажмите неподписанную **добавить** кнопку, чтобы создать элемент меню. В **свойства** измените **заголовок** для `Quick Print`, **идентификатор** для `ID_FILE_PRINT_DIRECT`, и **изображения** для `5` . Свойство "Изображение" задает значок "Быстрая печать" в ресурсе точечных изображений IDB_FILESMALL.  
  
3.  Чтобы убедиться, что кнопки добавлены на панель ленты, соберите приложение и запустите его. Для сборки приложения, в **построения** меню, нажмите кнопку **построить решение**. Если сборка приложения прошла успешно, запустите приложение, нажав кнопку **начать отладку** на **отладки** меню. **Печати** кнопки и поля со списком поле на **Избранное** на панели **настраиваемый** должны отображаться на вкладке ленты.  
  
## <a name="next-steps"></a>Следующие шаги  
 [Практическое руководство. Настройка панели быстрого доступа](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [Практическое руководство. Настройка кнопки приложения](../mfc/how-to-customize-the-application-button.md)  
  
 Образцы конца в конец см [образцы (MFC пакет компонентов)](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства](../mfc/walkthroughs-mfc.md)   
 [Примеры (пакет компонентов MFC)](../visual-cpp-samples.md)

