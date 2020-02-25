---
title: Активные пользователи в отчетах об использовании Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Сведения об активных пользователях аналитики использования Microsoft 365, отчетах об активности и метриках внедрения.
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247280"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a><span data-ttu-id="6829b-103">Активные пользователи в отчетах об использовании Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6829b-103">Active user in Microsoft 365 usage reports</span></span>

## <a name="active-user-in-usage-reports"></a><span data-ttu-id="6829b-104">Активные пользователи в отчетах об использовании</span><span class="sxs-lookup"><span data-stu-id="6829b-104">Active user in usage reports</span></span>

<span data-ttu-id="6829b-105">Активный пользователь продуктов Microsoft 365 для [аналитики использования microsoft 365](usage-analytics.md) и [отчеты об активности в центре администрирования](../activity-reports/activity-reports.md) определены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6829b-105">An active user of Microsoft 365 products for [Microsoft 365 usage analytics](usage-analytics.md) and the [Activity Reports in the admin center](../activity-reports/activity-reports.md) is defined as follows.</span></span> 
  
|<span data-ttu-id="6829b-106">**Продукт**</span><span class="sxs-lookup"><span data-stu-id="6829b-106">**Product**</span></span>|<span data-ttu-id="6829b-107">**Определение активного пользователя**</span><span class="sxs-lookup"><span data-stu-id="6829b-107">**Definition of an active user**</span></span>|<span data-ttu-id="6829b-108">**Примечания**</span><span class="sxs-lookup"><span data-stu-id="6829b-108">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6829b-109">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6829b-109">Exchange Online</span></span>  <br/> |<span data-ttu-id="6829b-110">Любой пользователь, который прочитал или отправил по крайней мере одно сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6829b-110">Any user who has read or sent an email.</span></span>  <br/> |<span data-ttu-id="6829b-111">Данные календаря не учитываются (эта возможность будет добавлена в будущем).</span><span class="sxs-lookup"><span data-stu-id="6829b-111">No calendar information is represented, this will be added in an upcoming update.</span></span>  <br/> |
|<span data-ttu-id="6829b-112">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6829b-112">SharePoint Online</span></span>  <br/> |<span data-ttu-id="6829b-113">Любой пользователь, который создал, изменил, просмотрел, удалил файл, предоставил к нему внутренний или внешний доступ, синхронизировался с клиентами на любом сайте или просмотрел страницу на любом сайте.</span><span class="sxs-lookup"><span data-stu-id="6829b-113">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients on any site or viewed a page on any site.</span></span>  <br/> |<span data-ttu-id="6829b-114">Метрика активного пользователя SharePoint Online в приложении шаблона аналитики использования Microsoft 365 отражает только пользователей, которые выполнили действия с файлами на сайте группы SharePoint или на сайте группы.</span><span class="sxs-lookup"><span data-stu-id="6829b-114">The active user metric for SharePoint Online in the Microsoft 365 Usage Analytics template app only reflect users who did file activity against a SharePoint Team site or a Group site.</span></span> <span data-ttu-id="6829b-115">Приложение шаблона будет обновлено для синхронизации определения с тем же именем, что и в отчетах об использовании в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="6829b-115">The template app will be updated to synchronize the definition to the same as that on the usage reports in the admin center.</span></span>  <br/> |
|<span data-ttu-id="6829b-116">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6829b-116">OneDrive for Business</span></span>  <br/> |<span data-ttu-id="6829b-117">Любой пользователь, который создал, изменил, просмотрел, удалил файл, предоставил к нему внутренний или внешний доступ либо синхронизировался с клиентами на любом сайте.</span><span class="sxs-lookup"><span data-stu-id="6829b-117">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients.</span></span>  <br/> ||
|<span data-ttu-id="6829b-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="6829b-118">Yammer</span></span>  <br/> |<span data-ttu-id="6829b-119">Любой пользователь, который прочитал, опубликовал сообщение или поставил отметку "Нравится" в Yammer.</span><span class="sxs-lookup"><span data-stu-id="6829b-119">Any user who has read, posted, or liked a message on Yammer.</span></span>  <br/> ||
|<span data-ttu-id="6829b-120">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6829b-120">Skype for Business</span></span>  <br/> |<span data-ttu-id="6829b-121">Любой пользователь, который участвовал в одноранговом сеансе (включая обмен мгновенными сообщениями, голосовые вызовы и видеозвонки, общий доступ к приложениям и передачу файлов), организовал конференцию или принимал участие в ней.</span><span class="sxs-lookup"><span data-stu-id="6829b-121">Any user who has participated in a peer-to-peer session (including instant messaging, audio and video calls, application sharing, and file transfers) or who has organized or participated in a conference.</span></span>  <br/> ||
|<span data-ttu-id="6829b-122">Office</span><span class="sxs-lookup"><span data-stu-id="6829b-122">Office</span></span>  <br/> |<span data-ttu-id="6829b-123">Любой пользователь, который активировал свою подписку на Microsoft 365 Pro Plus, Visio Pro или Project Pro по крайней мере на одном устройстве.</span><span class="sxs-lookup"><span data-stu-id="6829b-123">Any user who has activated their Microsoft 365 Pro Plus, Visio Pro or Project Pro subscription on at least one device.</span></span>  <br/> ||
|<span data-ttu-id="6829b-124">Группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6829b-124">Microsoft 365 Groups</span></span>  <br/> |<span data-ttu-id="6829b-125">Любой участник группы, который выполнял действия в почтовом ящике (если в группу было отправлено хотя бы одно сообщение)</span><span class="sxs-lookup"><span data-stu-id="6829b-125">Any group member that has mailbox activity (if a message has been sent to the group)</span></span>  <br/> |<span data-ttu-id="6829b-126">Это определение будет расширено с действием файл сайта группы и действия группы Yammer (активность файлов на сайте группы и сообщения, опубликованные в группе Yammer, связанной с группой). В настоящее время эти данные недоступны в приложении шаблона аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6829b-126">This definition will be enhanced with group site file activity and Yammer group activity (file activity on group site and message posted to Yammer group associated with the group.) This data is currently not available in the Microsoft 365 Usage Analytics template app</span></span>  <br/> |
|<span data-ttu-id="6829b-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6829b-127">Microsoft Teams</span></span>  <br/> |<span data-ttu-id="6829b-128">Любой пользователь, который участвовал в сообщениях чата, сообщениях частного чата, звонках, собраниях и других действиях.</span><span class="sxs-lookup"><span data-stu-id="6829b-128">Any user who has participated in chat messages, private chat messages, calls,meetings or other activity.</span></span> <span data-ttu-id="6829b-129">Другие действия определяются по мере того, как число других действий группы осуществляется пользователем, некоторые из которых включают в себя сообщения, приложения, работу с файлами, поиск, а также команды и фаворитинг.</span><span class="sxs-lookup"><span data-stu-id="6829b-129">Other activity is defined as the number of other team activities by the user some of which include, and not limited to: liking messages, apps, working on files, searching, following teams and channel and favoriting them.</span></span>  <br/> ||
   
