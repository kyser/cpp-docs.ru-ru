---
title: Класс Platform::WeakReference | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8db5c855b6a377a0202183d48b8fd34e93b6072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformweakreference-class"></a>Класс Platform::WeakReference
Представляет слабую ссылку на экземпляр класса ссылок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>Параметры  
  
### <a name="members"></a>Участники  
  
### <a name="constructors"></a>Конструкторы  
  
|Член|Описание|  
|------------|-----------------|  
|[WeakReference::WeakReference](#ctor)|Инициализирует новый экземпляр класса WeakReference.|  
  
### <a name="methods"></a>Методы  
  
|Член|Описание|  
|------------|-----------------|  
|[WeakReference::Resolve](#resolve)|Возвращает дескриптор базовому классу ссылок или значение nullptr, если объект больше не существует.|  
  
### <a name="operators"></a>Операторы  
  
|Член|Описание|  
|------------|-----------------|  
|[WeakReference::operator=](#operator-assign)|Присваивает новое значение объекту WeakReference.|  
|[WeakReference::operator BoolType](#booltype)|Реализует безопасный шаблон bool.|  
  
### <a name="remarks"></a>Примечания  
 Класс WeakReference сам не является классом ссылок и поэтому не наследуется от Platform::Object^ и не может использоваться в сигнатуре открытого метода.  

## <a name="operator-assign"></a> WeakReference::operator =
Присваивает значение WeakReference.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));    
WeakReference& operator=(const WeakReference& otherArg);   
WeakReference& operator=(WeakReference&& otherArg);    
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg); 
```  
  
### <a name="remarks"></a>Примечания  
 Последняя перегрузка в списке выше позволяет назначить класс ссылок переменной WeakReference. В этом случае выполняется нисходящее приведение типа для класса ссылок [Platform::Object](../cppcx/platform-object-class.md)^. Восстановить исходный тип позднее путем задания его в качестве аргумента для параметра типа в [WeakReference::Resolve\<T >](#resolve) функции-члена.  
  
## <a name="booltype"></a> WeakReference::operator BoolType
Реализует безопасный шаблон bool для класса WeakReference. Не предназначен для явного вызова в коде.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a> Метод WeakReference::Resolve (пространство имен Platform)
Возвращает дескриптор для исходного класса ссылок или `nullptr`, если объект больше не существует.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>Параметры  
  
### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Дескриптор класс ссылок, с которым ранее был связан объект WeakReference, или значение nullptr.  
  
### <a name="example"></a>Пример  
 Это описание для примера кода.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Обратите внимание, что параметр типа — T, а не T^.  
  
 
## <a name="ctor"></a> Конструктор WeakReference::WeakReference
Предоставляет различные способы построения WeakReference.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& otherArg);  
WeakReference(WeakReference&& otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);  
```  
### <a name="example"></a>Пример  
  
```cpp    
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();    
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)