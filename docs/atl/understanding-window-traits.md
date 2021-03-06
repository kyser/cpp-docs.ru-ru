---
title: Признаки окна ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71fbf5b3c4c3f1aa95070cbc0d30beb9e1321348
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-window-traits"></a>Основные сведения об окне признаки
Окно признаки классы предоставляют простой способ для стандартизации стили, используемые для создания объекта ATL окна. Признаки окна могут использоваться в качестве параметров шаблона, [CWindowImpl](../atl/reference/cwindowimpl-class.md) и другие классы окон ATL как способа предоставления стили окна на уровне класса по умолчанию.  
  
 Если создатель экземпляр окна не предоставляет стили явным образом при вызове [создать](../atl/reference/cwindowimpl-class.md#create), можно использовать класс характеристик для убедитесь, что окно по-прежнему создана с правильными стилями. Можно даже убедитесь, что некоторые стили заданы для всех экземпляров этого класса окна пока разрешен другие стили, задаваемое для каждого экземпляра.  
  
## <a name="atl-window-traits-templates"></a>Шаблоны признаки окон ATL  
 Библиотека ATL предоставляет два шаблона окна признаки, которые позволяют задавать стили по умолчанию во время компиляции, с помощью их параметров шаблона.  
  
|Класс|Описание|  
|-----------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|Используйте этот шаблон, когда вы хотите предоставить по умолчанию стили окна, которые будут использоваться только в том случае, если нет другие стили, указаны в вызове **создать**. Стили, предоставленных во время выполнения имеет приоритет над стилями, заданными во время компиляции.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Этот класс используется в том случае, если вы хотите указать стили, которые всегда должны быть заданы для класса окна. Стили, предоставленных во время выполнения объединяются со стилями, заданными во время компиляции с помощью оператора побитового или.|  
  
 Помимо этих шаблонов, библиотека ATL предоставляет ряд предопределенных специализации `CWinTraits` шаблона для часто используемых сочетаний стили окна. В разделе [CWinTraits](../atl/reference/cwintraits-class.md) справочную документацию по классу полные данные.  
  
## <a name="custom-window-traits"></a>Признаки пользовательского окна  
 В ситуации, скорее всего, что специализирующем один из шаблонов, представленных ATL недостаточно и необходимо создать собственный класс признаки, необходимо создать класс, реализующий два статических функций: `GetWndStyle` и **GetWndStyleEx** :  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]  
  
 Каждая из этих функций будет передано значение стиля во время выполнения, что его можно использовать для создания нового значения стилей. Если признаки класс окна используется в качестве аргумента шаблона для класс окна ATL, значения стиля, переданные эти статические функции будет независимо от был передан в качестве аргументов стиля [создать](../atl/reference/cwindowimpl-class.md#create).  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

