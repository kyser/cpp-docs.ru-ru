---
title: Ошибка компилятора C3738 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3738
dev_langs:
- C++
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf54ba4114c0184871f1c79ca8f1757ae7e78b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3738"></a>Ошибка компилятора C3738
«соглашение_о_вызовах»: соглашение о вызовах явное создание экземпляра должно совпадать с количеством шаблона создаваемых экземпляров  
  
 Рекомендуется не указывать соглашение о вызовах на явное создание экземпляра. Если вам необходимо, то эти соглашения о вызовах должны совпадать.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3738.  
  
```  
// C3738.cpp  
// compile with: /clr  
// processor: x86  
#include <stdio.h>  
template< class T >  
void f ( T arg ) {   // by default calling convention is __cdecl  
   printf ( "f: %s\n", __FUNCSIG__ );  
}  
  
template   
void __stdcall f< int > ( int arg );   // C3738  
// try the following line instead  
// void f< int > ( int arg );  
  
int main () {  
   f(1);  
   f< int > ( 1 );  
}  
```