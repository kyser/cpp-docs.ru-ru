---
title: Свойства (C + +/ CX) | Документы Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 64c7bc56-3191-4cd5-bdf4-476d07d285d5
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6393b5e5849ab2198fa8d084c2c1d15838c69bdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="properties-ccx"></a>Свойства (C++/CX)
Типы среды выполнения Windows предоставляют открытые данные в виде свойств. Клиентский код обращается к свойству как открытым данным-членам. Внутренне свойство реализуется в виде блока, содержащего метод доступа get или set, или оба эти метода. С помощью методов доступа можно выполнять дополнительные действия до или после получения значения; например, можно вызывать события или выполнять проверки.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства содержится в закрытой переменной (называемой *резервным хранилищем*), принадлежащей к тому же типу, что и само свойство. Свойство может одновременно содержать метод доступа set, присваивающий значение резервному хранилищу, и метод доступа get, извлекающий значение резервного хранилища. Свойство доступно только для чтения, если оно предоставляет только метод доступа get, только для записи, если предоставляет только метод доступа set, и для чтения и записи, если предоставляет оба метода доступа.  
  
 *Тривиальное* свойство — это свойство, доступное для чтения и записи, для которого компилятор автоматически реализует методы доступа и резервное хранилище. Доступ к реализации компилятора для вас невозможен. Впрочем, вы можете объявить пользовательское свойство и явно объявить его методы доступа и резервное хранилище. Внутри метода доступа можно реализовать любую необходимую логику, например проверку входных данных метода доступа set, вычисление значения с использованием значения свойства или вызов события при изменении свойства.  
  
 Когда создается экземпляр класса ссылки C++/CX, его память перед вызовом конструктора инициализируется нулями, таким образом, всем свойствам в качестве значения по умолчанию назначается ноль или nullptr.  
  
### <a name="examples"></a>Примеры  
 В следующем примере кода показано, как объявить свойство и обратиться к нему. Первое свойство `Name`является *тривиальным* , поскольку компилятор автоматически создает метод доступа `set` , метод доступа `get` и резервное хранилище.  
  
 Второе свойство `Doctor`доступно только для чтения, поскольку для него указан *блок property* , в котором явно объявлен только метод доступа `get` . Поскольку блок property объявлен, необходимо явно объявить резервное хранилище, то есть закрытую переменную `doctor_`класса String^. Обычно свойство, доступное только для чтения, просто возвращает значение резервного хранилища. Только сам класс может задавать значение резервного хранилища, обычно это происходит в конструкторе.  
  
 Третье свойство `Quantity`доступно для чтения и записи, так как в нем объявлен блок property, где объявлены оба метода доступа `set` и `get` .  
  
 Метод доступа `set` выполняет определенную пользователем проверку допустимости присваиваемого значения. В отличие от C#, здесь имя *value* — это просто идентификатор параметра в методе доступа `set` , оно не является ключевым словом. Если *value* не больше нуля, вызывается исключение Platform::InvalidArgumentException. В противном случае резервному хранилищу `quantity_`задается присваиваемое значение.  
  
 Обратите внимание, что свойство невозможно инициализировать в списке членов. Хотя переменные резервного хранилища можно инициализировать в списке членов.  
  
 [!code-cpp[cx_properties#01](../cppcx/codesnippet/CPP/cx_properties/class1.h#01)]  
  
## <a name="see-also"></a>См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)