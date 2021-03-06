---
title: Нотация приведения типов и знакомство с safe_cast&lt; &gt; | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- casting
- C-style casts and /clr, motivation for new cast notation
- safe_cast keyword [C++]
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6b9432b40099f9893d7fd270faf5375646fb0493
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cast-notation-and-introduction-of-safecastltgt"></a>Нотация приведения типов и знакомство с safe_cast&lt;&gt;
Нотация приведения типов отличается от управляемых расширений для C++ к Visual C++.  
  
 Изменение существующей структуры является работа и сложнее, от создания начальной структуры. Существуют меньшее число степеней свободы и решение стремится к компромисс между идеальной реструктуризации и каков неосуществимым заданному существующие структурные зависимости.  
  
 Другим примером является расширение языка. В начале 90-х как объектно-ориентированное программирование стало важным принципом, потребность в строго типизированный приведения типов в C++ стала при нажатии. Образование производных типов является пользователя явного преобразования указателя базового класса или ссылка на указатель или производного класса. Приведение требуется явное приведение. Причина заключается в том, что фактический тип указателя базового класса является аспектом среду выполнения. Компилятор таким образом не может проверить его. Или словами, приведения типов, так же, как вызов виртуальной функции, требуется так называемое динамическое разрешение. Это вызывает два вопроса:  
  
-   Почему приведения не требуется в объектно-ориентированном программировании? Недостаточно механизма виртуальных функций? То есть, почему нельзя сказать, что потребность приведения (или преобразование любого рода) происходит сбой разработки?  
  
