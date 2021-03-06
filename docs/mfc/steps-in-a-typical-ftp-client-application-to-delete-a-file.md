---
title: Шаги в типичном клиентском приложении FTP для удаления файла | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb595dfdc1a73ecd068e251cec5df99d4daaab30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Шаги для удаления файла в типичном клиентском приложении FTP
В следующей таблице показаны шаги, которые необходимо выполнять в обычном клиентском приложении FTP, удаляющее файл.  
  
|Ваша цель|Выполняемые действия|Произведенный эффект|  
|---------------|----------------------|-------------|  
|Начните сеанс FTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|  
|Подключиться к FTP-серверу.|Используйте [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Возвращает [классе CFtpConnection](../mfc/reference/cftpconnection-class.md) объекта.|  
|Проверьте, что вы в правом каталог на FTP-сервере.|Используйте [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) или [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Возвращает имя или URL-адрес каталога, который в настоящий момент подключены к на сервере, в зависимости от выбранной функции-члена.|  
|Изменения в новый каталог FTP на сервере.|Используйте [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Изменяет каталог, который в настоящий момент подключены к на сервере.|  
|Найти первый файл в каталоге FTP.|Используйте [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|Находит первый файл. Возвращает значение FALSE, если файлы не найдены.|  
|Найти следующий файл в каталоге FTP.|Используйте [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Находит следующий файл. Возвращает значение FALSE, если файл не найден.|  
|Удаление файла, обнаруженные **FindFile** или `FindNextFile`.|Используйте [CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove), возвращенные с помощью имени файла **FindFile** или `FindNextFile`.|Удаляет файл на сервере для чтения или записи.|  
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса FTP.|Удалить [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Предварительные требования для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
