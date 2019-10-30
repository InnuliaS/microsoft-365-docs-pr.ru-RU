---
title: Миграция из Microsoft 365 Business в Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Сведения о том, как перенести бизнес-деятельность из Microsoft 365 Business в Microsoft 365 корпоративный E3.
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772728"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="e45e8-103">Миграция из Microsoft 365 Business в Microsoft 365 корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="e45e8-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="e45e8-104">Microsoft 365 Business имеет все необходимое для малого бизнеса, объединяя лучшие облачные приложения для продуктивной работы с помощью простого управления устройствами и обеспечения безопасности, которые позволяют сотрудникам выполнять свои действия.</span><span class="sxs-lookup"><span data-stu-id="e45e8-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="e45e8-105">Однако в некоторых случаях вам может потребоваться перенести Microsoft 365 бизнес-подписку на Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="e45e8-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="e45e8-106">Например, ваша организация увеличилась и нуждается в более чем 300 лицензиях (Поздравляем, кстати).</span><span class="sxs-lookup"><span data-stu-id="e45e8-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="e45e8-107">Кроме того, для вашего бизнеса требуются корпоративные функции, такие как Office 365 профессиональный плюс, Windows 10 Корпоративная или корпоративные клиентские лицензии (CAL).</span><span class="sxs-lookup"><span data-stu-id="e45e8-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="e45e8-108">Миграция проста: просто переключите лицензии.</span><span class="sxs-lookup"><span data-stu-id="e45e8-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="e45e8-109">Все ваши данные и конфигурация в текущей подписке поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e45e8-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="e45e8-110">Вы не можете подготовиться к миграции и не предпринимать никаких дополнительных действий, кроме использования новых функций.</span><span class="sxs-lookup"><span data-stu-id="e45e8-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="e45e8-111">Вы также можете использовать подписку на Microsoft 365 Business для получения до 300 рабочих мест и получения подписки на Microsoft 365 корпоративный E3 для более чем 300 рабочих мест.</span><span class="sxs-lookup"><span data-stu-id="e45e8-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="e45e8-112">Однако Office 365 ATP не входит в состав Microsoft 365 корпоративный E3.</span><span class="sxs-lookup"><span data-stu-id="e45e8-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="e45e8-113">Необходимо добавить дополнительные лицензии Office 365 ATP для пользователей в вашей подписке Microsoft 365 корпоративный E3.</span><span class="sxs-lookup"><span data-stu-id="e45e8-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="e45e8-114">Различия между Microsoft 365 Business и Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="e45e8-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e45e8-115">В этой таблице показаны различия между Microsoft 365 Business и Microsoft 365 корпоративный E3.</span><span class="sxs-lookup"><span data-stu-id="e45e8-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="e45e8-116">Компонент</span><span class="sxs-lookup"><span data-stu-id="e45e8-116">Feature</span></span>   | <span data-ttu-id="e45e8-117">Поддержка в Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e45e8-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="e45e8-118">Поддержка в Microsoft 365 корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="e45e8-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="e45e8-119">**Локальная среда**</span><span class="sxs-lookup"><span data-stu-id="e45e8-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="e45e8-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e45e8-120">Windows 10</span></span>    | <span data-ttu-id="e45e8-121">Windows 10 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e45e8-121">Windows 10 Business</span></span>  |    <span data-ttu-id="e45e8-122">Windows 10 Корпоративная E3</span><span class="sxs-lookup"><span data-stu-id="e45e8-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="e45e8-123">Приложения Office \*</span><span class="sxs-lookup"><span data-stu-id="e45e8-123">Office apps\*</span></span>  | [<span data-ttu-id="e45e8-124">Office 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="e45e8-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="e45e8-125">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="e45e8-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="e45e8-126">**Облачные приложения для работы**</span><span class="sxs-lookup"><span data-stu-id="e45e8-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="e45e8-127">Exchange Online и Outlook</span><span class="sxs-lookup"><span data-stu-id="e45e8-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="e45e8-128">50 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e45e8-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="e45e8-129">100 ГБ дискового пространства для почтового ящика и неограниченная Архивация на базе Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e45e8-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="e45e8-130">Teams</span><span class="sxs-lookup"><span data-stu-id="e45e8-130">Teams</span></span> | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-133">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e45e8-133">OneDrive for Business</span></span> | <span data-ttu-id="e45e8-134">ограничения на размер хранилища на одного пользователя (1 ТБ)</span><span class="sxs-lookup"><span data-stu-id="e45e8-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="e45e8-135">Без ограничений</span><span class="sxs-lookup"><span data-stu-id="e45e8-135">Unlimited</span></span> | 
| <span data-ttu-id="e45e8-136">Yammer, SharePoint Online, планировщик, поток</span><span class="sxs-lookup"><span data-stu-id="e45e8-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="e45e8-139">StaffHub</span></span>  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-142">Диспетчер клиентов Outlook, Милеик</span><span class="sxs-lookup"><span data-stu-id="e45e8-142">Outlook Customer Manager, MileIQ</span></span>  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | | 
| <span data-ttu-id="e45e8-144">**Защита от угроз**</span><span class="sxs-lookup"><span data-stu-id="e45e8-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="e45e8-145">Возможности сокращения уязвимой зоны</span><span class="sxs-lookup"><span data-stu-id="e45e8-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="e45e8-146">Просмотреть этот список</span><span class="sxs-lookup"><span data-stu-id="e45e8-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="e45e8-147">Корпоративное управление изоляцией на основе оборудования для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e45e8-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="e45e8-148">Office 365 Advanced Threat protection (ATP), план 1</span><span class="sxs-lookup"><span data-stu-id="e45e8-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)  | <span data-ttu-id="e45e8-150">Не включено, но его можно добавить на</span><span class="sxs-lookup"><span data-stu-id="e45e8-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="e45e8-151">**управление удостоверениями;**</span><span class="sxs-lookup"><span data-stu-id="e45e8-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="e45e8-152">Самостоятельный сброс паролей для гибридных учетных записей Azure Active Directory (Azure AD), служба Azure Multi-Factor Authentication (MFA), условный доступ, обратная запись пароля для локальных удостоверений</span><span class="sxs-lookup"><span data-stu-id="e45e8-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Входит в состав Microsoft 365 Business](./media/check-mark.png) | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-155">Обнаружение облачных приложений, работоспособность подключения Azure AD</span><span class="sxs-lookup"><span data-stu-id="e45e8-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-157">Единый вход для приложений Azure AD Office 365 (SSO): 10 приложений на пользователя (приложения коллекции, такие как Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="e45e8-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Входит в состав Microsoft 365 Business](./media/check-mark.png) | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-160">Azure AD Premium 1 SSO: без ограничений (локальных приложений через прокси приложения Azure AD и негалереи приложения с помощью шаблонов интеграции приложений самостоятельно)</span><span class="sxs-lookup"><span data-stu-id="e45e8-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-162">**Управление устройствами и приложениями**</span><span class="sxs-lookup"><span data-stu-id="e45e8-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="e45e8-163">Microsoft Intune, Windows для автопилота</span><span class="sxs-lookup"><span data-stu-id="e45e8-163">Microsoft Intune, Windows Autopilot</span></span>|  ![Входит в состав Microsoft 365 Business](./media/check-mark.png) | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
|<span data-ttu-id="e45e8-166">Доступ к виртуальному рабочему столу (вда)</span><span class="sxs-lookup"><span data-stu-id="e45e8-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
|<span data-ttu-id="e45e8-168">Виртуальный рабочий стол Windows (ВВД)</span><span class="sxs-lookup"><span data-stu-id="e45e8-168">Windows Virtual Desktop (WVD)</span></span>  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png) |     ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
|<span data-ttu-id="e45e8-171">Активация на общем компьютере (SCA)</span><span class="sxs-lookup"><span data-stu-id="e45e8-171">Shared Computer Activation (SCA)</span></span>   | ![Входит в состав Microsoft 365 Business](./media/check-mark.png) |     ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-174">Пакет оптимизации рабочего стола Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e45e8-174">Microsoft Desktop Optimization Package</span></span>    | |     ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-176">**Защита информации**</span><span class="sxs-lookup"><span data-stu-id="e45e8-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="e45e8-177">Защита от потери данных в Office 365, план Azure Information Protection (план 1)</span><span class="sxs-lookup"><span data-stu-id="e45e8-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-180">Защита информации о Windows для конечной точки DLP</span><span class="sxs-lookup"><span data-stu-id="e45e8-180">Window Information Protection for endpoint DLP</span></span>    | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-183">**Лицензия клиентского доступа (права CAL)**</span><span class="sxs-lookup"><span data-stu-id="e45e8-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="e45e8-184">Набор корпоративных лицензий CAL (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, управление правами Windows)</span><span class="sxs-lookup"><span data-stu-id="e45e8-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-186">**Соответствие требованиям**</span><span class="sxs-lookup"><span data-stu-id="e45e8-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="e45e8-187">Неограниченная Архивация электронной почты</span><span class="sxs-lookup"><span data-stu-id="e45e8-187">Unlimited email archiving</span></span> | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-190">Диспетчер соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e45e8-190">Compliance Manager</span></span>    | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-193">Обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="e45e8-193">eDiscovery</span></span>    | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-196">Удержание на месте и удержание для судебного разбирательства</span><span class="sxs-lookup"><span data-stu-id="e45e8-196">In-place hold and litigation hold</span></span> | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
| <span data-ttu-id="e45e8-199">Теги и политики хранения для управления записями сообщений</span><span class="sxs-lookup"><span data-stu-id="e45e8-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Входит в состав Microsoft 365 Business](./media/check-mark.png)   | ![Входит в состав Microsoft 365 корпоративный E3](./media/check-mark.png) | 
||||

