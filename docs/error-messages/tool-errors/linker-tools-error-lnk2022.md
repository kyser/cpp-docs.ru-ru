---
title: Ошибка средств компоновщика LNK2022 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7769bc28dc777ef8d7b82b91b9695356db05a682
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2022"></a>Ошибка средств компоновщика LNK2022  
  
> Сбой операции метаданных (*HRESULT*): *error_message*  
  
Компоновщик обнаружил ошибку при слиянии метаданных. Ошибки в метаданных должны быть разрешены для связывания успешно.  
  
Для диагностики этой проблемы можно выполнить **ildasm-токены** на файлы объектов для определения типов токенов перечислены в `error_message`и просмотрите различия.  В метаданных два различных типа с тем же именем является недопустимым, даже если только атрибут LayoutType отличается.  
  
Одной из причин для LNK2022 — когда типа (например struct) существует в нескольких единиц компиляции с тем же именем, но с конфликтующими определениями, а также при компиляции с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  В этом случае убедитесь, что тип имеет во всех компилируемых объектах совпадают.  Имя типа отображается в `error_message`.  
  
Другая возможная причина LNK2022 — если компоновщик обнаруживает файл метаданных в другом месте, чем было указано для компилятора (с [#using](../../preprocessor/hash-using-directive-cpp.md) ). Убедитесь, что файл метаданных (.dll или .netmodule) находится в том же расположении при передаче в компоновщик, который был передан в компилятор.  
  
При сборке приложения ATL использование макроса `_ATL_MIXED` требуется во всех компилируемых объектах, если он используется хотя бы по одному.  
  
## <a name="example"></a>Пример  
  
В следующем примере определяется пустой тип.  
  
```cpp  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>Пример  
  
В этом примере показано, что нельзя связать двух файлов исходного кода, содержащие типы таким же именем, но разными определениями.  
  
Следующий пример приводит к возникновению ошибки LNK2022.  
  
```cpp  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```