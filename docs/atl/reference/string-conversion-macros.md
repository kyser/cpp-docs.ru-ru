---
title: Макросы преобразования строк | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 917afc7dae7a0ed96d5d5cc476b4f8394abe8913
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="string-conversion-macros"></a>Макросы преобразования строк

Эти макросы обеспечивают строка функции преобразования.  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL и MFC макросы преобразования строк

Рассматриваемые здесь макросы преобразования строк можно использовать как для ATL, так и для MFC. Дополнительные сведения о преобразовании строки MFC см. в разделе [TN059: использование макросов преобразования MFC MBCS в Юникод](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) и [макросов MFC и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE и макросы преобразования строк TEXTMETRIC

Эти макросы создать копию [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) или [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) структуры и преобразования строк в новой структуре новый строковый тип. Макросы выделение памяти в стеке для новой структуры и вернуть указатель на структуру нового.  
  
```cpp
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Примечания

Пример:  
  
[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
and:  
  
[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
В именах макросов тип string в структуре источника находится слева (например, **A**) и строкового типа в целевой структуре — справа (например, **W**). **Объект** расшифровывается `LPSTR`, **OLE** расшифровывается `LPOLESTR`, **T** расшифровывается `LPTSTR`, и **W** расшифровывается `LPWSTR`.  
  
Таким образом **DEVMODEA2W** копии `DEVMODE` структура с `LPSTR` строки в `DEVMODE` структура с `LPWSTR` строк, **TEXTMETRICOLE2T** копирует `TEXTMETRIC`структура с `LPOLESTR` строки в `TEXTMETRIC` структура с `LPTSTR` строк и т. д.  
  
Две строки преобразуются в `DEVMODE` структуры — это имя устройства (`dmDeviceName`) и имя формы (`dmFormName`). `DEVMODE` Макросы преобразования строк также обновить размер структуры (`dmSize`).  
  
Четыре строки, преобразуются в `TEXTMETRIC` структуры являются первым символом (`tmFirstChar`), последним символом (`tmLastChar`), символ по умолчанию (`tmDefaultChar`) и символа разрыва (`tmBreakChar`).
  
Поведение `DEVMODE` и `TEXTMETRIC` макросы преобразования строк зависит от директивы компилятора в силу, если таковые имеются. Если исходный и конечный типы совпадают, преобразование не выполняется. Директивы компилятора изменяют **T** и **OLE** следующим образом:  
  
|Действующая директива компилятора|T становится|OLE становится|  
|----------------------------------|---------------|-----------------|  
|Нет|**A**|**W**|  
|**\_ЮНИКОД**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**\_Юникод** и **OLE2ANSI**|**W**|**A**|  
  
 В следующей таблице перечислены `DEVMODE` и `TEXTMETRIC` макросы преобразования строк.  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
