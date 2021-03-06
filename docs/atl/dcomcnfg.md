---
title: DCOMCNFG | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DCOMCNFG
dev_langs:
- C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a165102294f9f39d25f0c3118251382ecab067b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="dcomcnfg"></a>DCOMCNFG.
**DCOMCNFG** — это программа Windows NT 4.0, которая позволяет настраивать различные параметры DCOM в реестре. **DCOMCNFG** окно содержит три страницы: безопасность по умолчанию, свойства по умолчанию и приложений. В среде Windows 2000 четвертой странице протоколов по умолчанию, отсутствует.  
  
## <a name="default-security-page"></a>Страница «Безопасность по умолчанию»  
 Страница настройки безопасности по умолчанию для задания разрешений по умолчанию для объектов в системе. Безопасность по умолчанию страница имеет три раздела: доступ, запуск и конфигурации. Чтобы изменить значения по умолчанию раздел, соответствующий пункт **изменить значения по умолчанию** кнопки. Эти параметры безопасности по умолчанию хранятся в разделе реестра `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.  
  
## <a name="default-protocols-page"></a>Страница протоколов по умолчанию  
 На этой странице перечислены набор сетевых протоколов, доступных для DCOM на этом компьютере. Порядок отражает приоритет, в котором они будут использоваться; Первый элемент в списке имеет наивысший приоритет. Протоколы может быть добавлены или удалены с этой страницы.  
  
## <a name="default-properties-page"></a>Страница свойств по умолчанию  
 На странице свойства по умолчанию, необходимо выбрать **разрешить использование DCOM на этом компьютере** флажок, чтобы клиенты на других компьютерах для доступа к COM-объектам, выполняющихся на этом компьютере. Выбор этого параметра задает `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` значение `Y`.  
  
## <a name="applications-page"></a>Страница «приложения»  
 Можно изменить параметры для определенного объекта со страницей приложения. Просто выберите приложение из списка и нажмите кнопку **свойства** кнопки. В окне свойств имеется пять страниц:  
  
-   Страница «Общие» подтверждает приложения, в которой вы работаете.  
  
-   Странице «расположение» позволяет указать, где следует запускать приложение, когда клиент вызывает `CoCreateInstance` на соответствующий код CLSID. При выборе **запустить приложение на следующем компьютере** флажок и введите имя компьютера, а затем `RemoteServerName` добавить значение в группе AppID для данного приложения. Очистка **запуска приложения на этом компьютере** флажок переименовывает `LocalService` значение `_LocalService` и тем самым отключает его.  
  
-   Страница «безопасность» аналогичны параметрам безопасности по умолчанию страница найдена в **DCOMCNFG** окна, за исключением того, что эти параметры применяются только для текущего приложения. Опять же параметры хранятся в AppID для этого объекта.  
  
-   Выявление страницы определяет, какая учетная запись будет использоваться для запуска приложения.  
  
-   На странице конечные точки перечислены протоколы и конечные точки, доступные для использования клиентами выбранного сервера DCOM.  
  
## <a name="see-also"></a>См. также  
 [Службы](../atl/atl-services.md)

