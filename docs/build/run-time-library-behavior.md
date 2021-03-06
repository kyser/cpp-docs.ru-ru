---
title: Библиотеки DLL и поведение библиотеки времени выполнения Visual C++ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: feee3d888fbf43bfd8675ccc83a04fd4e1f0b528
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Библиотеки DLL и поведение библиотеки времени выполнения Visual C++  
  
При построении библиотека динамической компоновки (DLL) с помощью Visual C++ по умолчанию компоновщик включает библиотеку времени выполнения Visual C++ (VCRuntime). VCRuntime содержит код, необходимый для инициализация и прекращение исполняемый объект C/C++. При связывании в библиотеку DLL, код VCRuntime предоставляет Внутренняя функция точки входа DLL вызывается `_DllMainCRTStartup` , обрабатывает сообщения Windows ОС на библиотеку DLL, чтобы присоединять или отсоединять их от процесса или потока. `_DllMainCRTStartup` Функция выполняет основные задачи, такие как безопасность буфера стека, установки, инициализации библиотеки времени выполнения (CRT) C и завершения и вызывает конструкторы и деструкторы для статические и глобальные объекты. `_DllMainCRTStartup` также вызывает обработчик функций в других библиотеках, например WinRT, MFC и ATL для выполнения своих собственных инициализация и прекращение работы. Без инициализации, CRT и другими библиотеками, а также статических переменных останется в неинициализированном состоянии. Же VCRuntime внутренней инициализации и завершения процедуры вызываются ли использует библиотеки DLL, статически скомпонованной CRT, так и динамически скомпонованная Библиотека CRT.  
  
## <a name="default-dll-entry-point-dllmaincrtstartup"></a>По умолчанию _DllMainCRTStartup точки входа библиотеки DLL  
  
В Windows, все библиотеки DLL могут содержать необязательный точки входа функции, обычно называемой `DllMain`, который вызывается для инициализации и завершения. Это дает возможность выделить или освободить дополнительные ресурсы по мере необходимости. Windows вызывает функцию точки входа в четырех случаях: присоединение процесса, отсоединение процесса, потока присоединения и отсоединения потока. При загрузке библиотеки DLL в адресное пространство процесса при загрузке приложения, использующего его или когда приложение запрашивает DLL во время выполнения, операционная система создает отдельную копию данных библиотеки DLL. Это называется *присоединение процесса*. *Присоединение потока* возникает, когда библиотека DLL загружается в процесс создает новый поток. *Поток отсоединения* возникает, когда поток завершается, и *отсоединение процесса* когда больше не требуется и освобождается приложением библиотеки DLL. Операционная система вызывает отдельные точки входа библиотеки DLL для каждого из этих событий, передав *Причина* аргумент для каждого типа события. Например, операционная система отправляет `DLL_PROCESS_ATTACH` как *Причина* аргумент для обозначения процесса присоединения.  
  
Библиотека VCRuntime содержит функцию точки входа с именем `_DllMainCRTStartup` для обработки операций инициализация и прекращение работы по умолчанию. В процессе присоединения, `_DllMainCRTStartup` функция задает проверки безопасности буфера, инициализирует CRT и другими библиотеками, инициализирует сведения о типах времени выполнения, инициализирует и вызывает конструкторы для статических и нелокальные данные, инициализирует локальную память потока , увеличивает статический внутренний счетчик для каждого подключения, а затем вызывает или библиотека пользовательские `DllMain`. В процессе отсоединения, функция проходит через следующие действия в обратном порядке. Он вызывает `DllMain`, уменьшает внутренний счетчик вызывает деструкторы, завершение CRT вызовы функции и зарегистрирован `atexit` функции и уведомляет другие библиотеки прекращения. Если вложение счетчик становится равным нулю, функция возвращает значение `FALSE` для указания Windows, библиотеки DLL, что может быть выгружен. `_DllMainCRTStartup` Во время поток также вызывается функция присоединения и отсоединения потока. В таких случаях не выполняет дополнительную инициализацию или завершение самостоятельно VCRuntime код и просто вызывает `DllMain` для передачи сообщения вместе. Если `DllMain` возвращает `FALSE` из процесса присоединения, сигнализация сбоя `_DllMainCRTStartup` вызовы `DllMain` еще раз и передает `DLL_PROCESS_DETACH` как *Причина* аргумент, затем проходит через остальная часть Завершение процесса.  
  
При создании библиотеки DLL в Visual C++, точкой входа по умолчанию `_DllMainCRTStartup` предоставляемые VCRuntime компонуется автоматически. Необходимо указать функцию точки входа для библиотеки DLL с помощью [/Entry (символ точки входа)](../build/reference/entry-entry-point-symbol.md) компоновщика.  
  
> [!NOTE]
> Хотя можно указать другую функцию точки входа библиотеки DLL с помощью / ENTRY: параметр компоновщика не рекомендуется, поскольку функция точки входа потребуется скопировать все содержимое, `_DllMainCRTStartup` так, в том же порядке. VCRuntime предоставляет функции, позволяющие дублировать его поведение. Например, можно вызвать [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) непосредственно в процессе присоединения для поддержки [/GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md) Выбор параметра буфера. Можно вызвать `_CRT_INIT` функции, передав в качестве функцию точки входа для выполнения остальная часть функции инициализации или завершения DLL теми же параметрами.  
  
