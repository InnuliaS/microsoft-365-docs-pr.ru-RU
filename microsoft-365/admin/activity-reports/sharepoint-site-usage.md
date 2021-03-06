---
title: Отчеты Microsoft 365 в центре администрирования — использование сайта SharePoint
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Получите отчет об использовании сайта SharePoint, чтобы узнать, сколько файлов пользователи хранят на сайтах SharePoint, сколько используется активно и сколько потребляется общее хранилище. '
ms.openlocfilehash: b39f1588f5c0c68a5972aab3039a8d7d901f9dc5
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689304"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Отчеты Microsoft 365 в центре администрирования — использование сайта SharePoint

Как администратор Microsoft 365, панель мониторинга **отчетов** показывает обзор действий для различных продуктов в Организации. Вы можете детализировать их, чтобы получить более подробную информацию о действиях для каждого продукта. Например, вы можете получить общее представление о том, насколько активно SharePoint используется с точки зрения количества хранимых или активно используемых файлов и объема хранилища, занятого на всех сайтах SharePoint. Затем вы можете детализировать отчет об использовании сайта SharePoint, чтобы выявить тенденции и получить сведения об использовании на уровне сайта. 
  
> [!NOTE]
> Для просмотра отчетов необходимо быть глобальным администратором, глобальным читателям или читателями отчетов в Microsoft 365 или Exchange, SharePoint, Teams Service, Team Communications или Skype для бизнеса.
Отчеты Microsoft 365 в центре администрирования не поддерживаются для клиентов с высоким уровнем связи GCC и DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Открытие отчета об использовании сайта SharePoint

1. В центре администрирования выберите **отчеты** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a>.

    
2. В раскрывающемся списке **выберите отчет** выберите **SharePoint** \> **Использование сайта**SharePoint.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Анализ отчета об использовании сайтов SharePoint

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |В отчете **Использование сайтов SharePoint** можно отследить тенденции за последние 7, 30, 90 и 180 дней. Тем не менее, если выбрать определенный день в отчете, в таблице (7) будут отображаться данные в течение 28 дней с текущей даты (не Дата создания отчета).  <br/> |
|2.  <br/> |Данные в каждом отчете обычно закрываются в течение последних 24 – 48 часов. <br/> |
|3.  <br/> |На диаграмме " **сайты** " показано количество общих и активных сайтов, включая любой сайт, в котором пользователи были просмотрены, изменены, загружены, загружены, предоставлены для совместного доступа или синхронизированы.  <br/> |
|4.  <br/> |На диаграмме **Файлы** отображаются общее количество файлов на всех сайтах и количество активных файлов. В общее количество входят и пользовательские, и системные файлы. Файл считается активным, если он был сохранен, синхронизирован, изменен или опубликован в течение определенного периода.  |
|5.  <br/> |Диаграмма **Хранилище** показывает тенденции выделения и использования хранилища в рамках отчетного периода.  <br/> |
|6.  <br/> |На диаграмме **Страницы** показано количество страниц, просмотренных на всех сайтах.  <br/> |
|7.  <br/> |Вы можете отфильтровать отображенные диаграммы, выбрав элемент в условных обозначениях. Например, на диаграмме **файлы** выберите **файлы** или **Активные файлы**. На диаграмме **сайты** можно выбрать пункт **общие сайты** или **активные сайты**. На диаграмме **хранилища** можно выбрать **выделенное хранилище** или **потребление памяти.** При выборе другого значения данные в таблице-сетке не меняются.  <br/> |
|8.  <br/> | В таблице показана разбивка действий по сайтам.  <br/> ![Параметры столбцов для отчета об использовании](../../media/sharepointsite-usage.png)           <br/> **URL-адрес сайта**  это полный URL-адрес сайта.  <br/> **Удалено**  это состояние удаления сайта. Сайты помечаются как удаленные не ранее чем через 7 дней.  <br/> **Владелец сайта**  имя пользователя, который является основным владельцем сайта.  <br/>**Имя участника-владельца сайта** — это адрес электронной почты владельца сайта.  <br/> **Дата последнего действия (UTC)**  дата последнего действия с файлами или просмотра страниц на сайте.  <br/> **Файлы**  число файлов на сайте.  <br/> **Активные файлы** — это количество активных файлов на сайте.<br/> NOTE: Если файлы были удалены в течение указанного периода времени для отчета, то количество активных файлов, отображаемых в отчете, может быть больше, чем текущее количество файлов на сайте.<br/>**Используемое хранилище (МБ)**  объем хранилища, которое используется на сайте.  <br/> **Выделенное хранилище (МБ)**  это максимальный объем хранилища, выделенного для сайта.  <br/> **Просмотры страниц**  количество просмотров страниц на сайте.  <br/> **Посещения страниц**  количество уникальных страниц, посещенных на сайте.  <br/> **Шаблон корневого веб-сайта**  шаблон, который применялся для создания сайта.  <br/> NOTE: Если вы хотите отфильтровать данные по различным типам сайтов, экспортируйте данные и используйте столбец корневого веб-шаблона. <br/>Если политики организации не позволяют просматривать отчеты, в которых есть личные сведения пользователей, можно изменить параметр конфиденциальности для всех отчетов. Ознакомьтесь с разделом " **как скрыть сведения о уровне пользователя?** " в [отчетах об активности в центре администрирования Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Выберите **Управление столбцами** ![ Управление столбцами ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) , чтобы добавить столбцы в отчет или удалить их из него.    <br/> |
|десяти.  <br/> |Вы также можете экспортировать данные отчета в CSV-файл Excel, выбрав ссылку **Экспорт** экспорта ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) . При этом данные всех сайтов будут экспортированы в формат, позволяющий сортировать и фильтровать их для дальнейшего анализа. Если у вас менее 2000 сайтов, вы можете сортировать и фильтровать значения в самой таблице отчета. Если сайтов больше 2000, для фильтрации и сортировки потребуется экспортировать данные.  <br/> NOTE: при экспорте данных в файл Excel обратите внимание на то, что Дата создания отчета о содержимом отражается в файле данных в **виде** столбца.      <br/>   |
|||
