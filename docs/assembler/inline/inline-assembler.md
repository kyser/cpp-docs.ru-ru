---
title: Встроенный ассемблер | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5236bebdeef2db519556d3dace4c20d9529d0e23
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="inline-assembler"></a>Встроенный сборщик
**Блок, относящийся только к системам Microsoft**  
  
 Язык ассемблера может служить для целого ряда целей, например для повышения скорости работы программы, сокращения потребления памяти и управления оборудованием. Встроенный код на ассемблере можно использовать для внедрения инструкций языка ассемблера непосредственно в исходные программы С и С++ без дополнительных шагов по сборке и компоновке. Встроенный код на ассемблере встроен в компилятор, поэтому вам не требуется отдельный сборщик для языка ассемблера, такой как Microsoft Macro Assembler (MASM).  
  
> [!NOTE]
>  Программы со встроенным кодом на языке ассемблера не всегда можно перенести на другие аппаратные платформы. При разработке переносимой версии старайтесь не использовать встроенный код ассемблера.  
  
 Встроенный код на ассемблере не поддерживается в процессорах ARM и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  В следующих разделах объясняется, как использовать встроенный код на ассемблере в программах Visual C/C++ для процессоров x86.  
  
-   [Обзор встроенного кода на ассемблере](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Преимущества встроенного кода на ассемблере](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [__asm](../../assembler/inline/asm.md)  
  
-   [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Использование и сохранение регистров во встроенном коде на языке ассемблера](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [Переход к меткам во встроенном коде на языке ассемблера](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Вызов функций C во встроенном коде на языке ассемблера](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Вызов функций C++ во встроенном коде на языке ассемблера](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [Определение блоков __asm как макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Оптимизация встроенного кода на языке ассемблера](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора и язык ассемблера](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [Справочник по языку C++](../../cpp/cpp-language-reference.md)