---
title: Ошибка компилятора C3345 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3345
dev_langs:
- C++
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6b3a021d9c747e4ec30278d8a22bde899cb39a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3345"></a>Ошибка компилятора C3345
"идентификатор": недопустимый идентификатор для имени модуля  
  
 *Идентификатор* для модуля содержит как минимум один недопустимый символ. В правильном идентификаторе первым символом должна быть буква, подчеркивание или расширенный символ ANSI (0x80-FF), а все последующие символы должны быть буквами, цифрами, подчеркиваниями или расширенными символами ANSI.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что *идентификатор* не содержит пробелы или другие недопустимые символы.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3345, поскольку параметр `name` атрибута `module` содержит пробел.  
  
```  
// cpp_attr_name_module.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// C3345 expected  
[module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")]   
// Try the following line instead  
//[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// Module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [__iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Модуль](../../windows/module-cpp.md)