## <a name="adoption-metrics"></a><span data-ttu-id="6829b-130">Показатели внедрения</span><span class="sxs-lookup"><span data-stu-id="6829b-130">Adoption Metrics</span></span>

<span data-ttu-id="6829b-131">[Аналитика использования Microsoft 365](usage-analytics.md) содержит дополнительные метрики, связанные с активными пользователями, чтобы показать, какие продукты были применены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="6829b-131">[Microsoft 365 usage analytics](usage-analytics.md) contains additional adoption metrics related to active users to show adoption of the products over time.</span></span> <span data-ttu-id="6829b-132">Эти показатели действительны в соответствии с выбранным месяцем, годом и продуктом и определяются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6829b-132">These metrics are valid for the month, year, and product selected and are defined as follows.</span></span> 
  
|<span data-ttu-id="6829b-133">**Метр**</span><span class="sxs-lookup"><span data-stu-id="6829b-133">**Metric**</span></span>|<span data-ttu-id="6829b-134">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6829b-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6829b-135">енабледусерс</span><span class="sxs-lookup"><span data-stu-id="6829b-135">EnabledUsers</span></span>  <br/> |<span data-ttu-id="6829b-136">Количество пользователей, которые могут использовать продукт в месяц.</span><span class="sxs-lookup"><span data-stu-id="6829b-136">Number of users enabled to use the product in the month.</span></span>  <br/> |
|<span data-ttu-id="6829b-137">активеусерс</span><span class="sxs-lookup"><span data-stu-id="6829b-137">ActiveUsers</span></span>  <br/> |<span data-ttu-id="6829b-138">Количество активных пользователей в месяце.</span><span class="sxs-lookup"><span data-stu-id="6829b-138">Number of users active in the month.</span></span>  <br/> |
|<span data-ttu-id="6829b-139">момретурнингусерс</span><span class="sxs-lookup"><span data-stu-id="6829b-139">MoMReturningUsers</span></span>  <br/> |<span data-ttu-id="6829b-140">Количество активных пользователей в месяц, которые также активны в предыдущем месяце.</span><span class="sxs-lookup"><span data-stu-id="6829b-140">Number of users active in the month that were also active in the preceding month.</span></span>  <br/> |
|<span data-ttu-id="6829b-141">фирсттимеусерс</span><span class="sxs-lookup"><span data-stu-id="6829b-141">FirstTimeUsers</span></span>  <br/> |<span data-ttu-id="6829b-142">Количество активных пользователей в месяц, в течение которых служба раньше никогда не использовалась.</span><span class="sxs-lookup"><span data-stu-id="6829b-142">Number of users active in the month that had never used the service before.</span></span>  <br/> |
|<span data-ttu-id="6829b-143">кумулативеактивеусерс</span><span class="sxs-lookup"><span data-stu-id="6829b-143">CumulativeActiveUsers</span></span>  <br/> |<span data-ttu-id="6829b-144">Количество пользователей, активных в месяц плюс любой предшествующий месяц.</span><span class="sxs-lookup"><span data-stu-id="6829b-144">Number of users active in the month plus any preceding month.</span></span>  <br/> |
|<span data-ttu-id="6829b-145">Активеусерс (%)</span><span class="sxs-lookup"><span data-stu-id="6829b-145">ActiveUsers(%)</span></span>  <br/> |<span data-ttu-id="6829b-146">Процент пользователей, округленный до ближайших десятых, активных в месяц по сравнению с числом пользователей, включенных в этот месяц.</span><span class="sxs-lookup"><span data-stu-id="6829b-146">Percent of users, rounded to the nearest tenth, active in the month compared to the number of users enabled in that month.</span></span>  <br/> |
|<span data-ttu-id="6829b-147">Момретурнингусерс (%)</span><span class="sxs-lookup"><span data-stu-id="6829b-147">MoMReturningUsers(%)</span></span>  <br/> |<span data-ttu-id="6829b-148">Процент пользователей, округленных до ближайших десятых, активных в месяц, которые также активны в предыдущем месяце по сравнению с числом активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6829b-148">Percent of users, rounded to the nearest tenth, active in the month that were also active in the preceding month compared to the number of active users.</span></span>  <br/> |
   
<span data-ttu-id="6829b-149">Момретурнингусерс, Фирсттимеусерс, &amp; кумулативеактивеусерс были сброшены, начиная с 1 января 2018 и заканчивая включением Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6829b-149">MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers were reset starting January 1st 2018 with the inclusion of Microsoft Teams.</span></span>
  