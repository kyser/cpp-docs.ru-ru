---
title: Определение встроенных функций C при использовании dllexport и dllimport | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ca4ab6fdfe06dec6d790db3135e42a6eeb39d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Определение подставляемых функций C с использованием dllexport и dllimport
**Блок, относящийся только к системам Microsoft**  
  
 Функцию с атрибутом `dllexport` можно определить как встроенную. В этом случае всегда создается экземпляр функции и она экспортируется независимо от того, ссылается ли на нее какой-либо модуль в программе. Предполагается, что функция должна импортироваться другой программой.  
  
 В качестве встроенной можно также определить функцию, объявленную с атрибутом **dllimport**. В этом случае функцию можно расширить (согласно спецификации параметров компилятора /Ob (inline)), но ее экземпляр никогда не создается. В частности, если принимается адрес встроенной импортированной функции, возвращается адрес функции, находящейся в библиотеке DLL. Это поведение аналогично получению адреса невстроенной импортированной функции.  
  
 Локальные статические данные и строки во встроенных функциях поддерживают одинаковые идентификаторы между библиотекой DLL и клиентом так, как это было бы в одной программе (т. е. исполняемый файл без интерфейса DLL).  
  
 При предоставлении импортированных встроенных функций соблюдайте осторожность. Например, при обновлении библиотеки DLL не следует предполагать, что клиент использует ее измененную версию. Чтобы убедиться в загрузке правильной версии библиотеки DLL, перестройте также клиент этой библиотеки.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функции импорта и экспорта DLL](../c-language/dll-import-and-export-functions.md)