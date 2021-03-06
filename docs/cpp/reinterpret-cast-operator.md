---
title: Оператор reinterpret_cast | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- reinterpret_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd64960469c9c4ca069611f6ebeefeaac8b29ba0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="reinterpretcast-operator"></a>Оператор reinterpret_cast
Позволяет преобразовывать любой указатель в указатель любого другого типа. Также позволяет преобразовывать любой целочисленный тип в любой тип указателя и наоборот.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Примечания  
 Неправильное использование оператора `reinterpret_cast` легко может оказаться небезопасным. Если требуемое преобразование не является низкоуровневым по самой своей природе, следует использовать один из других операторов приведения типов.  
  
 Оператор `reinterpret_cast` можно использовать для таких преобразований, как `char*` в `int*` или `One_class*` в `Unrelated_class*`, которые небезопасны по самой своей сути.  
  
 Результат применения `reinterpret_cast` не может безопасно использоваться ни для чего другого, кроме приведения обратно в исходный тип. Другие применения в лучшем случае будут непереносимыми.  
  
 `reinterpret_cast` Оператор не может удалять **const**, `volatile`, или **__unaligned** атрибуты. В разделе [оператор const_cast](../cpp/const-cast-operator.md) сведения об удалении этих атрибутов.  
  
 Оператор `reinterpret_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
 Одним из практических применений оператора `reinterpret_cast` является хэш-функция, которая сопоставляет значение индексу таким образом, что два несовпадающих значения редко соответствуют одинаковым индексам.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 Оператор `reinterpret_cast` позволяет использовать указатель как целочисленный тип. Затем для получения уникального индекса (уникального с высокой степенью вероятности) к результату применяется побитовый сдвиг и операция XOR с самим собой. Далее индекс усекается с использованием стандартного для языка C приведения к типу возвращаемого значения функции.  
  
## <a name="see-also"></a>См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)