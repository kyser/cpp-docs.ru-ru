---
title: Автоматическая параллелизация и автоматическая векторизация | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1ec19065647f78b4d9b2665003c0aa3a2795ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Автоматическая параллелизация и автоматическая векторизация
Автоматический параллелизатор и автоматический векторизатор обеспечивают автоматическое повышение производительности циклов в коде.  
  
## <a name="auto-parallelizer"></a>Автоматический параллелизатор  
 [/Qpar](../build/reference/qpar-auto-parallelizer.md) переключатель компилятора позволяет *автоматическую параллелизацию* циклов в коде. Если установить этот флажок без изменения существующего кода, компилятор проанализирует код, чтобы выявить циклы, выполнение которых можно ускорить благодаря параллелизации. Компилятор может обнаружить циклы, которые не представляют большую нагрузку и по которым не получается выигрыш от параллелизации. Для организации параллелизации может потребоваться создание пула потоков, дополнительная синхронизация или другая обработка, которая вместо повышения производительности может привести к ее снижению. Поэтому компилятор строго оценивает возможность выигрыша при выборе циклов для параллелизации. Например, рассмотрим случай, в котором верхняя граница цикла неизвестна во время компиляции.  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Поскольку значение `u` может быть маленьким, компилятор не будет выполнять автоматическую параллелизацию этого цикла. Допустим, вам известно, что значение `u` всегда будет большим и параллелизацию этого цикла желательно выполнить. Чтобы включить автоматическую параллелизацию, укажите [#pragma loop(hint_parallel(n))](../preprocessor/loop.md), где `n` — число потоков для сквозной параллелизации. В приведенном ниже примере компилятор попытается выполнить параллелизацию цикла по 8 потокам.  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Как и во всех [директивы pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), дополнительный синтаксис pragma `__pragma(loop(hint_parallel(n)))` также поддерживается.  
  
 Существуют такие циклы, для которых компилятор не сможет выполнить параллелизацию, даже если вы захотите это сделать. Ниже приведен пример:  
  
```cpp  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 Функция `upper_bound()` может меняться при каждом вызове. Поскольку верхняя граница неизвестна, компилятор может вывести диагностическое сообщение, объясняющее, почему он не может выполнить параллелизацию этого цикла. В приведенном ниже примере демонстрируется цикл, в котором может выполняться параллелизация, цикл, в котором не может выполняться параллелизация, синтаксис компилятора для командной строки и выходные данные компилятора для каждого параметра командной строки:  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 При компиляции с помощью команды:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-report: 1**  
  
 получаются следующие выходные данные:  
  
 **---Анализ функции: void __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): цикл параллелизован**  
  
 При компиляции с помощью команды:  
  
 **CL d:\myproject\mylooptest.cpp/O2 /Qpar /Qpar-report: 2**  
  
 получаются следующие выходные данные:  
  
 **---Анализ функции: void __cdecl test(void)**   
 **d:\myproject\mytest.cpp(4): цикл параллелизован**   
 **d:\myproject\mytest.cpp(4): цикл не параллелизован по причине "1008"**  
  
 Обратите внимание на различие в выходных данных для двух различных [/qpar-Report (уровень отчетности автоматического Параллелизатора)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) параметры. **/ Qpar-report: 1** выводит сообщения параллелизатора только для распараллеленных успешно. **/ Qpar-report: 2** выводит сообщения параллелизатора для обоих невыполненных параллелизаций цикла успешные и неудачные.  
  
 Дополнительные сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
## <a name="auto-vectorizer"></a>Автоматический векторизатор  
 Автоматический векторизатор анализирует циклы в коде и использует векторные регистры и инструкции на целевом компьютере для их выполнения, если это возможно. Это может повысить производительность кода. Компилятор обращается инструкции SSE2, AVX и AVX2 в процессорах Intel и AMD или инструкции NEON в процессорах ARM согласно [/arch](../build/reference/arch-minimum-cpu-architecture.md) переключения.  
  
 Автоматический Векторизатор может создавать инструкции, отличные от указанных **/arch** переключения. Эти инструкции защищены проверкой среды выполнения, гарантирующей, что код все еще работает правильно. Например, при компиляции **/arch:SSE2**, могут быть выданы инструкции SSE4.2. При проверке среды выполнения проверяется, что инструкция SSE4.2 доступна на целевом процессоре, и осуществляется переход к версии цикла, отличной от SSE4.2, если процессор не поддерживает эти инструкции.  
  
 По умолчанию автоматический векторизатор включен. Если вы хотите сравнить производительность векторизированного кода, можно использовать [#pragma loop(no_vector)](../preprocessor/loop.md) для отключения векторизации любого цикла.  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 Как и во всех [директивы pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), дополнительный синтаксис pragma `__pragma(loop(no_vector))` также поддерживается.  
  
 Как и к автоматическому Параллелизатору, можно задавать [/Qvec-report (уровень отчетности автоматического Векторизатора)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) параметр командной строки, чтобы получать отчет успешно векторизован циклы только —**/Qvec-report: 1**— или успешно или неудачно векторизован циклы —**/Qvec-report: 2**).  
  
 Дополнительные сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
 Пример, показывающий, как векторизатор работает на практике, см. [проекта Остине часть 2 из 6: изгиб страницы](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>См. также  
 [цикл](../preprocessor/loop.md)   
 [Параллельное программирование в машинном коде](http://go.microsoft.com/fwlink/p/?linkid=263662)   
 [/ Qpar (автоматический Параллелизатор)](../build/reference/qpar-auto-parallelizer.md)   
 [/ Qpar-report (уровень отчетности автоматического Параллелизатора)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/ Qvec-report (уровень отчетности автоматического Векторизатора)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [Сообщения векторизатора и параллелизатора](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)