---
title: Предупреждение | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- warning_CPP
- vc-pragma.warning
dev_langs:
- C++
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b739a3f72416b6ab58cbdba45a496e10fef4424
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="warning-pragma"></a>warning-прагма
Включает выборочное изменение поведения предупреждающих сообщений компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```
#pragma warning(   
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## <a name="remarks"></a>Примечания  
Доступны следующие параметры описателей предупреждений.  
  
|Описатель предупреждения|Значение|  
|------------------------|-------------|  
|`1, 2, 3, 4`|Применение данного уровня к определенным предупреждениям. Также включается указанное предупреждение, отключенное по умолчанию.|  
|`default`|Сброс поведения предупреждения до значения по умолчанию. Также включается указанное предупреждение, отключенное по умолчанию. Предупреждение создается на документированном уровне по умолчанию.<br /><br /> Дополнительные сведения см. в разделе [компилятора предупреждения выключенные по умолчанию](../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|`disable`|Запрет на выдачу указанных предупреждающих сообщений.|  
|`error`|Сообщение об указанных предупреждениях как об ошибках.|  
|`once`|Отображение указанных сообщений только один раз.|  
|`suppress`|Помещение текущего состояния директивы pragma в стек, отключение указанного предупреждения для следующей строки, и отображение стека предупреждений для сброса состояния директивы pragma.|  
  
 В приведенном ниже операторе кода показано, что параметр `warning-number-list` может содержать несколько номеров предупреждений и что в одной директиве pragma можно указать несколько параметров `warning-specifier`.  
  
```cpp  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 Это функционально эквивалентно следующему коду.  
  
```cpp  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 Компилятор добавляет 4000 к любому номеру предупреждения от 0 до 999.  
  
 Для номеров предупреждений в диапазоне от 4700 до 4999, связанных с созданием кода, состояние предупреждения, действующее на момент обнаружения компилятором открывающей фигурной скобки функции, будет действовать для остальной части функции. Использование директивы pragma `warning` в функции для изменения состояния предупреждения с номером больше 4699 возможно только после конца функции. В следующем примере показано правильное размещение директив pragma `warning` для отключения предупреждающего сообщения о создании кода и его последующего восстановления.  
  
```cpp  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 Обратите внимание, что во всем теле функции последний параметр директивы pragma `warning` будет действовать для всей функции.  
  
## <a name="push-and-pop"></a>Отправка и отображение  
 `warning` Pragma также поддерживает следующий синтаксис, где `n` представляет порог предупреждений (от 1 до 4).  
  
 `#pragma warning( push [ , n ] )`  
  
 `#pragma warning( pop )`  
   
 Директива pragma `warning( push )` сохраняет текущее состояние предупреждения для каждого предупреждения. Директива pragma `warning( push, n )` сохраняет текущее состояние для каждого предупреждения и задает глобального порога предупреждений `n`.  
  
 Директива pragma `warning( pop )` извлекает последнее состояние предупреждения, помещаются в стек. Любые изменения, внесенные в состояние предупреждения между `push` и `pop`, отменяются. Рассмотрим следующий пример.  
  
```cpp  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 В конце этого кода `pop` восстанавливает состояние каждого предупреждения (включает 4705, 4706 и 4707), действующее в начале кода.  
  
 При написании файлов заголовков `push` и `pop` можно использовать для гарантии того, что изменения состояния предупреждения, внесенные пользователем, не помешают правильной компиляции заголовков. Используйте `push` в начале заголовка, а `pop` — в конце. Например, если имеется заголовок, который не компилируется правильно на пороге предупреждений 4, следующий код изменит порог предупреждений на 3, а затем восстановит исходный порог предупреждений в конце заголовка.  
  
```cpp  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 Дополнительные сведения о компиляторе, параметры, которые позволяют отключить предупреждения, в разделе [/FI](../build/reference/fi-name-forced-include-file.md) и [/w](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)