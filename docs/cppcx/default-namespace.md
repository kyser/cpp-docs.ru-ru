---
title: пространство имен по умолчанию | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f4386d3636744a673a10dd9530fd3836fdb78e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-namespace"></a>Пространство имен default
`default` Пространства имен охватывает встроенные типы, поддерживаемые в C + +/ CX.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace default;  
```  
  
### <a name="members"></a>Участники  
 Все встроенные типы наследуют следующие члены.  
  
|||  
|-|-|  
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Определяет, равен ли заданный объект текущему объекту.|  
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Возвращает хэш-код данного экземпляра.|  
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Возвращает строку, которая представляет текущий тип.|  
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Возвращает строку, которая представляет текущий тип.|  
  
### <a name="built-in-types"></a>Встроенные типы  
  
|name|Описание|  
|----------|-----------------|  
|`char16`|16-битовое нечисловое значение, представляющее кодовую точку Юникода (UTF-16).|  
|`float32`|32-битовое число с плавающей запятой стандарта IEEE 754.|  
|`float64`|64-битовое число с плавающей запятой стандарта IEEE 754.|  
|`int16`|16-разрядное знаковое целое число.|  
|`int32`|32-разрядное знаковое целое число.|  
|`int64`|64-разрядное целое число со знаком.|  
|`int8`|8-разрядное числовое значение со знаком.|  
|`uint16`|16-разрядное целое число без знака.|  
|`uint32`|32-разрядное целое число без знака.|  
|`uint64`|64-разрядное целое число без знака.|  
|`uint8`|8-разрядное числовое значение без знака.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** vccorlib.h  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)