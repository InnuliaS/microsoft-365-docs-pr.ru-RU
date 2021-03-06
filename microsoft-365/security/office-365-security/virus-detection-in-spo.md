---
title: Обнаружение вирусов в SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Сведения о том, как SharePoint Online обнаруживает вирусы в файлах, отправляемых пользователями, и запрещает пользователям загружать или синхронизировать эти файлы.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029612"
---
# <a name="virus-detection-in-sharepoint-online"></a>Обнаружение вирусов в SharePoint Online

Microsoft 365 поможет защитить среду от вредоносных программ, обнаруживая вирусы в файлах, отправляемых пользователями в SharePoint Online. После отправки файлы могут быть проверены на наличие вирусов. Если вирус заражен, для него задается соответствующее свойство, которое не позволяет пользователям скачать его из браузера или синхронизировать.

> [!IMPORTANT]
> Эти возможности в SharePoint Online позволяют включать вирусы. Они не предназначены для защиты от вредоносных программ в вашей среде. Мы рекомендуем всем клиентам оценивать и внедрять защиту от вредоносных программ на различных уровнях и применять рекомендации по обеспечению безопасности корпоративной инфраструктуры. Более подробную информацию о стратегиях и рекомендациях можно узнать в статье [Security Security](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Что происходит при отправке зараженного файла в SharePoint Online?

Microsoft 365 использует общий механизм обнаружения вирусов. Ядро работает асинхронно в SharePoint Online и сканирует некоторые файлы после их отправки. Эвристические алгоритмы используются для определения сканируемых файлов. Если выясняется, что файл содержит вирус, он помечается, чтобы его нельзя было снова скачать. В апреле 2018 был удален лимит в 25 МБ для сканированных файлов.

Ниже вкратце описано, что происходит.

1. Пользователь отправляет файл в SharePoint Online.

2. SharePoint Online определяет, соответствует ли файл условиям проверки.

3. Модуль поиска вирусов проверяет файл.

4. Если обнаружен вирус, антивирусная программа задает для файла свойство, указывающее на то, что оно заражено.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Что происходит, когда пользователь пытается скачать зараженный файл через браузер?

Если файл заражен, пользователи не могут скачать файл из SharePoint Online с помощью браузера.

Ниже вкратце описано, что происходит.

1. Пользователь открывает веб-браузер и пытается скачать зараженный файл из SharePoint Online.

2. Пользователю выдается предупреждение о том, что вирус обнаружен. Пользователю предоставляется возможность загрузить файл и попытаться очистить его с помощью собственного антивирусного программного обеспечения.

> [!NOTE]
> Вы можете использовать параметр *дисалловинфектедфиледовнлоад* командлета [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) в SharePoint Online PowerShell, чтобы запретить пользователям скачивать зараженный файл даже в окне предупреждения о антивирусной борьбе.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Что происходит, когда клиент синхронизации OneDrive пытается синхронизировать зараженный файл?

Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.

## <a name="more-information"></a>Дополнительные сведения

Для получения дополнительных сведений о настройке антивирусной программы SharePoint Online обратитесь к разделу [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) и [Включение ATP для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) .


