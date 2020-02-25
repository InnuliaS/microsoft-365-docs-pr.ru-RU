---
title: Разрешение пользователям отправлять сообщения от имени группы или отправлять от него
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Сведения о том, как разрешить участникам отправлять электронную почту в виде группы Office 365 или отправлять электронную почту от имени группы Office 365.
ms.openlocfilehash: c0dca3a3bbed6617874d9dfbca06a4ec5d6b4ebc
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245519"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="97824-103">Разрешение пользователям отправлять сообщения от имени группы или отправлять от него</span><span class="sxs-lookup"><span data-stu-id="97824-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="97824-104">Члены группы Office 365, которым предоставлены разрешения " **Отправить как** " или " **Отправить от имени** ", теперь могут отправлять сообщения электронной почты в виде группы или от имени группы.</span><span class="sxs-lookup"><span data-stu-id="97824-104">A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="97824-105">В этом разделе объясняется, как администратор может настроить эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="97824-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="97824-106">Например, если Меган Бовен входит в **учебную** группу Office 365 и имеет разрешения " **Отправить как** " для группы, то, если она отправляет сообщение электронной почты в качестве группы, она будет выглядеть так, как **учебная** группа отправила сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="97824-106">For example, if Megan Bowen is part of the **Training** Office 365 Group, and has **Send as** permissions on the group, if she sends an email as the Group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="97824-107">Разрешение " **Отправить от имени** " позволяет пользователю отправлять электронную почту от имени группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="97824-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group.</span></span> <span data-ttu-id="97824-108">Например, если Алекс Вилбер является частью **маркетинговой** группы Office 365 и имеет разрешения " **Отправить от имени** " и отправляет сообщение электронной почты в качестве группы, сообщение будет выглядеть так, как если бы оно было отправлено пользователем **Алекс Вилбер от имени маркетингового отдела**.</span><span class="sxs-lookup"><span data-stu-id="97824-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97824-109">Вы можете настроить " **Отправить как** " или " **Отправить от имени** " для определенного пользователя, но не для обоих.</span><span class="sxs-lookup"><span data-stu-id="97824-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="97824-110">Если вы настроили оба значения, то по умолчанию будет **отправляться как**.</span><span class="sxs-lookup"><span data-stu-id="97824-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="97824-111">Чтобы узнать, как использовать Outlook и Outlook в Интернете для отправки электронной почты из группы, ознакомьтесь со статьей " [Отправка почты от имени" или "от имени" для группы Office 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) .</span><span class="sxs-lookup"><span data-stu-id="97824-111">Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a Group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="97824-112">Разрешение участникам отправлять электронную почту как группу</span><span class="sxs-lookup"><span data-stu-id="97824-112">Allow members to send email as a Group</span></span>

<span data-ttu-id="97824-113">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту как группу в [центре администрирования Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="97824-113">This section explains how to allow users to send email as a Group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="97824-114">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="97824-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="97824-115">Выберите команду **изменить**![значок](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования группы для группы, которую нужно разрешить пользователям отправлять.  </span><span class="sxs-lookup"><span data-stu-id="97824-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="97824-116">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="97824-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="97824-117">В разделе **Отправить как** выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="97824-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Office 365.](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="97824-119">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="97824-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="97824-120">Нажмите кнопку **ОК** и **Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="97824-120">Select **OK** and **Save**.</span></span>
    
    ![Введите текст для поиска или выберите пользователя из списка.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="97824-122">Разрешение участникам отправлять электронную почту от имени группы</span><span class="sxs-lookup"><span data-stu-id="97824-122">Allow members to send email on behalf of a Group</span></span>

<span data-ttu-id="97824-123">В этом разделе объясняется, как разрешить пользователям отправлять электронную почту от имени группы в центре администрирования Exchange в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="97824-123">This section explains how to allow users to send email on behalf of a Group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="97824-124">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="97824-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="97824-125">Выберите команду **изменить** ![значок](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) редактирования группы для группы, которую нужно разрешить пользователям отправлять.</span><span class="sxs-lookup"><span data-stu-id="97824-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="97824-126">Выберите пункт **Делегирование группы**.</span><span class="sxs-lookup"><span data-stu-id="97824-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="97824-127">В разделе Отправить от имени выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы.</span><span class="sxs-lookup"><span data-stu-id="97824-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Office 365.](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="97824-129">Введите имя, чтобы найти пользователя, или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="97824-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="97824-130">Нажмите кнопку **ОК** и **Сохраните**.</span><span class="sxs-lookup"><span data-stu-id="97824-130">Select **OK** and **Save**.</span></span>
    
    ![Введите текст для поиска или выберите пользователя из списка.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="97824-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="97824-132">Related articles</span></span>

[<span data-ttu-id="97824-133">Дополнительные сведения о группах Office 365</span><span class="sxs-lookup"><span data-stu-id="97824-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="97824-134">Add — RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="97824-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="97824-135">Set — UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="97824-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)