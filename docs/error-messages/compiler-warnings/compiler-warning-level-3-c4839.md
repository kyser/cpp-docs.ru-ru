---
title: Предупреждение (уровень 3) C4839 компилятора | Документы Microsoft
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4839
dev_langs:
- C++
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b72289eef03c56356865b0b62a999c417da570a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4839"></a>Компилятор C4839 предупреждение (уровень 4)

> Нестандартное использование класса*типа*"как аргумент для функции с переменным числом аргументов

В Visual Studio 2017 г., классов или структур, которые передаются с переменным числом аргументов функции например `printf` должен быть тривиально копируемых. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4839:

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Чтобы исправить эту ошибку, можно вызвать функцию-член, возвращающую тип, доступный для простого копирования,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

или выполнить статическое приведение для преобразования объекта перед его передачей:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Для строк построен и управляются с помощью `CStringW`, предоставленный `operator LPCWSTR()` следует использовать для приведения `CStringW` объекта указатель C, ожидаемый формат строки.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```