---
title: ATP для SharePoint, OneDrive и Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Сведения о Advanced Threat Protection в Office 365 для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815413"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP для SharePoint, OneDrive и Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Обзор Office 365 ATP для SharePoint, OneDrive и Microsoft Teams

Пользователи регулярно совместно используют файлы и совместно работают с помощью SharePoint, OneDrive и Microsoft Teams. В [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) ваша организация может быть более безопасной совместной работой. ATP позволяет обнаруживать и блокировать файлы, которые определены как вредоносные на сайтах групп и библиотеках документов.

## <a name="how-office-365-atp-operates"></a>Как работает Office 365 ATP

Когда файл в SharePoint Online, OneDrive для бизнеса и Microsoft Teams определен как вредоносный, ATP напрямую интегрируется с хранилищами файлов для блокировки этого файла. На следующем рисунке показан пример вредоносного файла, обнаруженного в библиотеке.

![Файлы в OneDrive для бизнеса с одной обнаруженной вредоносной службой](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Несмотря на то, что заблокированный файл по-прежнему отображается в библиотеке документов и в веб-приложениях, на мобильных или для настольных компьютерах, заблокированный файл не может быть открыт, скопирован, перемещен или открыт для совместного использования. Тем не менее, пользователи могут удалить заблокированный файл. Вот пример того, что выглядит на мобильном устройстве пользователя:

![Удаление заблокированного файла из OneDrive для бизнеса из мобильного приложения OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

В зависимости от того, как настроена Microsoft 365, пользователи могут или не могут скачать заблокированный файл. Вот как будет выглядеть заблокированный файл на мобильном устройстве пользователя:

![Скачивание заблокированного файла в OneDrive для бизнеса](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Дополнительные сведения см. в статье [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="keep-these-points-in-mind"></a>Помните об этих моментах

- ATP не будет сканировать каждый отдельный файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams. Это сделано намеренно. Файлы сканируются асинхронно, с помощью процесса, который использует события общего доступа и гостевых действий, а также интеллектуальные эвристики и сигналы угроз для идентификации вредоносных файлов.

- Убедитесь, что сайты SharePoint настроены на использование [современного интерфейса](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Если файл определен как вредоносный и заблокированный, люди могут видеть, что это произошло в современном интерфейсе, но не является классическим представлением. Защита ATP определяет, используется ли современный интерфейс или классическое представление; Однако визуальные индикаторы, заблокированные файлом, присутствуют только в современном интерфейсе.

- Файлы, которые определены как вредоносные в SharePoint Online, OneDrive для бизнеса или Microsoft Teams, будут отображаться в [отчетах для Office 365 Advanced Threat protection](view-reports-for-atp.md) и в [Проводнике (и обнаружения в режиме реального времени)](threat-explorer.md).

- ATP является частью общей стратегии защиты от угроз, включающей защиту от нежелательной почты и вредоносных программ, а также безопасные ссылки и безопасные вложения. Чтобы узнать больше, ознакомьтесь [со статьей защита от угроз в Office 365](protect-against-threats.md).

- Администратор SharePoint Online может определить, следует ли разрешить пользователям загружать файлы, обнаруженные как вредоносные. Для этого необходимо выполнить командлет PowerShell Set-SPOTenant с параметром Дисалловинфектедфиледовнлоад ( [включить Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Карантин в ATP для SharePoint Online, OneDrive для бизнеса и Microsoft Teams

 Начиная с опоздания, Май 2018, функции [карантина](quarantine-email-messages.md) в &amp; центре безопасности соответствуют расширению ATP для SharePoint Online, OneDrive для бизнеса и Microsoft Teams.

Если файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams определен как вредоносный, помимо того, что ATP блокирует файл из-за открытия или предоставления общего доступа, этот файл включается в список элементов, помещенных в карантин. (В разделе Security &amp; Центр соответствия требованиям, перейдите к разделу **Управление угрозами** \> **Просмотр** \> **карантина** и отфильтруйте **файлы**.)

Если вы участвуете в работе группы безопасности Microsoft 365 для бизнеса и обладаете необходимыми [разрешениями в &amp; центре безопасности](permissions-in-the-security-and-compliance-center.md), можно загружать, освобождать, отчитываться и удалять файлы, обнаруженные как вредоносные, из карантина.

- При **освобождении и составлении отчетов** файл удаляется в файле на соответствующем сайте группы или в библиотеке документов для SharePoint, OneDrive или Microsoft Teams. После этого пользователи смогут открывать, предоставлять к ним общий доступ и скачивать файл. Если выбран параметр **Отправить отчет корпорации Майкрософт** , файл сообщается о ложном срабатывании в корпорацию Майкрософт.

- При **удалении файла** удаляется файл из карантина; Тем не менее, файл по-прежнему заблокирован от открытия или предоставления общего доступа. Файл также должен быть удален в соответствующей библиотеке документов или на сайте группы (SharePoint Online, OneDrive для бизнеса или Microsoft Teams).

- **Загрузка файла** позволяет скачать и проанализировать файл на наличие ложных срабатываний.

## <a name="next-steps"></a>Дальнейшие действия

 - [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)

 - [Просмотр сведений о вредоносных файлах, обнаруженных в SharePoint, OneDrive или Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

