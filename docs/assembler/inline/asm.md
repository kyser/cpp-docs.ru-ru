---
title: __asm | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- __asm
- __asm_cpp
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], vs. asm blocks
- __asm keyword [C++]
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e09f6af92839c6113c9c5ba375a1583bcf7149
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="asm"></a>__asm
**Блок, относящийся только к системам Microsoft**  
  
 Ключевое слово `__asm` вызывает встроенный ассемблер и может отображаться везде, где допустим оператор С или С++. Он не может отображаться самостоятельно. За ним должна следовать инструкция по сборке, группа инструкций, заключенная в круглые скобки, либо, в крайнем случае, пустая пара круглых скобок. Термин "блок `__asm`" в этом разделе относится к любой инструкции или группе инструкций, в скобках или без них.  
  
> [!NOTE]
>  Поддержка стандартного ключевого слова C++ `asm` в Visual C++ ограничена тем фактом, что компилятор не создаст ошибку по ключевому слову. Однако блок `asm` не создаст никакого значимого кода. Используйте `__asm` вместо `asm`.  
  
 Синтаксис:  
  
 __asm *инструкции ассемблера* [;]  
  
 __asm { *список инструкций сборке* } [;]  
  
## <a name="grammar"></a>Грамматика  
 `__asm`  `assembly-instruction`  `;`необязательно  
  
 `__asm {`  `assembly-instruction-list`  `};`необязательно  
  
 *список инструкций сборке*:  
 `assembly-instruction` `;`необязательно  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;`необязательно  
  
 При использовании без круглых скобок ключевое слово `__asm` означает, что остальная часть строки — это оператор на языке сборки. При использовании с фигурными скобками оно означает, что каждая строка между скобками — это оператор на языке сборки. Для обеспечения совместимости с предыдущими версиями `_asm` является синонимом `__asm`.  
  
 Поскольку ключевое слово `__asm` является разделителем операторов, можно также помещать инструкции ассемблера на одной строке:  
  
 До Visual C++ 2005 эта инструкция  
  
```  
__asm int 3  
```  
  
 не вызывала машинного кода, создаваемого при компиляции с параметром **/CLR**; компилятор преобразовывал инструкцию в инструкцию прерывания среды CLR.  
  
 `__asm int 3` теперь приводит к созданию машинного кода для функции. Если функция должна вызвать точку останова в коде и этой функции, скомпилированные в MSIL, используйте [__debugbreak](../../intrinsics/debugbreak.md).  
  
## <a name="example"></a>Пример  
 Следующий фрагмент кода — это простой блок `__asm`, заключенный в фигурные скобки:  
  
```  
__asm {  
   mov al, 2  
   mov dx, 0xD007  
   out dx, al  
}  
```  
  
 Кроме того, можно поставить `__asm` перед каждой инструкцией по сборке.  
  
```  
__asm mov al, 2  
__asm mov dx, 0xD007  
__asm out dx, al  
```  
  
 Поскольку ключевое слово `__asm` является разделителем операторов, можно также помещать инструкции по сборке на одной строке.  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 Все три примера создают один и тот же код, но первый стиль (где блок `__asm` заключен в фигурные скобки) имеет некоторые преимущества. Фигурные скобки четко отделяют код сборки от кода С или С++ и позволяют избежать лишнего повторения ключевого слова `__asm`. Скобки также помогают избежать неоднозначности. Если требуется поместить оператор C или C++ на одной строке в виде блока `__asm`, необходимо заключить блок в фигурные скобки. Без фигурных скобок компилятор не может определить, где прекращается код сборки и начинаются операторы C или C++. Наконец, поскольку текст в фигурных скобках имеет тот же формат, что и обычный текст MASM, можно легко вырезать и вставить текст из существующих исходных файлов MASM.  
  
 В отличие от фигурных скобок в C и C++ фигурные скобки, в которые заключается блок `__asm`, не влияют на область видимости переменной. Можно также разместить блоки `__asm` в виде вложения, вложение не влияет на область видимости переменной.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../../cpp/keywords-cpp.md)   
 [Встроенный сборщик](../../assembler/inline/inline-assembler.md)