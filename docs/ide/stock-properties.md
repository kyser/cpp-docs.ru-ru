---
title: Стандартные свойства | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3586fb33c30148c870b096d0d49a41d7ad8c6c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="stock-properties"></a>Свойства хранения
При добавлении свойства в MFC disp-интерфейса с помощью [мастер добавления свойств](../ide/idl-attributes-add-property-wizard.md), можно выбрать из стандартного свойства **имя свойства** списка в [имена](../ide/names-add-property-wizard.md) страницы мастер. Список содержит следующие свойства.  
  
|Имя свойства.|Описание|  
|-------------------|-----------------|  
|**Внешний вид**|Возвращает или задает значение, определяющее внешний вид элемента управления. Элемент управления **внешний вид** свойства можно включить или исключить объемным. Это свойство окружения чтения и записи.|  
|`BackColor`|Возвращает или задает элемент управления окружения `BackColor` цветовой палитры (RGB), так и системные свойства. По умолчанию его значение соответствует цвет переднего плана для контейнера элемента управления. Это свойство окружения чтения и записи.|  
|`BorderStyle`|Возвращает или задает стиль границы для элемента управления. Это свойство чтения/записи.|  
|**Подпись**|Возвращает или задает элемент управления **заголовок** свойство. Заголовок является заголовком окна. **Заголовок** не имеет **переменной-члена** тип реализации.|  
|**Включено**|Возвращает или задает элемент управления **включено** свойство. Включенный элемент управления может отвечать на события, вызываемые пользователем.|  
|**Шрифт**|Возвращает или задает параметры внешнего шрифта для элемента управления. Имеет значение NULL, если какой-либо шрифт для элемента управления.|  
|`ForeColor`|Возвращает или задает элемент управления окружения `ForeColor` свойство.|  
|**hWnd**|Возвращает или задает элемент управления **hWnd** свойство. **hWnd** не имеет **переменной-члена** тип реализации.|  
|**Состояние готовности**|Возвращает или задает элемент управления **состояние готовности** свойство. Элемент управления может быть неинициализированным, инициализированный, загрузка, интерактивной или завершения. В разделе [состояние готовности](https://msdn.microsoft.com/en-us/library/aa768362.aspx) в *Internet SDK* Дополнительные сведения.|  
|**Text**|Возвращает или задает текст, содержащийся в элементе управления. **Текст** не имеет **переменной-члена** тип реализации.|  
  
## <a name="see-also"></a>См. также  
 [Добавление свойства](../ide/adding-a-property-visual-cpp.md)   
 [Атрибуты IDL, мастер добавления свойств](../ide/idl-attributes-add-property-wizard.md)