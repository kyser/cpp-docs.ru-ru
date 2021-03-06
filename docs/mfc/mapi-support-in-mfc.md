---
title: Поддержка MAPI в MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5d6498d1ecb20b47070cb26bf1a9d732340e266
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mapi-support-in-mfc"></a>Поддержка MAPI в MFC
MFC предоставляет поддержку подмножество из Microsoft программы интерфейс MAPI (Messaging Application) в классе **CDocument**. В частности **CDocument** содержит функции-члены, определить, присутствует ли почтовых служб на компьютере конечного пользователя и если да, включить команду Отправить сообщение с идентификатором стандартную команду **ID_FILE_SEND_MAIL**. Функция обработчика MFC для этой команды позволяет пользователю отправлять документ по электронной почте.  
  
> [!TIP]
>  Несмотря на то, что MFC не содержит весь набор функций MAPI, можно по-прежнему вызывать функции MAPI напрямую, так же как API-интерфейса Win32 функции можно вызывать непосредственно из программ MFC.  
  
 Предоставление Отправка почты команду в приложении является очень простым. MFC предоставляет реализацию для упаковки документа (то есть **CDocument**-производный объект) как вложение и отправлять их по почте. Это вложение эквивалентно команду сохранения файла, которая сохраняет (сериализует) содержимое документа к почтовому сообщению. Эта реализация вызывает почтовый клиент на компьютере пользователя, чтобы дать пользователю возможность в поле адреса и добавление тема и текст сообщения для сообщения электронной почты. Пользователи увидят их почты знакомый интерфейс пользователя. Эта функциональность предоставляется на два **CDocument** функций-членов: `OnFileSendMail` и `OnUpdateFileSendMail`.  
  
 MAPI необходимо прочитать файл, чтобы отправить вложение. Если приложение поддерживает его файла данных открытым во время `OnFileSendMail` вызов функции, файл необходимо открыть с помощью режима общего доступа, которая позволяет нескольким процессам для доступа к файлу.  
  
> [!NOTE]
>  Переопределение `OnFileSendMail` для класса `COleDocument` правильно обрабатывает составных документов.  
  
#### <a name="to-implement-a-send-mail-command-with-mfc"></a>Реализация команды Отправка почты с MFC  
  
1.  Используйте Visual C++ редактор меню Добавление пункта меню с идентификатором команды **ID_FILE_SEND_MAIL**.  
  
     Этот идентификатор команды обеспечивается платформы на AFXRES. З. Можно добавить команды меню, но обычно он добавляется в **файл** меню.  
  
2.  Вручную добавьте следующий код в схему сообщений в документе:  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  На этой карте сообщений работает для документа, полученные из либо **CDocument** или **COleDocument** — он собирает правильного базового класса в любом случае, несмотря на то, что в схеме сообщений — в документ в производном классе.  
  
3.  Постройте приложение.  
  
 При наличии почтовых служб MFC позволяет элемента меню с `OnUpdateFileSendMail` и впоследствии обрабатывает команды с `OnFileSendMail`. Если поддержка почты недоступна, MFC автоматически удаляет элемента меню, чтобы пользователь не увидит ее.  
  
> [!TIP]
>  Вместо того чтобы вручную добавлять записи схемы сообщений как описано выше, можно использовать окно свойств класса для сопоставления сообщения с функциями. Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).  
  
 Дополнительные сведения см. в разделе [MAPI](../mfc/mapi.md) Обзор.  
  
 Дополнительные сведения о **CDocument** функции-члены, позволяющие MAPI, см.:  
  
-   [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)  
  
-   [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)  
  
-   [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)  
  
## <a name="see-also"></a>См. также  
 [MAPI](../mfc/mapi.md)

