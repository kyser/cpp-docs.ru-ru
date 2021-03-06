---
title: cpp_quote | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38ecabcde55f49687abf7caff66fb2c316fab0fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="cppquote"></a>cpp_quote
Создает указанную строку без символов кавычек, в сгенерированный IDL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 *statement*  
 Инструкцию C.  
  
## <a name="remarks"></a>Примечания  
 **Cpp_quote** C++ атрибут полезен, если вы хотите поместить директиву препроцессора в IDL-файл.  
  
 Можно также использовать **cpp_quote** и создания h-файле, в процессе компиляции MIDL. Например если имеется файл заголовка C++, который использует атрибуты C++ IDL, но не может использовать этот файл для некоторых задач, затем можно скомпилировать его, чтобы создать созданные MIDL h-файл, который можно использовать.  
  
 **Cpp_quote** атрибут имеет ту же функциональность, что [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) языка MIDL.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [двойного](../windows/dual.md) использовать пример, как использовать **cpp_quote**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
