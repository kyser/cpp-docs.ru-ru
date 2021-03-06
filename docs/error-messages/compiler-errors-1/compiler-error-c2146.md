---
title: Ошибка компилятора C2146 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2146
dev_langs:
- C++
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73367284a8c13316d344a4cff87ccae4ee7c832d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2146"></a>Ошибка компилятора C2146
Синтаксическая ошибка: отсутствует «токен» перед идентификатором «идентификатор»  
  
 Компилятор ожидал `token` и найти `identifier` вместо него.  Возможные причины:  
  
1.  Ошибка проверки орфографии или регистр букв.  
  
2.  Отсутствует спецификатор типа в объявлении идентификатора.  
  
 Эта ошибка может быть вызвана орфографическую ошибку. Ошибка [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) обычно предшествует эту ошибку.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2146.  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## <a name="example"></a>Пример  
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: отсутствует `typename` ключевое слово.  
  
 В следующем примере компилируется в Visual Studio .NET 2002, но завершается ошибкой в Visual Studio .NET 2003:  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## <a name="example"></a>Пример  
 Вы также эта ошибка возникает в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: явной специализации не удается найти параметры шаблона из первичного шаблона.  
  
 Использование `T` из первичного шаблона недопустимо в явной специализации. Чтобы код функционировал в версии Visual C++ в Visual Studio .NET 2003 и Visual Studio .NET замените все экземпляры параметра шаблона в специализации явно специализированный тип.  
  
 В следующем примере компилируется в Visual Studio .NET, но завершается ошибкой в Visual Studio .NET 2003:  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```