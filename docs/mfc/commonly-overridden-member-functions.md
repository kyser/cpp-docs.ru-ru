---
title: Часто переопределяемые функции-члены | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed090057394c385dd12825864c5de9ff7d079e29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="commonly-overridden-member-functions"></a>Часто переопределяемые функции-члены
В следующей таблице перечислены наиболее вероятной причиной функции-члены для переопределения в вашей `CDialog`-производного класса.  
  
### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Часто переопределяемые функции-члены класса CDialog  
  
|Функция-член|Ответ на сообщение|Цель переопределения|  
|---------------------|----------------------------|-----------------------------|  
|`OnInitDialog`|**WM_INITDIALOG**|Инициализация элементов управления в диалоговое окно «».|  
|`OnOK`|**BN_CLICKED** для кнопки **IDOK**|Ответить, когда пользователь нажимает кнопку "ОК".|  
|`OnCancel`|**BN_CLICKED** для кнопки **IDCANCEL**|Ответить, когда пользователь нажимает кнопку "Отмена".|  
  
 `OnInitDialog`, `OnOK`, и `OnCancel` являются виртуальными функциями. Для их переопределения, переопределяющую функцию объявлять в классе производном диалогового окна с помощью [окно свойств](/visualstudio/ide/reference/properties-window).  
  
 `OnInitDialog` вызывается непосредственно перед отображением диалоговым окном. Значение по умолчанию необходимо вызвать `OnInitDialog` обработчиком переопределенный — обычно как первое действие в обработчике. По умолчанию `OnInitDialog` возвращает **TRUE** для указания, что фокус следует установить на первый элемент управления в диалоговом окне.  
  
 `OnOK` обычно переопределяется для немодального, но не модальные диалоговые окна. При переопределении этого обработчика для модального диалогового окна вызовите версии базового класса из переопределения, чтобы убедиться, что `EndDialog` вызывается — или вызвать `EndDialog` самостоятельно.  
  
 `OnCancel` обычно переопределяется для безрежимные диалоговые окна.  
  
 Дополнительные сведения об этих функциях-членах см. класс [CDialog](../mfc/reference/cdialog-class.md) в *Справочник по библиотеке MFC* и обсуждение на [жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md).  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)
