---
title: Совместное использование календарей с внешними пользователями
f1.keywords:
- NOCSH
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Сведения о том, как предоставить пользователям доступ к своим календарям внешним пользователям для собраний и встреч. '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780065"
---
# <a name="share-calendars-with-external-users"></a>Совместное использование календарей с внешними пользователями

Часто приходится планировать встречи с людьми вне организации. Чтобы упростить процесс поиска обоюдно согласованного времени собраний, Microsoft 365 позволяет сделать календари доступными для внешних пользователей, которые должны видеть сведения о занятости, но не имеют учетных записей пользователей для своей среды Майкрософт 365.
  
Общий доступ к календарю это глобальный параметр, то есть администратор может включить его для всех пользователей в клиенте. После включения общего доступа пользователи могут использовать Outlook Web App для предоставления общего доступа к своим календарям в пределах организации или за ее пределами. Пользователи в организации могут просматривать общий календарь параллельно с собственными. Пользователям за прев Организации будет отправлен URL-адрес, который можно использовать для просмотра календаря. Пользователи определяют, когда следует предоставлять общий доступ, каковы общие сведения и как хранить календари в частном порядке.
  
> [!NOTE]
> If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information. 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Включение общего доступа к календарю с помощью центра администрирования Microsoft 365

1. В центре администрирования перейдите в раздел Параметры **Settings** \> **Организации**параметров. 
    
2. На вкладке **службы** выберите пункт **Календарь**.
  
3. На открывшейся странице **календаря** укажите, хотите ли вы предоставить пользователям доступ к своим календарям пользователям за прев Организации, у которой есть Microsoft 365 или Exchange.
    
4. Укажите, следует ли разрешить анонимным пользователям (пользователям без учетных данных для входа) доступ к календарям с помощью приглашения по электронной почте.

5. Выберите тип данных календаря, который должен быть доступен пользователям. Вы можете разрешить все данные или ограничить их только временем, темой и местом.

    
## <a name="invite-people-to-access-calendars"></a>Приглашение пользователей для доступа к календарям

Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions. 
  
