---
title: 'CWinApp: Класс приложений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c3641441554d73e0c7657dd220be86f0c0cab0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cwinapp-the-application-class"></a>CWinApp: класс приложений
Класс основного приложения в MFC инкапсулирует инициализации, запуска и завершения приложения для ОС Windows. Приложения, разработанного на платформе должен иметь один и только один объект класса, производный от [CWinApp](../mfc/reference/cwinapp-class.md). Перед созданием windows создается этот объект.  
  
 `CWinApp` является производным от `CWinThread`, который представляет основной поток выполнения для приложения, который может содержать один или несколько потоков. В последних версиях программ MFC `InitInstance`, **запуска**, `ExitInstance`, и `OnIdle` фактически являются функции-члены в классе `CWinThread`. Эти функции описанные здесь, как если бы они были `CWinApp` членов вместо этого, так как обсуждение вопросов объекта роли, как объект приложения, а не как основной поток.  
  
> [!NOTE]
>  Класс приложения представляет основной поток выполнения приложения. С помощью функций Win32 API, можно также создать второстепенных потоков выполнения. Эти потоки могут использовать библиотеку MFC. Дополнительные сведения см. в разделе [многопоточность](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Как и любой программы для операционной системы Windows, приложение framework имеет `WinMain` функции. В приложении framework, однако не пишутся `WinMain`. Он предоставляется библиотекой классов и вызывается при запуске приложения. `WinMain` выполняет стандартных служб, таких как Регистрация классов окон. Затем он вызывает член функции объекта приложения для инициализации и запуска приложения. (Вы можете настроить `WinMain` путем переопределения `CWinApp` функции-члены, `WinMain` вызовов.)  
  
 Для инициализации приложения, `WinMain` вызывает объект приложения `InitApplication` и `InitInstance` функции-члены. Чтобы запустить цикл обработки сообщений приложения, `WinMain` вызовы **запуска** функции-члена. При прерывании операции `WinMain` вызывает объект приложения `ExitInstance` функции-члена.  
  
> [!NOTE]
>  Имена, показанные в **полужирным** в этой документации, обозначающих элементы, предоставляемые Visual C++ и библиотеки классов Microsoft Foundation. Имена, показанные в `monospaced` тип указывает элементы, которые можно создать или переопределить.  
  
## <a name="see-also"></a>См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [CWinApp и мастер приложений MFC](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Переопределяемые CWinApp функции-члены](../mfc/overridable-cwinapp-member-functions.md)   
 [Специальные службы CWinApp](../mfc/special-cwinapp-services.md)