<a name="initializing-a-dll"></a>  
  
## <a name="initialize-a-dll"></a>Инициализация библиотеки DLL  
  
Библиотеки DLL, возможно, код инициализации, который должен выполняться при загрузке библиотеки DLL. Для того, для выполнения собственных DLL инициализация и прекращение работы функций `_DllMainCRTStartup` вызывает функцию с именем `DllMain` могут быть реализованы. Ваш `DllMain` должен иметь сигнатуру, необходимые для точки входа библиотеки DLL. Функция точки входа по умолчанию `_DllMainCRTStartup` вызовы `DllMain` теми же параметрами передал Windows. По умолчанию, если не предоставить `DllMain` функции, Visual C++ предоставляет его и связывает его в, чтобы `_DllMainCRTStartup` всегда содержит какие-то для вызова. Это означает, что если не требуется для инициализации библиотеки DLL, никаких дополнительных действий при построении библиотеки DLL.  
  
Это подпись, используемая для `DllMain`:  
  
```cpp  
#include <windows.h>  
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```  
  
Некоторые библиотеки помещают `DllMain` функции для вас. Например, в обычных библиотек DLL MFC, следует реализовать `CWinApp` объекта `InitInstance` и `ExitInstance` функции-члены для выполнения инициализации и завершения, необходимых для библиотеки DLL. Дополнительные сведения см. в разделе [обычный режим инициализации библиотеки DLL MFC](#initializing-regular-dlls) раздела.  
  
> [!WARNING]
> Существуют значительные ограничения на безопасно возможности в библиотеке DLL точки входа. В разделе [Общие рекомендации](https://msdn.microsoft.com/library/windows/desktop/dn633971#general_best_practices) для определенных API-интерфейсы Windows, небезопасных для вызова в `DllMain`. Если вам требуется только простой инициализации затем использовать функцию инициализации для библиотеки DLL. Можно потребовать, чтобы приложения, вызывающие функции инициализации после `DllMain` имеет выполнения и перед их вызывать любые другие функции в DLL.  
  
<a name="initializing-non-mfc-dlls"></a>  
  
### <a name="initialize-ordinary-non-mfc-dlls"></a>Инициализация библиотек DLL, обычный (не MFC)  
  
Для инициализации собственных библиотек DLL обычный (не MFC), используйте предоставленный VCRuntime `_DllMainCRTStartup` точки входа DLL исходный код должен содержать функцию с именем `DllMain`. В следующем отрывке кода структуру определения функции `DllMain` может выглядеть так:  
  
```cpp  
#include <windows.h>
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason) 
    { 
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```  
  
> [!NOTE]
> Документацию к предыдущим версиям Windows SDK сказано, что фактическое имя этой функции точки входа DLL должно быть указано в строке компоновщика командной строки с параметром/Entry. С помощью Visual C++, вы не обязательно должны использовать параметр/Entry, если функция точки входа называется `DllMain`. На самом деле, если используется параметр/Entry и имя точки входа функции, что-либо отличные от `DllMain`, CRT не удастся инициализировать пока точка входа функции сделает же вызовы инициализации `_DllMainCRTStartup` делает.  
  
<a name="initializing-regular-dlls"></a>  
  
### <a name="initialize-regular-mfc-dlls"></a>Инициализация обычных библиотек DLL MFC  
  
Так как обычные библиотеки DLL MFC имеют `CWinApp` объекта, они должны выполнять инициализацию и завершение в том же расположении, как приложение MFC: в `InitInstance` и `ExitInstance` функций-членов из библиотеки DLL `CWinApp`-производный класс. Поскольку MFC предоставляет `DllMain` функция, вызываемая `_DllMainCRTStartup` для `DLL_PROCESS_ATTACH` и `DLL_PROCESS_DETACH`, следует писать собственные `DllMain` функции. Предоставляемая MFC `DllMain` вызовов функций `InitInstance` при загрузке библиотеки DLL и вызывает `ExitInstance` перед выгрузкой библиотеки DLL.  
  
Обычной MFC DLL можно хранить список нескольких потоков, вызвав [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) и [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) в его `InitInstance` функции. Эти функции позволяют библиотеке DLL для отслеживания данных для определенного потока.  
  
В обычной MFC DLL, динамически связанной с MFC, при использовании любого MFC OLE, баз данных MFC (или DAO) или сокеты MFC поддерживают, соответственно, отладки расширения MFC DLL MFCO*версии*D.dll, MFCD*версии*D.dll и MFCN*версии*D.dll (где *версии* номер версии) связываются автоматически. Необходимо вызвать один из следующих предопределенных функций настройки для каждой из этих библиотек DLL, которые используются в библиотеке регулярных DLL MFC `CWinApp::InitInstance`.  
  
|Тип поддержки MFC|Вызываемая функция|  
|-------------------------|-------------------------------------|  
|MFC OLE (MFCO*версии*D.dll)|`AfxOleInitModule`|  
|Базы данных MFC (MFCD*версии*D.dll)|`AfxDbInitModule`|  
|Сокеты MFC (MFCN*версии*D.dll)|`AfxNetInitModule`|  
  
<a name="initializing-extension-dlls"></a>  
  
### <a name="initialize-mfc-extension-dlls"></a>Инициализация библиотек расширения MFC  
  
Поскольку библиотеки DLL расширения MFC не имеют `CWinApp`-производный объект (от обычных библиотек DLL MFC), следует добавить код инициализации и завершения, чтобы `DllMain` функции, сформированному мастером MFC DLL.  
  
 Мастер предоставляет следующий код для расширения MFC библиотеки DLL. В коде `PROJNAME` — это имя проекта.  
  
```cpp  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // MFC extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
Создание нового `CDynLinkLibrary` объект во время инициализации позволяет расширения MFC DLL для экспорта `CRuntimeClass` объектов или ресурсов для клиентского приложения.  
  
Если планируется использование расширения MFC DLL из одного или нескольких обычных библиотек DLL MFC, необходимо экспортировать функцию инициализации, которая создает `CDynLinkLibrary` объекта. Эта функция должна вызываться из каждого обычные библиотеки DLL MFC, с помощью расширения MFC DLL. Необходимо вызвать эту функцию инициализации находится в `InitInstance` функцию-член регулярных DLL MFC `CWinApp`-производный объект перед использованием некоторых экспортируемые классы или функции DLL расширения MFC.  
  
В `DllMain` , мастер библиотек DLL MFC приводит к возникновению ошибки, вызов `AfxInitExtensionModule` захватывает классов времени выполнения модуля (`CRuntimeClass` структуры) а также производства объектов (`COleObjectFactory` объектов) для использования при `CDynLinkLibrary` создан объект. Следует проверить значение, возвращаемое `AfxInitExtensionModule`; если возвращенный нулевое значение `AfxInitExtensionModule`, возвращают ноль из вашего `DllMain` функции.  
  
Если библиотеки DLL расширения MFC явно связана в исполняемый файл (то есть в исполняемом файле вызывается `AfxLoadLibrary` для связывания с библиотекой DLL), следует добавить вызов `AfxTermExtensionModule` на `DLL_PROCESS_DETACH`. Эта функция используется в MFC для очистки библиотеки DLL расширения MFC, после отсоединения всех процессов из библиотеки DLL расширения MFC (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате использования `AfxFreeLibrary` вызова). Если в приложение вызов неявного связывания библиотеки DLL расширения MFC `AfxTermExtensionModule` не требуется.  
  
Приложения, которые явно ссылку, чтобы библиотеки DLL расширения MFC необходимо вызвать метод `AfxTermExtensionModule` при освобождении библиотеки DLL. Она также использует `AfxLoadLibrary` и `AfxFreeLibrary` (вместо функций Win32 `LoadLibrary` и `FreeLibrary`), если приложение использует несколько потоков. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения MFC не приведет к повреждению глобального состояния MFC.  
  
Поскольку MFCx0.dll к моменту полностью `DllMain` — вызывается, можно выделить память и вызвать функции MFC в `DllMain` (в отличие от 16-разрядной версии MFC).  
  
Библиотеки DLL расширения может обрабатывать многопоточность, обрабатывая `DLL_THREAD_ATTACH` и `DLL_THREAD_DETACH` вариантов в `DllMain` функции. Эти значения передаются в `DllMain` при потоков присоединения и отсоединения от библиотеки DLL. Вызов [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) при присоединении DLL позволит использовать Библиотеку для поддержания поток индексирует локальное хранилище (TLS) для каждого потока, присоединенного к библиотеке DLL.  
  
Обратите внимание, что в файле заголовка Afxdllx.h содержит специальные определения для структур, используемых в библиотеки DLL расширения MFC, такие как определение `AFX_EXTENSION_MODULE` и `CDynLinkLibrary`. Следует включить файл заголовка в библиотеки DLL расширения MFC.  
  
> [!NOTE]
>  Очень важно, ни определения, ни отменять `_AFX_NO_XXX` макросов добавьте в файл Stdafx.h. Эти макросы существует только для проверки, поддерживает ли определенный целевой платформы этой функции. Можно написать программу так, чтобы проверить эти макросы (например, `#ifndef _AFX_NO_OLE_SUPPORT`), но программа никогда не следует определения или отмены определения этих макросов.  
  
Пример функции инициализации, обработка многопоточности, включенный в [с помощью локальной памяти в библиотеке динамической компоновки](http://msdn.microsoft.com/library/windows/desktop/ms686997) в Windows SDK. Обратите внимание, что пример содержит функцию точки входа с именем `LibMain`, но вам следует присвоить имя `DllMain` , что позволит использовать ее в библиотеках времени выполнения MFC и C.  
  
## <a name="see-also"></a>См. также  
  
[DLL в Visual C++](../build/dlls-in-visual-cpp.md)  
[Точка входа функции DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583.aspx)  
[Рекомендации по использованию библиотеки динамической компоновки](https://msdn.microsoft.com/library/windows/desktop/dn633971.aspx)  