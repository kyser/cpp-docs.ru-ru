---
title: 'Как: включить 64-разрядных инструментов Visual C++ в командной строке | Документы Microsoft'
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22290cdf9418299cbba51ab1d893d60cb790e2e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>Как: включить 64-разрядной, x64 размещенных набора инструментов Visual C++ в командной строке

Visual C++ содержит компиляторы, компоновщики и другие средства, которые можно использовать для создания версий конкретную платформу приложения, которые могут выполняться в 32-разрядной, 64-разрядной или ARM под управлением ОС Windows. Другие необязательные рабочие нагрузки Visual Studio позволяют использовать инструменты C++ для других платформ, таких как iOS, Android и Linux. Архитектура сборки по умолчанию использует 32-разрядные, размещенные x86 средства для построения 32-разрядные, x86 машинный код Windows. Тем не менее возможно, 64-разрядном компьютере. Можно воспользоваться преимуществами процессора и памяти, доступное для 64-разрядного кода с помощью набора инструментов 64-разрядные, размещенные x64 при создании кода для x86, x64 или процессоров ARM.

> [!NOTE]
> Сведения о конкретных средствах, которые входят в состав каждого выпуска Visual C++ см. в разделе [Visual C++ средствах и функциях в выпусках Visual Studio](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Сведения о том, как использовать интегрированную среду разработки Visual Studio для создания 64-разрядных приложений см. в разделе [как: Настройка проектов Visual C++ для 64-разрядных x64 платформы](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

При установке C++ рабочей нагрузки в установщик Visual Studio всегда устанавливается 32-разрядной, размещенных в x86, машинная компиляция и кросс компилятора средства для построения кода x86- и x64. При включении рабочей нагрузки универсальной платформы Windows также устанавливается размещенных x86 кросс-компилятор средства для построения кода ARM. При установке этих рабочих нагрузок на x64 64-разрядных процессоров, вы также получаете собственный 64-разрядный и кросс-компилятор инструменты для создания x86 x 64 и ARM кода. 32-разрядных и 64-разрядные средства создают идентичный код, однако 64-разрядные средства поддерживают больше памяти для предварительно скомпилированных символов заголовков и оптимизации всей программы ([/GL](../build/reference/gl-whole-program-optimization.md) и [/LTCG](../build/reference/ltcg-link-time-code-generation.md)) параметры. При возникновении ограничения памяти при использовании 32-разрядные средства, попробуйте 64-разрядные средства.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Использование командной строки разработчика размещенного 64-разрядных сочетания клавиш

При установке Visual Studio в 64-разрядной операционной системе Windows, доступны дополнительные разработчика ярлыки командной строки для 64-разрядные, размещенные x64 собственные и кросс-компиляторы. Для использования этих командных строк в Windows 10 на **запустить** меню, откройте папку для вашей версии Visual Studio, например **2017 г. Visual Studio**и затем выберите один из x64 собственного или кросс инструмента Командная строка разработчика. Для использования этих командных строк в Windows 8 на **запустить** открывшегося экрана **все приложения**. Под заголовком для установленной версии Visual Studio, откройте **Visual Studio** папки (в предыдущих версиях Visual Studio, она может называться **набора средств Visual Studio**). В более ранних версиях Windows, выберите **запустить**, разверните **все программы**, в папке для вашей версии **Visual Studio** (и в предыдущих версиях Visual Studio  **Набор средств Visual Studio**). Дополнительные сведения см. в разделе [Ярлыки командной строки разработчика](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Использовать файл Vcvarsall.bat для задания для построения размещенного 64-разрядной архитектуры

Файл любого собственного или кросс-компилятора средства конфигурации построения можно использовать в командной строке, запустив файл vcvarsall.bat команды. Этот командный файл настраивает путь и переменные среды, позволяющие конкретной архитектура в окне командной строки с существующей сборки. Дополнительные инструкции в разделе [разработчика командных файлов и расположений](../build/building-on-the-command-line.md#developer-command-files-and-locations).

## <a name="see-also"></a>См. также

[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
