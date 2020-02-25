---
title: Совместное использование календарей с внешними пользователями
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Сведения о том, как предоставить пользователям доступ к своим календарям внешним пользователям для собраний и встреч. '
ms.openlocfilehash: 42bce53c3963c41684644d02dab18210f9ed828a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254831"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="723fe-103">Совместное использование календарей с внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="723fe-103">Share calendars with external users</span></span>

<span data-ttu-id="723fe-p101">Часто приходится планировать встречи с людьми вне организации. Чтобы упростить процесс поиска взаимоприемлемого времени собрания, Office 365 позволяет сделать календари доступными "внешним пользователям"  тем, кому нужно видеть сведения о доступности, но у кого при этом нет учетных записей пользователей для среды Office 365.</span><span class="sxs-lookup"><span data-stu-id="723fe-p101">It's often necessary to schedule meetings with people outside your organization. To simplify the process of finding mutually agreeable meeting times, Office 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Office 365 environment.</span></span>
  
<span data-ttu-id="723fe-106">Общий доступ к календарю это глобальный параметр, то есть администратор может включить его для всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="723fe-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="723fe-107">После включения общего доступа пользователи могут использовать Outlook Web App для предоставления общего доступа к своим календарям в пределах организации или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="723fe-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="723fe-108">Пользователи в организации могут просматривать общий календарь параллельно с собственными.</span><span class="sxs-lookup"><span data-stu-id="723fe-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="723fe-109">Пользователям за прев Организации будет отправлен URL-адрес, который можно использовать для просмотра календаря.</span><span class="sxs-lookup"><span data-stu-id="723fe-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="723fe-110">Пользователи определяют, когда следует предоставлять общий доступ, каковы общие сведения и как хранить календари в частном порядке.</span><span class="sxs-lookup"><span data-stu-id="723fe-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="723fe-p103">Если вы хотите совместно использовать календари с организацией, работающей с Exchange Server 2013 (локально), администратор Exchange должен будет настроить связь проверки подлинности с облаком. Это называется "федерация", и она должна соответствовать минимальным требованиям к программному обеспечению. Дополнительные сведения см. в статье [Предоставление общего доступа](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="723fe-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="723fe-114">Включение общего доступа к календарю с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="723fe-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="723fe-115">В центре администрирования откройте страницу " **Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">служб &</a> надстроек".</span><span class="sxs-lookup"><span data-stu-id="723fe-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="723fe-116">На странице **" &amp; надстройки служб** " выберите пункт **Календарь**.</span><span class="sxs-lookup"><span data-stu-id="723fe-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="723fe-117">На открывшейся странице **календаря** укажите, хотите ли вы предоставить пользователям доступ к своим календарям пользователям за прев Организации, у которой есть Office 365 или Exchange.</span><span class="sxs-lookup"><span data-stu-id="723fe-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Office 365 or Exchange.</span></span>
    
4. <span data-ttu-id="723fe-118">Укажите, следует ли разрешить анонимным пользователям (пользователям без учетных данных для входа) доступ к календарям с помощью приглашения по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="723fe-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="723fe-119">Выберите тип данных календаря, который должен быть доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="723fe-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="723fe-120">Вы можете разрешить все данные или ограничить их только временем, темой и местом.</span><span class="sxs-lookup"><span data-stu-id="723fe-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="723fe-121">Приглашение пользователей для доступа к календарям</span><span class="sxs-lookup"><span data-stu-id="723fe-121">Invite people to access calendars</span></span>

<span data-ttu-id="723fe-p105">После включения общего доступа для клиента владельцы календаря могут создать приглашения для конкретных пользователей. Дополнительные инструкции см. в статье [Предоставление общего доступа к календарю в приложении Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx).</span><span class="sxs-lookup"><span data-stu-id="723fe-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  
