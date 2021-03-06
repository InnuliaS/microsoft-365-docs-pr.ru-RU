---
title: Просмотр действий с метками для документов
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Узнайте, как использовать Обозреватель действий с метками в Центре безопасности и соответствия требованиям Microsoft 365 для поиска и просмотра действий с метками.
ms.openlocfilehash: 9cf505575a17c8f6eb4d48e609d358f9c988965f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819029"
---
# <a name="view-label-activity-for-documents"></a>Просмотр действий с метками для документов

After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.
  
Например, при помощи обозревателя действий с метками вы можете:
  
- Просматривать, сколько раз каждая метка применялась в тот или иной день (до 30 дней).
    
- Узнавать, кто и когда помечал какие файлы, и получать ссылки на сайты, где они хранятся.
    
- Определять, метки каких файлов были изменены или удалены, просматривать старые и новые метки, а также узнавать, кто внес изменение.
    
- Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
    
- View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.
    
Обозреватель действий с метками можно открыть из Центра безопасности &amp; соответствия требованиям, выбрав пункты **Управление информацией** > **Обозреватель действий с метками**.
  
Обратите внимание, что для использования обозревателя действий с метками необходима подписка на Office 365 корпоративный E5.
  
![Обозреватель действий с метками](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a>Просмотр действий с метками для файлов и папок

At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.
  
You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Раскрывающееся меню с пунктами для просмотра действий с файлами и папками](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a>Действия с метками

 **Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day. 
  
### <a name="label-changes"></a>Изменения меток

 **Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right. 
  
![Область сведений о действиях с метками](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a>Фильтрация действий с метками

You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.
  
![Фильтры для действий с метками](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

