---
title: __vmx_vmresume | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmresume
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8809489a71410af21e47d8771ec208340fc893a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="vmxvmresume"></a>__vmx_vmresume
**Блок, относящийся только к системам Microsoft**  
  
 Возобновляет некорневую операцию VMX, используя текущую структуру управления виртуальной машины (VMCS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|Значение|Смысл|  
|-----------|-------------|  
|0|Операция успешно выполнена.|  
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|  
|2|Сбой операции без сведений о состоянии.|  
  
## <a name="remarks"></a>Примечания  
 Приложение может выполнять операцию VM-enter, используя функцию [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) или `__vmx_vmresume` . Функцию `__vmx_vmlaunch` можно использовать только с VMCS, состояние запуска которой — `Clear`, а функцию `__vmx_vmresume` можно использовать только с VMCS, состояние запуска которой — `Launched`. Следовательно, используйте функцию [__vmx_vmclear](../intrinsics/vmx-vmclear.md) для задания состояния запуска VMCS `Clear`, а затем используйте функцию `__vmx_vmlaunch` для первой операции VM-enter и функцию `__vmx_vmresume` для последующих операций VM-enter.  
  
 Функция `__vmx_vmresume` эквивалентна инструкции компьютера `VMRESUME` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения, поиск в PDF-документе «Intel виртуализации технические спецификации для архитектуры IA-32 Intel,» документов номера C97063-002, на [Корпорация Intel](http://go.microsoft.com/fwlink/p/?linkid=127) сайта.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)