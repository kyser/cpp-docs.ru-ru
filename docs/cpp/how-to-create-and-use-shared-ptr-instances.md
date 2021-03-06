---
title: 'Как: Создание и использование экземпляров shared_ptr | Документы Microsoft'
ms.custom: how-to
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a2aad184a1f388df6f7a6941aa9e5f302f35b12
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-and-use-sharedptr-instances"></a>Практическое руководство. Создание и использование экземпляров shared_ptr
`shared_ptr` Тип является интеллектуальным указателем в стандартной библиотеке C++, которая предназначена для сценариев, в которых возможно более одного владельца, для управления временем жизни объекта в памяти. После инициализации `shared_ptr` можно скопировать его, передать его по значению в аргументы функций и назначать других `shared_ptr` экземпляров. Все экземпляры, выберите тот же объект и открывать общий доступ к одной «блок управления», которое увеличивает и уменьшает счетчик ссылок всякий раз, когда новый `shared_ptr` добавляется, выходит за пределы области или сбрасывается. Когда число ссылок достигает нуля, блок управления удаляет ресурсов памяти и самого себя.  
  
 На следующем рисунке показано несколько `shared_ptr` экземпляров, которые указывают на расположение в памяти.  
  
 [![Общий указатель](../cpp/media/shared_ptr.png "shared_ptr")](assetId:///9785ad08-31d8-411a-86a9-fb9cd9684c27)  
  
## <a name="example"></a>Пример  
 По возможности используйте [make_shared](../standard-library/memory-functions.md#make_shared) функция, создающая `shared_ptr` при создании ресурсов памяти в первый раз. `make_shared` — безопасный в отношении исключений. Использует же вызов, чтобы выделить память для блока управления и ресурса и тем самым снизить расходы на построение. Если вы не используете `make_shared`, то необходимо использовать явную нового выражения для создания объекта, прежде чем передать его в `shared_ptr` конструктора. В следующем примере показаны различные способы объявления и инициализации `shared_ptr` вместе с новым объектом.  
  
 [!code-cpp[stl_smart_pointers#1](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить и инициализировать `shared_ptr` экземпляры, которые принимают на общего владельца объекта, которое уже было выделено на другое `shared_ptr`. Предполагается, что `sp2` инициализации `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#2](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]  
  
## <a name="example"></a>Пример  
 `shared_ptr` также полезен при контейнеры стандартной библиотеки C++ при использовании алгоритмов, которые копируются элементы. Можно создать оболочку элементов в `shared_ptr`и скопировать его в другие контейнеры, тот факт, что основная память является допустимым, при условии, что он нужен и больше не. В следующем примере показано, как использовать `replace_copy_if` алгоритм на `shared_ptr` экземпляров в векторе.  
  
 [!code-cpp[stl_smart_pointers#4](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]  
  
## <a name="example"></a>Пример  
 Можно использовать `dynamic_pointer_cast`, `static_pointer_cast`, и `const_pointer_cast` для приведения `shared_ptr`. Эти функции напоминают `dynamic_cast`, `static_cast`, и `const_cast` операторы. Приведенный ниже показано, как проверить производный тип каждого элемента в вектор `shared_ptr` из базовых классов, скопируйте элементы и отображения сведений о них.  
  
 [!code-cpp[stl_smart_pointers#5](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]  
  
## <a name="example"></a>Пример  
 Можно передать `shared_ptr` в другую функцию следующим образом:  
  
-   Передайте `shared_ptr` по значению. Это вызывает конструктор копирования, увеличивает счетчик ссылок и делает вызываемый объект владельца. Имеется небольшое количество издержек в этой операции, может оказаться слишком дорогим в зависимости от того, сколько `shared_ptr` объекты передаются. Используйте этот параметр, когда код контракта (подразумеваемых или явных) между вызывающий и вызываемый объекты требует вызываемый объект владельца.  
  
-   Передайте `shared_ptr` ссылкой или константную ссылку. В этом случае не увеличивается счетчик ссылок, а вызываемый объект можно получить доступ к указатель при условии, что вызывающий объект не выходят за пределы области. Или можно ограничиться созданием вызываемый объект `shared_ptr` на основе ссылки и тем самым становятся общего владельца. Используйте этот параметр, когда вызывающий объект не имеет сведений о вызываемого метода, или когда необходимо передать `shared_ptr` и хотите избежать копирования для повышения производительности.  
  
-   Передайте базовый указатель или ссылку на базовый объект. Это позволяет вызываемым объектом использовать объект, но не включайте его общим владельцем или увеличить время существования. Если вызываемый объект создает `shared_ptr` из необработанного указателя новый `shared_ptr` не зависит от исходного и не влияет на основной ресурс. Используйте этот параметр, если контракт между вызывающий и вызываемый объекты четко указывает, что вызывающий объект сохраняет владение `shared_ptr` времени существования.  
  
-   При определении способ передачи `shared_ptr`, определяет, имеет ли вызываемый объект владеть основной ресурс. «Владелец» представляет собой объект или функцию, которая может поддерживать в основной ресурс активном состоянии до тех пор, пока она нужна. Если вызывающий объект должен гарантировать, что вызываемый объект увеличить срок указателя за пределы ее времени существования (функции), используется первый параметр. Если вам не выходит ли вызываемый объект время существования, передачи по ссылке и позволить вызываемый объект скопировать его или нет.  
  
-   При необходимости предоставьте доступ к функции поддержки для указателя базового и знать вспомогательная функция будет просто использовать указатель и возвращения до возврата вызывающей функции, то эта функция не имеет владеть указателя базового. Он просто должен иметь доступ к указатель за время существования вызывающего `shared_ptr`. В этом случае безопасная передача `shared_ptr` ссылкой, или передайте необработанный указатель или ссылку на базовый объект. Передача таким образом предоставляет небольшого увеличения производительности и может также помочь express намерениям программирования.  
  
-   В некоторых случаях для примера в `std:vector<shared_ptr<T>>`, необходимо передавать каждый `shared_ptr` тело лямбда-выражения или объекта функции по имени. Если лямбда-выражение или функция не является хранение указатель, то передайте `shared_ptr` по ссылке, чтобы избежать вызова конструктора копии для каждого элемента.    
  
## <a name="example"></a>Пример  
 В следующем примере показан способ `shared_ptr` перегружает различные операторы сравнения, чтобы включить Сравнение указателей памяти, которая принадлежит `shared_ptr` экземпляров.  
  
 [!code-cpp[stl_smart_pointers#3](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Интеллектуальные указатели](../cpp/smart-pointers-modern-cpp.md)