<span data-ttu-id="e45e8-202">\*Пользователи, которым назначен доступ к приложениям SaaS, могут получать единый единый доступ к 10 приложениям.</span><span class="sxs-lookup"><span data-stu-id="e45e8-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="e45e8-203">Администраторы могут настраивать единый вход и изменять доступ пользователей к различным приложениям SaaS, но доступ SSO разрешен только для 10 приложений на пользователя за раз.</span><span class="sxs-lookup"><span data-stu-id="e45e8-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="e45e8-204">Все приложения Office 365 считаются одним приложением.</span><span class="sxs-lookup"><span data-stu-id="e45e8-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="e45e8-205">Миграция</span><span class="sxs-lookup"><span data-stu-id="e45e8-205">Migration</span></span>

<span data-ttu-id="e45e8-206">Чтобы выполнить миграцию, свяжитесь с партнером, чтобы перенести Microsoft 365 бизнес-подписку и лицензии на подписку Microsoft 365 корпоративный E3 с лицензиями.</span><span class="sxs-lookup"><span data-stu-id="e45e8-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="e45e8-207">В следующих разделах описываются изменения, которые необходимо выполнить, если они есть, и действия, которые можно выполнить после миграции.</span><span class="sxs-lookup"><span data-stu-id="e45e8-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="e45e8-208">Конфигурация и данные подписки Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e45e8-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="e45e8-209">Вам не нужно вносить никаких изменений в текущую подписку или данные перед миграцией, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="e45e8-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="e45e8-210">Конфигурация подписки, например доменные имена DNS.</span><span class="sxs-lookup"><span data-stu-id="e45e8-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="e45e8-211">Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="e45e8-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="e45e8-212">Конфигурации служб производительности и их данные, такие как Teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.</span><span class="sxs-lookup"><span data-stu-id="e45e8-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="e45e8-213">Теперь пользователи могут работать с неограниченным хранилищем в папках почтовых ящиков Exchange Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e45e8-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="e45e8-214">Вы можете начать использовать обнаружение облачных приложений, работоспособность Azure AD Connect и единый вход для более чем 10 приложений.</span><span class="sxs-lookup"><span data-stu-id="e45e8-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="e45e8-215">После перехода на Microsoft 365 корпоративный E3 вы больше не сможете Outlook Customer Manager и Милеик.</span><span class="sxs-lookup"><span data-stu-id="e45e8-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="e45e8-216">Защита от угроз</span><span class="sxs-lookup"><span data-stu-id="e45e8-216">Threat protection</span></span>

