---
title: Директивы препроцессора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b73f6ce579f94d38621820a63888dc0aa5a75863
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-directives"></a>Директивы препроцессора
Директивы препроцессора, таких как `#define` и **#ifdef**, обычно используются, чтобы исходные программы легко изменять и компилировать в разных средах выполнения. Директивы в файле исходного кода позволяют препроцессору выполнять определенные действия. Например, препроцессор может заменять токены в тексте, вставлять содержимое других файлов в файл исходного кода или отключать компиляцию части файла путем удаления разделов текста. Строки препроцессора распознаются и выполняются до расширения макросов. Поэтому если макрос разворачивается в нечто, похожее на команду препроцессора, эта команда не распознается препроцессором.  
  
 В операторах препроцессора используется тот же набор символов, что и в операторах файла исходного кода, но escape-последовательности не поддерживаются. Кодировка, используемая в операторах препроцессора совпадает со значением [кодировки выполнения](http://msdn.microsoft.com/en-us/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Препроцессор также распознает отрицательные значения символов.  
  
 Препроцессор распознает следующие директивы:  
  
|||||  
|-|-|-|-|  
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|  
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 Знак числа (**#**) должна быть первой непробельный символ в строке, содержащей директиву; символы-разделители могут появляться между решетки и первой буквой директивы. Некоторые директивы содержат аргументы или значения. Любой текст, следующий директивы (за исключением аргумента или значения, часть директивы) должен предваряться разделителем однострочного комментария (**//**) или заключаться в разделители комментариев ( **/ \* \*/**). Можно продолжить строки, содержащие директивы препроцессора, непосредственно предшествующий маркер конца строки обратную косую черту (**\\**).  
  
 Директивы препроцессора могут находиться в любом месте файла исходного кода, но применяются только к оставшейся части файла.  
  
## <a name="see-also"></a>См. также  
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)   
 [Предустановленные макросы](../preprocessor/predefined-macros.md)   
 [Справочник по препроцессору в C/C++](../preprocessor/c-cpp-preprocessor-reference.md)