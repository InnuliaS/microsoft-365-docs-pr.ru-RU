---
title: Сравнение групп в Office 365
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Сведения о типах групп, которые можно использовать в Office 365.
ms.openlocfilehash: 5b8a3a7859a510a07b579f3b1da255e555d6ae1f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245501"
---
# <a name="compare-groups"></a><span data-ttu-id="b9ec2-103">Сравнение групп</span><span class="sxs-lookup"><span data-stu-id="b9ec2-103">Compare groups</span></span>

<span data-ttu-id="b9ec2-104">В Центре администрирования Microsoft 365 в разделе **Группы** можно создавать и настраивать группы следующих типов:</span><span class="sxs-lookup"><span data-stu-id="b9ec2-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="b9ec2-105">**Группы Office 365** используются для совместной работы пользователей в организации и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-105">**Office 365 groups** are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="b9ec2-106">**Группы рассылки** используются для отправки уведомлений группе людей.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="b9ec2-107">**Группы безопасности** используются для предоставления доступа к ресурсам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-107">**Security groups** are used for granting access to SharePoint resources.</span></span>
- <span data-ttu-id="b9ec2-108">**Группы безопасности, поддерживающие почту** используются для предоставления доступа к ресурсам SharePoint и отправки уведомлений пользователям.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-108">**Mail-enabled security groups** are used for granting access to SharePoint resources, and emailing notifications to those users.</span></span>
- <span data-ttu-id="b9ec2-109">**Общие почтовые ящики** используются, если нескольким людям необходим доступ к одному и тому же почтовому ящику, например к электронному адресу службы поддержки или к почтовому ящику со сведениями о компании.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="office-365-groups"></a><span data-ttu-id="b9ec2-110">Группы Office 365</span><span class="sxs-lookup"><span data-stu-id="b9ec2-110">Office 365 groups</span></span>

<span data-ttu-id="b9ec2-111">Группы Office 365 используются для совместной работы пользователей в организации и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-111">Office 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="b9ec2-112">Участники каждой группы Office 365 получают электронную почту группы, общую рабочую область для бесед, файлов и событий календаря, а также Планировщик.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-112">With each Office 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="b9ec2-113">Вы можете добавить внешних пользователей в группу, если это [разрешено администратором](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b9ec2-113">You can add users external to your company to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="b9ec2-114">Кроме того, вы можете разрешить внешним отправителям отправлять письма на электронный адрес группы.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="b9ec2-115">Группы Office 365 можно [настроить для динамического членства в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), что позволяет добавлять или удалять участников группы автоматически на основе таких атрибутов пользователя, как отдел, расположение, должность и т. д.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-115">Office 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="b9ec2-116">Доступ к группам Office 365 можно получить через мобильные приложения, например Outlook для iOS и Outlook для Android.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-116">Office 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="b9ec2-117">Участники группы могут отправлять сообщения с электронного адреса группы (разрешения "Отправить как" или "Отправить от имени"), если это [разрешено администратором](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="b9ec2-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="b9ec2-118">Группы рассылки</span><span class="sxs-lookup"><span data-stu-id="b9ec2-118">Distribution groups</span></span>

<span data-ttu-id="b9ec2-119">[Группы рассылки](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) используются для отправки уведомлений группе людей.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="b9ec2-120">Они могут получать электронную почту от внешних отправителей, если это разрешено администратором.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="b9ec2-121">Группы рассылки лучше всего подходят для ситуаций, когда необходимо передать информацию определенной группе людей, такой как "Люди в здании А" или "Все сотрудники Contoso".</span><span class="sxs-lookup"><span data-stu-id="b9ec2-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="b9ec2-122">Группы безопасности</span><span class="sxs-lookup"><span data-stu-id="b9ec2-122">Security groups</span></span>

<span data-ttu-id="b9ec2-123">[Группы безопасности](../email/create-edit-or-delete-a-security-group.md) используются для предоставления доступа к ресурсам Office 365, например SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Office 365 resources, such as SharePoint.</span></span> <span data-ttu-id="b9ec2-124">Они упрощают администрирование, так как вам нужно просто выполнять администрирование группы вместо того, чтобы добавлять пользователей для каждого ресурса отдельно.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="b9ec2-125">Группы безопасности могут включать пользователей или устройства.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="b9ec2-126">Создание групп безопасности для устройств может использоваться в службах управления мобильными устройствами, например Intune.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="b9ec2-127">Группы безопасности можно [настроить для динамического членства в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), что позволяет добавлять или удалять участников группы или устройства автоматически на основе таких атрибутов пользователя, как отдел, расположение или должность, или таких атрибутов устройства, как версия операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="b9ec2-128">Группы безопасности, поддерживающие почту</span><span class="sxs-lookup"><span data-stu-id="b9ec2-128">Mail-enabled security groups</span></span>

<span data-ttu-id="b9ec2-129">Группы безопасности, поддерживающие почту, действуют так же, как и обычные группы безопасности, однако к ним не применимо динамическое управление с помощью Azure Active Directory и они не могут включать устройства.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="b9ec2-130">Эти группы позволяют отправлять сообщения всем участникам группы.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="b9ec2-131">Общие почтовые ящики</span><span class="sxs-lookup"><span data-stu-id="b9ec2-131">Shared mailboxes</span></span>

<span data-ttu-id="b9ec2-132">[Общие почтовые ящики](../email/create-a-shared-mailbox.md) используются, если нескольким людям необходим доступ к одному и тому же почтовому ящику, например к электронному адресу службы поддержки, почтовому ящику со сведениями о компании, столу регистрации или к другой функции, которую совместно используют несколько человек.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="b9ec2-133">Общие почтовые ящики могут получать сообщения от внешних отправителей, если это разрешено администратором.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="b9ec2-134">Пользователи с разрешениями для почтового ящика группы "Отправить как" или "Отправить от имени" могут отправлять сообщения с электронного адреса почтового ящика, если это разрешено администратором.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="b9ec2-135">Эта возможность особенно полезна для почтовых ящиков службы справки и поддержки, так как пользователи могут отправлять письма из таких групп, как "Служба поддержки Contoso" или "Создание стола регистрации".</span><span class="sxs-lookup"><span data-stu-id="b9ec2-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="b9ec2-136">В настоящее время невозможно перенести общий почтовый ящик в группу Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9ec2-136">Currently it's not possible to migrate a shared mailbox to an Office 365 Group.</span></span> <span data-ttu-id="b9ec2-137">Это то, что вы искали?</span><span class="sxs-lookup"><span data-stu-id="b9ec2-137">Is this something you want?</span></span> <span data-ttu-id="b9ec2-138">Дайте нам знать!</span><span class="sxs-lookup"><span data-stu-id="b9ec2-138">Let us know.</span></span> <span data-ttu-id="b9ec2-139">**[Проголосуйте здесь!](https://go.microsoft.com/fwlink/?linkid=871518)**</span><span class="sxs-lookup"><span data-stu-id="b9ec2-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**</span></span>

## <a name="related-articles"></a><span data-ttu-id="b9ec2-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b9ec2-140">Related articles</span></span>

[<span data-ttu-id="b9ec2-141">Сведения о Группах Office 365</span><span class="sxs-lookup"><span data-stu-id="b9ec2-141">Learn about Office 365 Groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)