<span data-ttu-id="e45e8-217">Windows 10 бизнес включает следующие средства защиты:</span><span class="sxs-lookup"><span data-stu-id="e45e8-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="e45e8-218">Обеспечение целостности процесса загрузки операционной системы</span><span class="sxs-lookup"><span data-stu-id="e45e8-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="e45e8-219">Обеспечение целостности важных рабочих компонентов</span><span class="sxs-lookup"><span data-stu-id="e45e8-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="e45e8-220">Повышенная уязвимость и устранение уязвимостей с использованием нулевого дня</span><span class="sxs-lookup"><span data-stu-id="e45e8-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="e45e8-221">Защита сети на основе репутации для Microsoft EDGE, Internet Explorer и Chrome</span><span class="sxs-lookup"><span data-stu-id="e45e8-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="e45e8-222">Брандмауэр на основе узла</span><span class="sxs-lookup"><span data-stu-id="e45e8-222">Host-based firewall</span></span>
- <span data-ttu-id="e45e8-223">Снижение опасности для атаки программой «шантажистом»</span><span class="sxs-lookup"><span data-stu-id="e45e8-223">Ransomware mitigations</span></span>
- <span data-ttu-id="e45e8-224">Изоляция на основе оборудования для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e45e8-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="e45e8-225">Управление приложениями на базе интеллектуального графа безопасности</span><span class="sxs-lookup"><span data-stu-id="e45e8-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="e45e8-226">Управление устройством (USB)</span><span class="sxs-lookup"><span data-stu-id="e45e8-226">Device control (USB)</span></span>
- <span data-ttu-id="e45e8-227">Защита сети от угроз для веб-угроз</span><span class="sxs-lookup"><span data-stu-id="e45e8-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="e45e8-228">Правила предотвращения вторжения для узла</span><span class="sxs-lookup"><span data-stu-id="e45e8-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="e45e8-229">Windows 10 Корпоративная E3 также включает управление изоляцией на основе аппаратного обеспечения для Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e45e8-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="e45e8-230">После перехода на Microsoft 365 корпоративный E3 у вас больше нет Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="e45e8-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="e45e8-231">Вы можете приобрести дополнительные лицензии Office 365 ATP для вашей подписки на Microsoft 365 корпоративный E3 и назначить их учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="e45e8-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="e45e8-232">Управление устройствами с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="e45e8-232">Device management with Intune</span></span>

