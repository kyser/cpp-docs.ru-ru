---
title: 'Как: преобразование типа System::String в стандартную строку | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, converting System::String to standard string
- string conversion, System::String
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1c8bbab264fcb790017aebcdc48abf18168a7b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-systemstring-to-standard-string"></a>Практическое руководство. Преобразование строки System::String в стандартную строку
Вы можете преобразовать <xref:System.String> для `std::string` или `std::wstring`, без использования `PtrToStringChars` в Vcclr.h.  
  
## <a name="example"></a>Пример  
  
```  
// convert_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace std;  
using namespace System;  
  
void MarshalString ( String ^ s, string& os ) {  
   using namespace Runtime::InteropServices;  
   const char* chars =   
      (const char*)(Marshal::StringToHGlobalAnsi(s)).ToPointer();  
   os = chars;  
   Marshal::FreeHGlobal(IntPtr((void*)chars));  
}  
  
void MarshalString ( String ^ s, wstring& os ) {  
   using namespace Runtime::InteropServices;  
   const wchar_t* chars =   
      (const wchar_t*)(Marshal::StringToHGlobalUni(s)).ToPointer();  
   os = chars;  
   Marshal::FreeHGlobal(IntPtr((void*)chars));  
}  
  
int main() {  
   string a = "test";  
   wstring b = L"test2";  
   String ^ c = gcnew String("abcd");  
  
   cout << a << endl;  
   MarshalString(c, a);  
   c = "efgh";  
   MarshalString(c, b);  
   cout << a << endl;  
   wcout << b << endl;  
}  
```  
  
```  
test  
abcd  
efgh  
```  
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)