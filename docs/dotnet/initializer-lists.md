---
title: Списки инициализатора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6634b749480e5108548de0c8b53f8b09cc5a42c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="initializer-lists"></a>Списки инициализатора
Списки инициализатора в конструкторах теперь вызываются перед конструктор базового класса.  
  
## <a name="remarks"></a>Примечания  
 До Visual C++ 2005 конструктор базового класса вызывался перед списком инициализатора при компиляции с помощью управляемых расширений для C++. Теперь при компиляции с параметром **/CLR**, сначала вызывается список инициализатора.  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)