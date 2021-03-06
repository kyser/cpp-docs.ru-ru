---
title: Перечисления (C + +/ CX) | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c96fa4e7194e262eec0be4cf5f7467c163530bd2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="enums-ccx"></a>Перечисления (C++/CX)
C + +/ CX поддерживает `public enum class` ключевое слово, которое является аналогом standard C++ `scoped  enum`. При использовании перечислителя, объявленного с помощью ключевого слова `public enum class` , необходимо использовать идентификатор перечисления, чтобы определить область каждого значения перечислителя.  
  
### <a name="remarks"></a>Примечания  
 Объявление `public enum class` , не содержащее спецификатор доступа, например `public`, обрабатывается как стандартное [перечисление С++ с областью видимости](../cpp/enumerations-cpp.md).  
  
 Объект `public enum class` или `public enum struct` объявление может иметь базовый тип любого целочисленного типа, несмотря на то, что среда выполнения Windows требует тип int32 или uint32 для перечислений флагов использовался. Следующий синтаксис описывает части объявления `public enum class` или `public enum struct`.  
  
 В этом примере показано, как определить открытый класс перечисления:  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 В следующем примере показано, как использовать его:  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>Примеры  
 В следующих примерах показано, как объявить перечисление.  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 В следующем примере показано, как выполнять приведение к числовым эквивалентами и выполнять сравнения. Обратите внимание, что область использования перечислителя `One` определяется идентификатором перечисления `Enum1` , а область использования перечислителя `First` — идентификатором `Enum2`.  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)