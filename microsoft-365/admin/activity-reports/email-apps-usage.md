---
title: Отчеты Microsoft 365 в центре администрирования — использование почтовых приложений
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Узнайте, как получить отчет об использовании почтовых приложений, чтобы узнать о почтовых приложениях, подключающихся к Exchange Online, и о том, что пользователи используют версию Outlook.
ms.openlocfilehash: bfd8a911652283685486202203d0302479a8270e
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005760"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Отчеты Microsoft 365 в центре администрирования — использование почтовых приложений

На панели мониторинга **отчетов** Microsoft 365 вы увидите обзор действий по продуктам в вашей организации. Вы можете просмотреть отчеты по отдельным продуктам, чтобы получить более подробные сведения о действиях с каждым приложением. Ознакомьтесь со статьей [Обзор отчетов](activity-reports.md). В отчете об использовании почтовых приложений можно узнать, сколько почтовых приложений подключаются к Exchange Online. Вы также можете просмотреть сведения об используемых версиях приложений Outlook, чтобы найти сотрудников, которые используют неподдерживаемые версий.
  
> [!NOTE]
> Для просмотра отчетов необходимо быть глобальным администратором, глобальным читателям или читателями отчетов в Microsoft 365 или Exchange, SharePoint, Teams Service, Team Communications или Skype для бизнеса.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Получение отчета о почтовых приложениях

1. В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы.

    
2. В раскрывающемся списке **выберите отчет** выберите **Exchange** \> **использование почтовых приложений**Exchange.
  
## <a name="interpret-the-email-apps-report"></a>Интерпретация отчета о почтовых приложениях

Вы можете получить представление об активности почтовых приложений, изучив диаграммы **пользователей** и **клиентов** . 
  
![Используемые почтовые клиенты](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |Отчет **об использовании почтовых приложений** можно просмотреть для тенденций за последние 7, 30, 90 дней или 180 дней. Тем не менее, если выбрать определенный день в отчете, в таблице (7) будут отображаться данные в течение 28 дней с текущей даты (не Дата создания отчета).  <br/> |
|2.  <br/> |Данные в каждом отчете обычно закрываются в течение последних 24 – 48 часов.  <br/> |
|3.  <br/> |В представлении **Пользователи** показано количество уникальных пользователей, которые подключались к Exchange Online с помощью любой почтовой программы.  <br/> |
|4.  <br/> |В представлении **Приложения** отображается количество уникальных пользователей по приложениям за выбранный период.  <br/> |
|5.  <br/> |В представлении **версии** отображается количество уникальных пользователей для каждой версии Outlook в Windows.  <br/> |
|6.  <br/> | На диаграмме **Пользователи** ось Y представляет общее количество уникальных пользователей, которые подключались к приложению в любой день отчетного периода.  <br/>  Ось X на диаграмме **Пользователи** представляет число уникальных пользователей, которые использовали приложение в течение отчетного периода.  <br/>  На диаграмме **Приложения** ось Y представляет общее количество уникальных пользователей, которые использовали определенное приложение в течение отчетного периода.  <br/>  На оси X диаграммы **Приложения** представлен список приложений в организации.  <br/>  На диаграмме **Версии** ось Y представляет общее количество уникальных пользователей определенной версии классического приложения Outlook. Если отчет не может разрешить номер версии Outlook, то количество будет отображаться как **неопределенное**.  <br/>  На оси X диаграммы **Версии** представлен список приложений в организации.  <br/> |
|7.  <br/> |Вы можете отфильтровать ряды, которые вы видите на диаграмме, выбрав элемент в условных обозначениях. Например, на диаграмме **Пользователи** выберите **Mac-почта** или список **Outlook** ![ для клиентов электронной почты. Выберите клиент электронной почты, чтобы получить дополнительные данные отчетов для этого клиента.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) для просмотра только сведений, относящихся к этой категории. При выборе другого значения данные в таблице-сетке не меняются. Примерами почтовых приложений являются Почта Mac, Outlook для Mac, Outlook Mobile, классическая версия Outlook и Outlook в Интернете.  <br/> |
|8.  <br/> | В столбцах могут быть не все указанные ниже элементы, если не добавить их.<br/> **Username** имя владельца почтового приложения.  <br/> **Дата последнего действия** — это самая поздняя дата, когда пользователь прочитает или отправил сообщение электронной почты.  <br/> Примерами почтовых приложений являются **Почта Mac**, **Outlook для Mac**, **Outlook**, **Outlook Mobile** и **Outlook в Интернете**.  <br/>  Если политики организации не позволяют просматривать отчеты, в которых есть личные сведения пользователей, можно изменить параметр конфиденциальности для всех отчетов. Ознакомьтесь с разделом " **как скрыть сведения о уровне пользователя?** " в [отчетах об активности в центре администрирования Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Выберите **Управление столбцами** , чтобы добавить столбцы в отчет или удалить их из него.  <br/> ![Отчет об использовании почтовых приложений — выбор столбцов](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|десяти.  <br/> |Вы также можете экспортировать данные отчета в CSV-файл Excel, выбрав ссылку **Экспорт** . При этом данные всех пользователей будут экспортированы в формат, позволяющий сортировать и фильтровать их для дальнейшего анализа. Если у вас менее 2000 пользователей, вы можете сортировать и фильтровать значения в самой таблице отчета. Если пользователей больше 2000, для фильтрации и сортировки потребуется экспортировать данные.  <br/> |
|||
   
