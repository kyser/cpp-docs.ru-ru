---
title: __raise | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs:
- C++
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93bd00c89df69d655f42c06509ef0360eff0c092
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="raise"></a>__raise
Выделяет место вызова события.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Событие из управляемого кода можно вызвать только в пределах класса, где оно определено. В разделе [событие](../windows/event-cpp-component-extensions.md) для получения дополнительной информации.  
  
 Ключевое слово `__raise` вызывает ошибку, которая возникает при вызове объекта, не являющегося событием.  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="example"></a>Пример  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Обработка событий](../cpp/event-handling.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)