---
title: "Пространство имен Platform::Collections | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Пространство имен Platform::Collections"
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Пространство имен Platform::Collections
Пространство имен Platform::Collection содержит классы `Map`, `MapView`, `Vector` и `VectorView`. Эти классы являются конкретными реализациями соответствующих интерфейсов, которые определены в пространстве имен [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645). Конкретные типы коллекций не могут переноситься через интерфейс ABI \(например, когда программа JavaScript или C\# вызывает компонент C\+\+\), но они могут неявно преобразоваться в соответствующие типы интерфейсов. Например, если вы реализуете открытый метод, который заполняет и возвращает коллекцию, используйте [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) для внутренней реализации коллекции и [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) в качестве возвращаемого типа. Дополнительные сведения см. в разделах [Коллекции](../cppcx/collections-c-cx.md) и [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
 Можно создать Platform::Collections::Vector из [std::vector](../Topic/vector%20Class%201.md) и [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) из [std::map](../standard-library/map-class.md).  
  
 Кроме того, пространство имен Platform::Collection обеспечивает поддержку итераторов со вставкой в конец коллекции и итераторов ввода, а также итераторов `Vector` и `VectorView`.  
  
 Для использования типов из пространства имен Platform::Collection необходимо включить \(с помощью директивы `#include`\) заголовок collection.h.  
  
## Синтаксис  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
## Члены  
 Это пространство имен содержит следующие члены.  
  
|Имя|Описание|  
|---------|--------------|  
|[Класс Platform::Collections::BackInsertIterator](../cppcx/platform-collections-backinsertiterator-class.md)|Представляет итератор, который вставляет элемент в конец коллекции.|  
|[Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)|Представляет итератор, который вставляет элемент в начало коллекции.|  
|[Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)|Представляет изменяемую коллекцию пар "ключ\-значение", доступ к которым можно получить по ключу. Аналогично [std::map](../standard-library/map-class.md).|  
|[Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)|Представляет доступную только для чтения коллекцию пар "ключ\-значение", доступ к которым можно получить по ключу.|  
|[Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)|Представляет изменяемую последовательность элементов. Аналогично [std::vector](../Topic/vector%20Class%201.md).|  
|[Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)|Представляет итератор, который обходит коллекцию `Vector`.|  
|[Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)|Представляет доступную только для чтения последовательность элементов.|  
|[Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)|Представляет итератор, который обходит коллекцию `VectorView`.|  
  
## Иерархия наследования  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)  
  
## Требования  
 **Метаданные:** platform.winmd  
  
 **Пространство имен:** Platform::Collections  
  
 **Параметр компилятора:** \/ZW  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)