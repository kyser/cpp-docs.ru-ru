---
title: Преобразований в стиле C с - clr (C + +/ CLI) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 384aa6d1d7a4329f52157f1d002dcda2feb5cb8a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="c-style-casts-with-clr-ccli"></a>Приведение в стиле C с использованием параметра /clr (C++/CLI)
Следующий раздел относится только к общеязыковая среда выполнения.  
  
 При использовании с типами CLR, компилятор пытается сопоставить C-стиле приведение к одному из приведения типов, перечисленных ниже, в следующем порядке:  
  
1.  const_cast  
  
2.  safe_cast  
  
3.  safe_cast плюс const_cast  
  
4.  static_cast  
  
5.  static_cast плюс const_cast  
  
 Если ни один из перечисленных выше приведения допустим и тип выражения и целевого типа являются ссылочными типами CLR, приведение в стиле C сопоставляет проверку среды выполнения (инструкции MSIL castclass). В противном случае приведение в стиле считается недействительным, и компилятор выдает ошибку.  
  
## <a name="remarks"></a>Примечания  
 Приведение в стиле не рекомендуется. При компиляции с параметром [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md), используйте [safe_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 В следующем примере показано приведение в стиле, сопоставляется `const_cast`.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 В следующем примере показано приведение в стиле, сопоставляется `safe_cast`.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 В следующем примере показано приведение в стиле, сопоставляется `safe_cast` , а также `const_cast`.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 В следующем примере показано приведение в стиле, сопоставляется `static_cast`.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 В следующем примере показано приведение в стиле, сопоставляется `static_cast` , а также `const_cast`.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 В следующем примере показано приведение в стиле, сопоставляется проверки во время выполнения.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 В следующем примере показано недопустимое приведение в стиле, который указывает компилятору выдавать ошибку.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)