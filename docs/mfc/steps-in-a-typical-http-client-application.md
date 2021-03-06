---
title: Шаги в типичного клиентского приложения HTTP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c25402662296a9ebf2f15fe902dcefabb9d47073
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="steps-in-a-typical-http-client-application"></a>Шаги для организации типичного клиентского приложения HTTP
Ниже показаны шаги, которые необходимо выполнять в обычном клиентском приложении HTTP.  
  
|Ваша цель|Выполняемые действия|Произведенный эффект|  
|---------------|----------------------|-------------|  
|Начните сеанс HTTP.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|  
|Подключение к HTTP-серверу.|Используйте [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Возвращает [CHttpConnection](../mfc/reference/chttpconnection-class.md) объекта.|  
|Откройте запрос HTTP.|Используйте [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Возвращает [CHttpFile](../mfc/reference/chttpfile-class.md) объекта.|  
|Отправка HTTP-запроса.|Используйте [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) и [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Поиск файла. Возвращает значение FALSE, если файл не найден.|  
|Чтение из файла.|Используйте [CHttpFile](../mfc/reference/chttpfile-class.md).|Считывает указанное число байтов, с помощью буфера указанные вами.|  
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса HTTP.|Удалить [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Предварительные требования для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
