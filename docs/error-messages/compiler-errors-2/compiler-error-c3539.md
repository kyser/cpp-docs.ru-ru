---
title: Ошибка компилятора C3539 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f704bd283ab5228a8988d587707e978aa5b49e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3539"></a>Ошибка компилятора C3539
«Тип»: аргумент шаблона не может быть типом, содержащим «auto»  
  
 Указанный тип аргумента шаблона не может содержать `auto` ключевое слово.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не указывайте аргумент шаблона с `auto` ключевое слово.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)