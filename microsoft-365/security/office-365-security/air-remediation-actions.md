---
title: Действия по исправлению в Office 365 автоматизированное исследование и ответ
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Сведения о действиях по исправлению в автоматическом расследовании и возможностях реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261056"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="4ece5-104">Действия по исправлению, следующие за автоматическим исследованием в Office 365</span><span class="sxs-lookup"><span data-stu-id="4ece5-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="4ece5-105">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="4ece5-105">Remediation actions</span></span>

<span data-ttu-id="4ece5-106">[Автоматизированные функции расследования и реагирования](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) в Office 365 Advanced Threat protection включают некоторые действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="4ece5-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="4ece5-107">При каждом запуске или завершении автоматического исследования обычно отображается одно или несколько действий по исправлению, требующих утверждения командой "Управление операциями безопасности" для продолжения.</span><span class="sxs-lookup"><span data-stu-id="4ece5-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="4ece5-108">В следующей таблице приведены действия по исправлению, которые в настоящее время доступны в Office 365 Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="4ece5-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="4ece5-109">Действие</span><span class="sxs-lookup"><span data-stu-id="4ece5-109">Action</span></span> | <span data-ttu-id="4ece5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4ece5-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="4ece5-111">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="4ece5-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="4ece5-112">Защита от сообщений электронной почты и документов, содержащих вредоносные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="4ece5-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="4ece5-113">Это позволяет блокировать вредоносные ссылки и связанные с ней веб-страницы, используя [безопасные ссылки](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) , когда пользователь щелкает ссылку в существующем файле Office или в старом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4ece5-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="4ece5-114">Обратимое удаление электронной почты</span><span class="sxs-lookup"><span data-stu-id="4ece5-114">Soft delete email</span></span>  |<span data-ttu-id="4ece5-115">Обратимое удаление определенных сообщений электронной почты из почтового ящика пользователя</span><span class="sxs-lookup"><span data-stu-id="4ece5-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="4ece5-116">Обратимое удаление кластеров электронной почты</span><span class="sxs-lookup"><span data-stu-id="4ece5-116">Soft delete email clusters</span></span>  |<span data-ttu-id="4ece5-117">Обратимое удаление вредоносных сообщений электронной почты, отвечающих запросу из почтовых ящиков всех пользователей</span><span class="sxs-lookup"><span data-stu-id="4ece5-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="4ece5-118">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="4ece5-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="4ece5-119">Удаление правила пересылки из определенного почтового ящика пользователя</span><span class="sxs-lookup"><span data-stu-id="4ece5-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="4ece5-120">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="4ece5-120">Approve (or reject) pending actions</span></span>

![Страница "действия по расследованию воздуха"](../../media/air-investigationactionspage.png)

<span data-ttu-id="4ece5-122">При просмотре [сведений об исследовании](air-view-investigation-results.md)вы можете утвердить или отклонить все ожидающие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="4ece5-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="4ece5-123">Мы рекомендуем сделать это как можно скорее, чтобы завершить автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="4ece5-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ece5-124">Для утверждения или отклонения действий по исправлению необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="4ece5-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="4ece5-125">Ознакомьтесь [с разрешениями, необходимыми для использования возможностей Air](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="4ece5-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="4ece5-126">Перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="4ece5-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="4ece5-127">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="4ece5-127">Select an item in the list.</span></span> <span data-ttu-id="4ece5-128">(При этом становятся активными кнопки утвердить и отклонить.)</span><span class="sxs-lookup"><span data-stu-id="4ece5-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="4ece5-129">Просмотрите доступные сведения о выбранных элементах, а затем либо утвердите, либо отклоните действия.</span><span class="sxs-lookup"><span data-stu-id="4ece5-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="4ece5-130">**Одобрить** разрешает запуск исправления.</span><span class="sxs-lookup"><span data-stu-id="4ece5-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="4ece5-131">**Отклонить** не предпринимать дальнейших действий</span><span class="sxs-lookup"><span data-stu-id="4ece5-131">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ece5-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4ece5-132">Next steps</span></span>

- [<span data-ttu-id="4ece5-133">Сведения о скомпрометированном пользователе безопасности стратегия</span><span class="sxs-lookup"><span data-stu-id="4ece5-133">Learn about the compromised user security playbook</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [<span data-ttu-id="4ece5-134">Просмотр отчетов ATP</span><span class="sxs-lookup"><span data-stu-id="4ece5-134">View your ATP reports</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)