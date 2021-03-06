---
title: 'Как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20472a80b35318fa4c6d34221a61345de9e40f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне
В этой статье предполагается, что создается на базе диалогового окна ([класса CDialog](../mfc/reference/cdialog-class.md)) проекта Microsoft Foundation Classes (MFC), но можно также добавить поддержку для элемента управления Windows Forms в существующем диалоговом окне MFC.  
  
### <a name="to-create-the-net-user-control"></a>Создание пользовательского элемента управления .NET  
  
1.  Создайте проект Visual C# Windows Forms Библиотека элементов управления с именем `WindowsFormsControlLibrary1`.  
  
     В меню **Файл** последовательно выберите пункты **Создать** и **Проект**. В **Visual C#** выберите **Библиотека элементов управления Windows Forms**.  
  
     Принять `WindowsFormsControlLibrary1` имя проекта, щелкнув **ОК**.  
  
     По умолчанию имя элемента управления .NET будет `UserControl1`.  
  
2.  Добавление дочерних элементов управления к `UserControl1`.  
  
     В **элементов**откройте **все формы Windows Forms** списка. Перетащите **кнопку** управления `UserControl1` область конструктора.  
  
     Кроме того, добавить **TextBox** элемента управления.  
  
3.  В **обозревателе решений**, дважды щелкните **файл UserControl1.Designer.cs** чтобы открыть его для редактирования. Изменение объявления текстовое поле и кнопку из `private` для `public`.  
  
4.  Выполните построение проекта.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Создайте проект приложения MFC.  
  
     В меню **Файл** последовательно выберите пункты **Создать** и **Проект**. В **Visual C++** выберите **приложение MFC**.  
  
     В поле **Имя** введите `MFC01`. Измените настройку решения **добавить решение**. Нажмите кнопку **ОК**.  
  
     В **мастер приложений MFC**, выберите тип приложения **на базе диалогового окна**. Примите остальные значения по умолчанию и нажмите кнопку **Готово**. Это создает приложение MFC с диалоговым окном MFC.  
  
2.  Добавление элемента управления placeholder в диалоговом окне MFC.  
  
     На **представление** меню, нажмите кнопку **представление ресурсов**. В **представление ресурсов**, разверните **диалоговое окно** папку и дважды щелкните `IDD_MFC01_DIALOG`. Ресурс диалогового окна отображается в **редактор ресурсов**.  
  
     В **элементов**откройте **редактор диалоговых окон** списка. Перетащите **статический текст** элемента управления в ресурс диалогового окна. **Статический текст** управления будет использоваться как заполнитель для элемента управления .NET Windows Forms. Изменение размера до приблизительного размера элемента управления Windows Forms.  
  
     В **свойства** измените **идентификатор** из **статический текст** управления `IDC_CTRL1` и измените **TabStop** свойства **True**.  
  
3.  Настройка проекта для поддержки Common Language Runtime (CLR).  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши узел проекта MFC01 и нажмите кнопку **свойства**.  
  
     В **страницы свойств** диалогового **свойства конфигурации**выберите **Общие**. В **проекта по умолчанию** установите **поддержки Common Language Runtime** для **поддержка среды CLR (/ clr)**.  
  
     В разделе **свойства конфигурации**, разверните **C/C++** и выберите **Общие** узла. Задать **формат отладочной информации** для **(/Zi) база данных программы**.  
  
     Выберите **создания кода** узла. Задать **включить минимальное перестроение** для **нет (/ Gm-)**. Кроме того, задать **основные проверки времени выполнения** для **по умолчанию**.  
  
     Нажмите кнопку **ОК** для применения изменений.  
  
4.  Добавьте ссылку на элемент управления .NET.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши узел проекта MFC01 и нажмите кнопку **добавить**, **ссылки**. На **страницу свойств**, нажмите кнопку **добавить новую ссылку**выберите **WindowsFormsControlLibrary1** (в разделе **проекты** вкладку) и нажмите кнопку **ОК**. Добавлена ссылка в виде [/FU](../build/reference/fu-name-forced-hash-using-file.md) -параметр компилятора, чтобы программа будет компилироваться. Также копию WindowsFormsControlLibrary1.dll помещаются в папку проекта \MFC01\, программа будет запущена.  
  
5.  В файле Stdafx.h найдите следующую строку:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Над ним добавьте следующие строки:  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Добавьте код для создания управляемого элемента управления.  
  
     Сначала объявите управляемого элемента управления. В файле MFC01Dlg.h перейти к объявлению класса диалогового окна, и добавить элемент данных для пользовательского элемента управления в области Protected следующим образом.  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     Затем укажите реализацию управляемого элемента управления. В MFC01Dlg.cpp в диалоговом окне переопределение `CMFC01Dlg::DoDataExchange` , созданном с помощью мастера приложений MFC (не `CAboutDlg::DoDataExchange`, который находится в том же файле), добавьте следующий код для создания управляемого элемента управления и свяжите его с прототипом статического элемента управления IDC_CTRL1.  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  Постройте и запустите проект.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши **MFC01** и нажмите кнопку **Назначить запускаемым проектом**.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, нажмите кнопку **Запуск без отладки**. В диалоговом окне MFC отображать элемент управления Windows Forms.  
  
## <a name="see-also"></a>См. также  
 [Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)