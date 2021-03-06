---
title: Предупреждение (уровень 1) C4532 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4532
dev_langs:
- C++
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e37d36f565cc63c7cef9954a78e14ed60d676996
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4532"></a>Предупреждение компилятора (уровень 1) C4532
«continue»: переход из блока __finally/finally не определено поведение при обработке завершения  
  
 Компилятор обнаружил одно из следующих ключевых слов:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 что вызвало переход из [__finally](../../cpp/try-finally-statement.md) или [наконец](../../dotnet/finally.md) блок во время аварийного завершения.  
  
 При возникновении исключения, и во время стек развертывается во время выполнения обработчиков завершения ( `__finally` или блоков finally), и код переходит из `__finally` блокировать перед `__finally` завершения блока, поведение не определено. Элемент управления могут не возвращать в развертываемый код, исключение не может быть обработано должным образом.  
  
 Если необходимо перейти из **__finally** блока, сначала проверьте аварийного завершения.  
  
 Следующий пример приводит к возникновению ошибки C4532; просто комментарий преобразовать операторы для разрешения предупреждения.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```