<span data-ttu-id="e45e8-233">Перед миграцией не требуется вносить никаких изменений в текущую конфигурацию Intune, в том числе зарегистрированные устройства и параметры устройств и приложений.</span><span class="sxs-lookup"><span data-stu-id="e45e8-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="e45e8-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e45e8-234">Windows 10</span></span>

<span data-ttu-id="e45e8-235">Microsoft 365 Business включает Windows 10 бизнес, которую можно установить с помощью Windows автопилота.</span><span class="sxs-lookup"><span data-stu-id="e45e8-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="e45e8-236">При переходе на Microsoft 365 корпоративный E3 каждая пользовательская лицензия включает Windows 10 Корпоративная версия E3, которую можно также установить с помощью Windows автопилота.</span><span class="sxs-lookup"><span data-stu-id="e45e8-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="e45e8-237">Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e45e8-237">Office 365 Business</span></span>

<span data-ttu-id="e45e8-238">Office 365 Business Client, установленный на устройствах, автоматически начнет использовать функции Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="e45e8-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="e45e8-239">После миграции теперь можно использовать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="e45e8-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="e45e8-240">Активация корпоративных лицензий с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="e45e8-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="e45e8-241">Телеметрии приложений</span><span class="sxs-lookup"><span data-stu-id="e45e8-241">App telemetry</span></span>
 - <span data-ttu-id="e45e8-242">Обновление элементов управления</span><span class="sxs-lookup"><span data-stu-id="e45e8-242">Update controls</span></span>
 - <span data-ttu-id="e45e8-243">Сравнение и запрос электронной таблицы</span><span class="sxs-lookup"><span data-stu-id="e45e8-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="e45e8-244">Бизнес-аналитика</span><span class="sxs-lookup"><span data-stu-id="e45e8-244">Business intelligence</span></span>
