---
title: Lock::operator == | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
dev_langs:
- C++
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 276ad5b44dd2112abad2c7c2e293fc65b173fffc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lockoperator"></a>lock::operator==
Оператор равенства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `t`  
 Объект для сравнения на равенство.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `true` Если `t` является таким же, как объект блокировки, `false` в противном случае.  
  
## <a name="example"></a>Пример  
  
```  
// msl_lock_op_eq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   lock l1(o1);  
   if (l1 == o1) {  
      Console::WriteLine("Equal!");  
   }  
}  
```  
  
```Output  
Equal!  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\lock.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [Блокировка членов](../dotnet/lock-members.md)   
 [lock::operator!=](../dotnet/lock-operator-inequality.md)