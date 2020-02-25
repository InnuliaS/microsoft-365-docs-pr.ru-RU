---
title: Что поступает в показателях безопасности Майкрософт?
description: В этой статье описывается оценка безопасности Майкрософт в центре безопасности Майкрософт 365, вычисление сведений и возможные Администраторы безопасности.
keywords: безопасность, вредоносные программы, Microsoft 365, M365, Оценка безопасности, центр безопасности, действия по улучшению
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266989"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="f95ef-104">Что поступает в показателях безопасности Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="f95ef-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="f95ef-105">Чтобы сделать Microsoft Secure рейтинг более подходящим для вашей безопасности и улучшить удобство использования, мы будем вносить некоторые изменения в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="f95ef-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="f95ef-106">Ваш рейтинг и максимально возможный показатель будут меняться.</span><span class="sxs-lookup"><span data-stu-id="f95ef-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="f95ef-107">Однако это не подразумевает изменения в безопасности.</span><span class="sxs-lookup"><span data-stu-id="f95ef-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="f95ef-108">Чтобы узнать о последних изменениях, ознакомьтесь со статьей " [новые возможности оценки безопасности Майкрософт".](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="f95ef-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="f95ef-109">2 марта 2020</span><span class="sxs-lookup"><span data-stu-id="f95ef-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="f95ef-110">Удаление действий по улучшению из Intune</span><span class="sxs-lookup"><span data-stu-id="f95ef-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="f95ef-111">После оценки действий по улучшению оценки безопасности Майкрософт, предоставляемых Intune, было решено, что они не предоставляют удобного представления безопасности устройств в организациях.</span><span class="sxs-lookup"><span data-stu-id="f95ef-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="f95ef-112">Вместо того чтобы сосредоточиться на политиках, мы работаем над включением средств безопасности, которые напрямую оценивают состояние конфигурации устройств.</span><span class="sxs-lookup"><span data-stu-id="f95ef-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="f95ef-113">Будут удалены следующие действия по улучшению в Intune:</span><span class="sxs-lookup"><span data-stu-id="f95ef-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="f95ef-114">Включение управления мобильными устройствами Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f95ef-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="f95ef-115">Создание политики соответствия требованиям Microsoft Intune для Android</span><span class="sxs-lookup"><span data-stu-id="f95ef-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="f95ef-116">Создание политики соответствия Microsoft Intune для Android для работы</span><span class="sxs-lookup"><span data-stu-id="f95ef-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="f95ef-117">Создание политики защиты приложений Microsoft Intune для Android</span><span class="sxs-lookup"><span data-stu-id="f95ef-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="f95ef-118">Создание политики защиты приложений Microsoft Intune для iOS</span><span class="sxs-lookup"><span data-stu-id="f95ef-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="f95ef-119">Пометка устройств без политики соответствия требованиям Microsoft Intune, назначенных как несовместимые</span><span class="sxs-lookup"><span data-stu-id="f95ef-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="f95ef-120">Создание политики соответствия требованиям Microsoft Intune для iOS</span><span class="sxs-lookup"><span data-stu-id="f95ef-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="f95ef-121">Создание политики соответствия Microsoft Intune для macOS</span><span class="sxs-lookup"><span data-stu-id="f95ef-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="f95ef-122">Создание политики соответствия Microsoft Intune для Windows</span><span class="sxs-lookup"><span data-stu-id="f95ef-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="f95ef-123">Создание профиля конфигурации Microsoft Intune для Android</span><span class="sxs-lookup"><span data-stu-id="f95ef-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="f95ef-124">Создание профиля конфигурации Microsoft Intune для Android для работы</span><span class="sxs-lookup"><span data-stu-id="f95ef-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="f95ef-125">Создание профиля конфигурации Microsoft Intune для macOS</span><span class="sxs-lookup"><span data-stu-id="f95ef-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="f95ef-126">Создание профиля конфигурации Microsoft Intune для iOS</span><span class="sxs-lookup"><span data-stu-id="f95ef-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="f95ef-127">Создание профиля конфигурации Microsoft Intune для Windows</span><span class="sxs-lookup"><span data-stu-id="f95ef-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="f95ef-128">Включение обнаружения расширенных жаилбреак в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f95ef-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="f95ef-129">Требовать исправления всех устройств, включить поддержку вирусов и брандмауэров</span><span class="sxs-lookup"><span data-stu-id="f95ef-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="f95ef-130">Включение интеграции Windows Defender ATP в Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f95ef-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="f95ef-131">Создание политики Windows Information Protection для Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f95ef-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="f95ef-132">Все устройства должны иметь расширенные конфигурации безопасности</span><span class="sxs-lookup"><span data-stu-id="f95ef-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="f95ef-133">Просмотреть отчет о заблокированных устройствах еженедельно</span><span class="sxs-lookup"><span data-stu-id="f95ef-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="f95ef-134">Удаление действий улучшения, которые не отвечают ожиданиям для надежного измерения</span><span class="sxs-lookup"><span data-stu-id="f95ef-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="f95ef-135">Чтобы обеспечить осмысленность оценки безопасности Майкрософт и обеспечить надежность и надежность каждого действия по улучшению, мы удаляем следующие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="f95ef-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="f95ef-136">Включение записи данных аудита</span><span class="sxs-lookup"><span data-stu-id="f95ef-136">Turn on audit data recording</span></span>
- <span data-ttu-id="f95ef-137">Обнаружение рискованных и несоответствующих теневых ИТ приложений</span><span class="sxs-lookup"><span data-stu-id="f95ef-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="f95ef-138">Просмотр разрешений & блокировать рискованные приложения OAuth, подключенные к среде</span><span class="sxs-lookup"><span data-stu-id="f95ef-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="f95ef-139">Настройка управления версиями в библиотеках документов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f95ef-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="f95ef-140">Обновления действий по улучшению MFA</span><span class="sxs-lookup"><span data-stu-id="f95ef-140">MFA improvement action updates</span></span>

<span data-ttu-id="f95ef-141">Чтобы отразить необходимость использования бизнес-процессов для обеспечения максимальной безопасности при применении политик, работающих с бизнесом, Microsoft Security Score удаляет три действия по улучшению, ориентированные на многофакторную проверку подлинности, и добавляя два.</span><span class="sxs-lookup"><span data-stu-id="f95ef-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="f95ef-142">Удаляются три из них:</span><span class="sxs-lookup"><span data-stu-id="f95ef-142">The three that will be removed:</span></span>

- <span data-ttu-id="f95ef-143">Регистрация всех пользователей для многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f95ef-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="f95ef-144">Требовать указания MFA для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="f95ef-144">Require MFA for all users</span></span>
- <span data-ttu-id="f95ef-145">Запрос MFA для привилегированных ролей Azure AD</span><span class="sxs-lookup"><span data-stu-id="f95ef-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="f95ef-146">Добавлены новые действия по улучшению:</span><span class="sxs-lookup"><span data-stu-id="f95ef-146">New improvement actions added:</span></span>

- <span data-ttu-id="f95ef-147">Убедитесь, что все пользователи могут выполнять многофакторную проверку подлинности для безопасного доступа</span><span class="sxs-lookup"><span data-stu-id="f95ef-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="f95ef-148">Требовать использование MFA для административных ролей</span><span class="sxs-lookup"><span data-stu-id="f95ef-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="f95ef-149">Для этих новых действий по улучшению потребуется зарегистрировать пользователей или администраторов для многофакторной проверки подлинности (MFA) в вашем каталоге и установить правильный набор политик, соответствующих потребностям Организации.</span><span class="sxs-lookup"><span data-stu-id="f95ef-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="f95ef-150">Основной целью является гибкость, при которой все пользователи и администраторы могут выполнять проверку подлинности с использованием нескольких факторов или запросов на проверку подлинности на основе риска.</span><span class="sxs-lookup"><span data-stu-id="f95ef-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="f95ef-151">Это может занять форму с несколькими политиками, которые применяют решения с областью или по умолчанию (ожидается в 16 марта), которые позволяют корпорации Майкрософт решить, когда следует выдавать пользователям запрос на получение MFA.</span><span class="sxs-lookup"><span data-stu-id="f95ef-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="f95ef-152">Удаление действий по улучшению "Рецензирование"</span><span class="sxs-lookup"><span data-stu-id="f95ef-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="f95ef-153">Один из принципов безопасности оценки состоит в том, что показатель должен быть стандартизованным и легко связанным.</span><span class="sxs-lookup"><span data-stu-id="f95ef-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="f95ef-154">Наличие неизмеримых действий по улучшению или действий, которые приводят к возникновению путаницы.</span><span class="sxs-lookup"><span data-stu-id="f95ef-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="f95ef-155">Один показатель безопасности Майкрософт имеет смысл только в том случае, если каждая рекомендация может иметь четкое оформление оценки.</span><span class="sxs-lookup"><span data-stu-id="f95ef-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="f95ef-156">Проверка действий по улучшению не производится до тех же стандартных действий, что и другие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="f95ef-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="f95ef-157">По этим причинам все действия по улучшению, требующие ритмичности проверки, будут временно удалены.</span><span class="sxs-lookup"><span data-stu-id="f95ef-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="f95ef-158">В вашей части действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="f95ef-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="f95ef-159">16 марта 2020</span><span class="sxs-lookup"><span data-stu-id="f95ef-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="f95ef-160">Удаление действий улучшения, которые не отвечают ожиданиям для надежного измерения</span><span class="sxs-lookup"><span data-stu-id="f95ef-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="f95ef-161">Чтобы обеспечить осмысленность оценки безопасности Майкрософт и обеспечить надежность и надежность каждого действия по улучшению, мы удаляем следующие действия по улучшению.</span><span class="sxs-lookup"><span data-stu-id="f95ef-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="f95ef-162">Хранение документов пользователей в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f95ef-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="f95ef-163">Настройка политик безопасных вложений Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f95ef-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="f95ef-164">Настройка безопасных ссылок на Office 365 для проверки URL-адресов</span><span class="sxs-lookup"><span data-stu-id="f95ef-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="f95ef-165">Не разрешать делегирование почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="f95ef-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="f95ef-166">Разрешить ссылки анонимного общего доступа к гостям для сайтов и документов</span><span class="sxs-lookup"><span data-stu-id="f95ef-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="f95ef-167">Поддержка параметров безопасности по умолчанию для действий по улучшению Azure AD</span><span class="sxs-lookup"><span data-stu-id="f95ef-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="f95ef-168">Оценка безопасности Майкрософт будет обновлять действия по улучшению для поддержки параметров [безопасности по умолчанию в Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), что облегчит защиту Организации с помощью предварительно настроенных параметров безопасности для распространенных атак.</span><span class="sxs-lookup"><span data-stu-id="f95ef-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="f95ef-169">Он повлияет на следующие действия по улучшению:</span><span class="sxs-lookup"><span data-stu-id="f95ef-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="f95ef-170">Убедитесь, что все пользователи могут выполнять многофакторную проверку подлинности для безопасного доступа</span><span class="sxs-lookup"><span data-stu-id="f95ef-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="f95ef-171">Требовать использование MFA для административных ролей</span><span class="sxs-lookup"><span data-stu-id="f95ef-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="f95ef-172">Включение политики для блокирования устаревшей проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f95ef-172">Enable policy to block legacy authentication</span></span>