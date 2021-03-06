---
title: Классы поддержки компилятора COM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4fe4e7c26d1b32f16d524407279e5e71534d00c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-com-support-classes"></a>Классы поддержки компилятора COM
**Блок, относящийся только к системам Microsoft**  
  
 Стандартные классы используются для поддержки некоторых типов модели COM. Классы определены в \<comdef.h > и файлами заголовков, создается из библиотеки типов.  
  
|Класс|Цель|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Создает программу оболочку для типа `BSTR`, предоставляя полезные операторы и методы.|  
|[_com_error](../cpp/com-error-class.md)|Определяет объект ошибки, вызванные [_com_raise_error](../cpp/com-raise-error.md) в случае большинства сбоев.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Инкапсулирует указатели COM-интерфейса и автоматически выполняет необходимые вызовы методов `AddRef`, **выпуска**, и `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Создает оболочку для **VARIANT** типа, предоставляя полезные операторы и методы.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Поддержка COM компилятора](../cpp/compiler-com-support.md)   
 [Глобальные функции COM компилятора](../cpp/compiler-com-global-functions.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)