---
title: Предупреждение средств компоновщика LNK4248 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3b67661d1ad260f388f8425420711ae2f708ce3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4248"></a>Предупреждение средств компоновщика LNK4248
неразрешенная лексема typeref (лексема) для «тип»; образ нельзя запустить  
  
 Тип не имеет определения в метаданных MSIL.  
  
 Ошибка LNK4248 возникает при наличии прямого объявления типа в модуль MSIL (скомпилированный с **/CLR**), если ссылается на тип и компонуется с собственным модулем, который содержит определения для модуль MSIL тип.  
  
 В этом случае компоновщик предоставит определение собственного типа в метаданных MSIL, и это может обеспечить правильное поведение.  
  
 Тем не менее если объявление переадресации типа является типом CLR, затем определение собственного типа компоновщика может не быть правильным  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите определение типа в модуль MSIL.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK4248. Определите структуру a. для решения.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере приведено определение переадресации типа.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK4248.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```