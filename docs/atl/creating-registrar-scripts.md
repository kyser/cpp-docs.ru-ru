---
title: Создание сценариев для регистратор ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e140e66ee24d8333d25c0c2942924c7a9db4965b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
Сценарий регистратора доступ управляемых данными, а не управляемых API в системный реестр. Доступ на основе данных обычно более эффективны, так как он принимает только одну или две строки в сценарии, чтобы добавить раздел в реестр.  
  
 [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически создает скрипт регистрации для COM-сервер. Этот скрипт можно найти в RGS-файл, связанный с данным объектом.  
  
 Обработчик скриптов регистратор ATL обрабатывает скрипта регистратора во время выполнения. ATL, автоматически вызывает обработчик скриптов во время установки сервера.  
  
 В этой статье рассматриваются следующие вопросы, связанные с скрипты регистратора:  
  
-   [Основные сведения о синтаксисе формы Бэкуса-Наура (BNF)](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [Основные сведения о деревьях синтаксического анализа](../atl/understanding-parse-trees.md)  
  
-   [Примеры скриптов реестра](../atl/registry-scripting-examples.md)  
  
-   [Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Вызов скриптов](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>См. также  
 [Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

