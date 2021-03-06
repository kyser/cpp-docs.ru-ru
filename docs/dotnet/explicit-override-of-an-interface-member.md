---
title: Явное переопределение элемента интерфейса | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 811112d2721edccede6c7b4a278189fdec874523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-override-of-an-interface-member"></a>Явное переопределение элемента интерфейса
Синтаксис объявления явное переопределение элемента интерфейса в классе отличается от управляемых расширений для C++ к Visual C++.  
  
 Часто требуется предоставить два экземпляра элемента интерфейса в класс, реализующий интерфейс — один используется, если объекты класса управлять ими с помощью дескриптора интерфейса, а, которая используется при использовании объектов класса через интерфейс класса. Пример:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 В управляемых расширениях мы этого, предоставив явное объявление метода интерфейса с именем метода с именем интерфейса. Экземпляр данного класса, является неполным. Это избавляет от необходимости нисходящее приведение типа возвращаемого значения `Clone`, в этом примере, в случае явного вызова с помощью экземпляра `R`.  
  
 В новом синтаксисе механизм переопределения представлена, заменяет синтаксис управляемых расширений. Наш пример можно переписать следующим образом:  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Эта версия требует явного переопределения члена интерфейса присвоено уникальное имя в пределах класса. Здесь я указано неверное имя `InterfaceClone`. Поведение остается неизменным - вызов через `ICloneable` интерфейса вызывает переименованной `InterfaceClone`, тогда как вызов через объект типа `R` вызывается второй `Clone` экземпляра.  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Явные переопределения](../windows/explicit-overrides-cpp-component-extensions.md)