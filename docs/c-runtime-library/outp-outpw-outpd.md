---
title: _outp, _outpw, _outpd | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs:
- C++
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 140b53fd90d393f2629dda6573d994635b96f417
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd
Выводит на порт байт (`_outp`), слово (`_outpw`) или двойное слово (`_outpd`).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _outp(  
unsigned short port,  
int databyte   
);  
unsigned short _outpw(  
unsigned short port,  
unsigned short dataword   
);  
unsigned long _outpd(  
unsigned short port,  
unsigned long dataword   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *порт*  
 Номер порта.  
  
 *databyte, dataword*  
 Выходные значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции возвращают выходные данные. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функции `_outp`, `_outpw`и `_outpd` пишут байт, слово и двойное слово, соответственно, на указанный порт вывода. Аргумент *port* может быть любым целым числом без знака в диапазоне от 0 до 65535; *databyte* может быть любым целым числом в диапазоне от 0 до 255; *dataword* может быть любым значением в диапазоне целого числа, короткого целого без знака и длинного целого без знака, соответственно.  
  
 Поскольку эти функции пишут непосредственно на порт ввода-вывода, они не могут использоваться в пользовательском коде. Для получения дополнительных сведений об использовании портов ввода-вывода в этих операционных системах, выполните поиск по запросу "Последовательная связь в Win32" в MSDN.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_outp`|\<conio.h>|  
|`_outpw`|\<conio.h>|  
|`_outpd`|\<conio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод-вывод на консоль и порт](../c-runtime-library/console-and-port-i-o.md)   
 [_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)