-   Почему поддержка приведения должен быть проблемой в C++ После того как все это не проблема в объектно ориентированных языках, таких как Smalltalk (или, впоследствии, Java и C#)? Что такое о C++, который упрощает поддержку для приведения типов, которые сложно?  
  
 Виртуальная функция представляет зависящие от типа алгоритм, общий для семейства типов. (Мы не рассматриваем интерфейсов, который не поддерживается в стандарте ISO C++, но доступны программирования в среде CLR и представляют интересную альтернативу разработки). Макет этого семейства, как правило, представлены в виде иерархии классов, в котором имеется абстрактный базовый класс, объявляющий общий интерфейс (виртуальные функции) и набор конкретных производных классов, которые представляют фактические типы семейства в приложении домен.  
  
 Объект `Light` иерархии в компьютере созданные изображения (CGI) домене приложения, например, будет иметь общие атрибуты, такие как `color`, `intensity`, `position`, `on`, `off`, и т. д. Несколько индикаторы можно управлять с помощью общий интерфейс, не беспокоясь, является ли определенный индикатор spotlight, направленный свет, светлый ненаправленная (например, sun) или возможно светлый какой дверцы. В этом случае приведение для конкретного светло типа для виртуального интерфейса не требуется. В рабочей среде скорость играет важную роль. Один можно создавать производные классы и явно вызывать каждый метод, а чтобы таким образом, вместо того чтобы использовать механизм использования виртуальных функций могут выполняться встроенного выполнения вызовов.  
  
 Таким образом одна из причин для производных типов в C++ является отключение механизма виртуальных функций для значительного повышения производительности во время выполнения. (Обратите внимание, что автоматизация ручного оптимизацию активной областью исследования. Однако это более сложной задачей, чем просто явное использование `register` или `inline` ключевое слово.)  
  
 Вторая причина для производных типов выходит за пределы двойное полиморфизма. Один из способов Полиморфизм можно рассматривать как разделение пассивные и динамические пары форм.  
  
 Вызов виртуальных функций (и образование производных типов) представляет динамического использования полиморфизма: происходит выполнение действия на основе фактического типа указателя базового класса при конкретного экземпляра выполнения программы.  
  
 Тем не менее, назначение объект производного класса в его указатель базового класса, является пассивной формой полиморфизма; полиморфизм используется как механизм транспортировки. Это основной использования `Object`, например, предварительно универсального программирования в среде CLR. При использовании пассивно указатель базового класса, выбранный для передачи и хранения данных, обычно предоставляет интерфейс, который является слишком абстрактным. `Object`, например, предоставляют примерно пять методов через его интерфейс; все более конкретные действия необходимо явно производных типов. Например если мы хотим изменить угол света или коэффициент падения, мы бы нисходящее приведение типа явным образом. Виртуальный интерфейс в рамках семейства подтипов может подмножеством всех возможных методов его многочисленных дочерних объектов и поэтому приведения типов всегда необходимо указать в объектно ориентированного языка.  
  
 Образования производных территории необходимости в объектно ориентированный язык, то почему заняло C++ так много времени для добавления одного? Проблема заключается в том, как для предоставления сведений о времени выполнения тип указателя. В случае виртуальная функция информации во время выполнения имеет состоит из двух частей компилятором:  
  
-   Объект класса содержит элемент указателя дополнительной виртуальной таблицы (либо в начале или конце объекта класса; с имеет интересные историю само по себе), посвященное соответствующей виртуальной таблице. Например объект точечного освещения обращается к виртуальной таблице, направленный свет, направленного света виртуальную таблицу и т. д  
  
-   Каждая виртуальная функция имеет связанную фиксированную ячейку в таблице и фактический вызываемый экземпляр представлен адресом, хранимым в таблице. Например, виртуальный `Light` могут быть связаны с ячейкой 0, деструктор `Color` с ячейкой 1 и т. д. Это эффективной, если негибкий стратегии, так как он настраивается во время компиляции и представляет минимальный объем служебных операций.  
  
 Эту проблему, будет, как для обеспечения доступности на указатель на тип данных без изменения размера указателей в C++, добавляя второй адрес или непосредственно добавляя кодировку типа. Это не допустима для программистов (и программ), целесообразно не использовать объектно ориентированном программировании - по-прежнему бывшее сообщества преобладающим пользователей. Была другая возможность встраивать специально предназначенной для типов полиморфных классов, но это будет ввести в заблуждение и затруднить между смешивать два особенно вопросам указателями. Он также не допустима для поддержания таблицу во время выполнения, которая связывает каждый указатель с текущим связанным типом и динамически обновлять ее.  
  
 Затем проблема заключается в пару сообщества пользователей, имеющих различными подходами оба программирования. Решение должно представлять собой компромисс между двумя сообщества, что позволяет каждому не только их целью, но возможность взаимодействия. Это означает, что с решениями обе стороны могут включать затратна и решение наконец целью быть менее точной. Фактическое разрешение связано с определением полиморфного класса: является полиморфный класс, содержащий виртуальные функции. Полиморфный класс поддерживает динамическое типобезопасное. Так как все полиморфных классов содержит дополнительный элемент указателя на связанной виртуальной таблице неполадки устранены Ведение указатель адреса. Информацию о связанном типе, таким образом, могут храниться в расширенной виртуальной таблице. Стоимость типобезопасного приведения типов (почти) локализован для пользователей оборудования.  
  
 Следующая проблема с типобезопасного приведения типов является синтаксис. Так как это приведение исходного предложения Комитет ISO C++ использовать простой синтаксис приведения типов, как показано в примере:  
  
```  
spot = ( SpotLight* ) plight;  
```  
  
 но это был отклонен комитетом, поскольку не разрешает пользователю управлять издержками приведения типов. Если динамическое типобезопасное имеет тот же синтаксис, в предыдущей небезопасной, но статической нотация приведения типов, то оно становится подстановки, и пользователь не отключать дополнительную нагрузку время выполнения, если ненужные и, возможно, слишком много ресурсов.  
  
 Как правило в C++ имеется всегда механизм подавления функции поддержки компилятора. Например, можно отключить механизм использования виртуальных функций с помощью оператора class scope (`Box::rotate(angle)`) или путем вызова виртуального метода с помощью объекта класса (а не указателя или ссылки этого класса). Это не является обязательным в данном языке, но является вопросам реализации, аналогично отключение построения временных компонентов в объявление следующего вида:  
  
```  
// compilers are free to optimize away the temporary  
X x = X::X( 10 );  
```  
  
 Чтобы предложение было передано для дальнейшего рассмотрения и несколько альтернативных нотаций рассматривались и возвращены в комитет по тот был формы (`?type`), что указано его неопределенные - то есть динамической природы. Это предлагает пользователю переключаться между двумя формами — статической или динамической -, но никто не слишком довольны его. Поэтому было начинать сначала. Третья и успешно представляет собой теперь Стандартная `dynamic_cast<type>`, которой были обобщены, чтобы набор из четырех новых-нотаций приведения типов.  
  
 В C++ стандарта ISO `dynamic_cast` возвращает `0` при применены к несоответствующему типу указателя и выдает `std::bad_cast` исключения при применении к ссылочному типу. В управляемых расширениях для C++ применение `dynamic_cast` управляемому ссылочному типу (из-за представления указателя) всегда возвращается `0`. `__try_cast<type>` была введена как аналог вызову исключений `dynamic_cast`, за исключением того, что он выдает `System::InvalidCastException` в случае сбоя приведения.  
  
```  
public __gc class ItemVerb;  
public __gc class ItemVerbCollection {  
public:  
   ItemVerb *EnsureVerbArray() [] {  
      return __try_cast<ItemVerb *[]>  
         (verbList->ToArray(__typeof(ItemVerb *)));  
   }  
};  
```  
  
 В новом синтаксисе `__try_cast` была приведена как `safe_cast`. Ниже приведен тот же фрагмент кода в новом синтаксисе.  
  
```  
public ref class ItemVerb;  
public ref class ItemVerbCollection {  
public:  
   array<ItemVerb^>^ EnsureVerbArray() {  
      return safe_cast<array<ItemVerb^>^>  
         ( verbList->ToArray( ItemVerb::typeid ));  
   }  
};  
```  
  
 В управляемом коде очень важно для обеспечения проверяемый код, ограничивая возможность программистам приведения между типами таким образом, чтобы оставить непроверяемый код. Это ключевой аспект динамического программирования, представленного в новом синтаксисе. По этой причине экземпляры приведения старого стиля приведена внутренне как во время выполнения таким образом, например:  
  
```  
// internally recast into the   
// equivalent safe_cast expression above  
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );   
```  
  
 С другой стороны поскольку полиморфизм имеет активный и пассивный режим, иногда бывает необходимо выполнять приведение просто для получения доступа к API невиртуальный подтипа. Это может произойти, например, к элементам класса, необходимо адрес любой тип в иерархии (пассивный полиморфизм используется в качестве механизма передачи), но для которых известен фактический экземпляр в контексте определенной программы. В этом случае необходимости проверки во время выполнения приведения может быть неприемлемо дополнительной нагрузкой. Если в качестве языка программирования управляемых систем нового синтаксиса, он должен предоставить средства, позволяющие во время компиляции (то есть статический) производных типов. Поэтому приложение `static_cast` нотации может оставаться в производных типов во время компиляции:  
  
```  
// ok: cast performed at compile-time.   
// No run-time check for type correctness  
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));  
```  
  
 Проблема заключается не может гарантировать, что программист выполнив `static_cast` правильное и намерениями; то есть так, чтобы было проверяемым управляемому коду. Это является более срочным проблемой с парадигмой динамического программирования чем машинного, но не достаточно внутри системы, язык для запрета пользователю переключаться между статическим и приведение во время выполнения.  
  
 Однако, возникает ловушки производительности и ошибок в новом синтаксисе. В программировании собственного кода, нет разницы в производительности между нотации старый и новый стиль `static_cast` нотации. Но в новом синтаксисе значительно дороже, чем использование новой нотации приведения старого стиля `static_cast` нотации. Причина заключается в том, что компилятор выполняет внутреннее преобразование нотации старого стиля в проверки во время выполнения, которая создает исключение. Кроме того, он также изменяет профиль выполнения кода, так как он вызывает исключение перевод работу приложения — может быть рационально, однако та же ошибка не вызовет исключение, если `static_cast` использовались нотации. Можно утверждать, что это помогает пользователям продукта в формате новый стиль. Но только в случае сбоя. в противном случае это приведет к появлению программы, использующие старую нотацию будут выполняться значительно медленнее без видимых причин, аналогично следующие проблемы программиста C:  
  
```  
// pitfall # 1:   
// initialization can remove a temporary class object,   
// assignment cannot  
Matrix m;  
m = another_matrix;  
  
// pitfall # 2: declaration of class objects far from their use  
Matrix m( 2000, 2000 ), n( 2000, 2000 );  
if ( ! mumble ) return;  
```  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C + +/ CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [C-стиль приведения с параметром/CLR (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)