---
title: Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам с предварительными требованиями для облачной проверки подлинности.
ms.openlocfilehash: 9721d2972990998ca345f1d48d96494096f9190e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072569"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="759c7-103">Предварительные требования к удостоверениям и доступу к устройствам для облачного применения в тестовой среде Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="759c7-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="759c7-104">[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор настроек и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="759c7-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="759c7-105">В этой статье описано, как настроить тестовую среду Microsoft 365, соответствующую требованиям [предварительной настройки облачной среды](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="759c7-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="759c7-106">Настройка этой тестовой среды состоит из семи следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="759c7-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="759c7-107">Создание простой тестовой среды</span><span class="sxs-lookup"><span data-stu-id="759c7-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="759c7-108">Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="759c7-108">Configure named locations</span></span>
3.  <span data-ttu-id="759c7-109">Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="759c7-109">Configure password writeback</span></span>
4.  <span data-ttu-id="759c7-110">Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="759c7-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="759c7-111">Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="759c7-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="759c7-112">Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="759c7-112">Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="759c7-113">Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="759c7-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="759c7-114">Этап 1. Создание упрощенной тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="759c7-114">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="759c7-115">Следуйте инструкциям в статье [Простая базовая конфигурация](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="759c7-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="759c7-116">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="759c7-116">Here is the resulting configuration.</span></span>

![Простая среда тестирования Microsoft 365 корпоративный](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="759c7-118">Этап 2. Настройка именованных расположений</span><span class="sxs-lookup"><span data-stu-id="759c7-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="759c7-119">Сначала определите общедоступные IP-адреса или диапазоны адресов, используемые в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="759c7-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="759c7-120">Затем выполните инструкции из статьи [Настройка именованных расположений в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) для добавления адресов или диапазонов адресов в качестве именованных расположений.</span><span class="sxs-lookup"><span data-stu-id="759c7-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="759c7-121">Этап 3. Настройка компонента обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="759c7-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="759c7-122">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="759c7-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="759c7-123">Этап 4. Настройка самостоятельного сброса пароля</span><span class="sxs-lookup"><span data-stu-id="759c7-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="759c7-124">Выполните инструкции [этапа 3 руководства по лаборатории тестирования для сброса пароля](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="759c7-124">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="759c7-125">При включении сброса пароля для учетных записей в определенной группе Azure AD добавьте эти учетные записи в группу **Сброс пароля**:</span><span class="sxs-lookup"><span data-stu-id="759c7-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="759c7-126">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="759c7-126">User: %2</span></span>
- <span data-ttu-id="759c7-127">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="759c7-127">User Defined 3</span></span>
- <span data-ttu-id="759c7-128">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="759c7-128">User: %4</span></span>
- <span data-ttu-id="759c7-129">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="759c7-129">User 5</span></span>

<span data-ttu-id="759c7-130">Проверьте сброс паролей только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="759c7-130">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="759c7-131">Этап 5. Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="759c7-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="759c7-132">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для многофакторной проверки подлинности](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) для следующих учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="759c7-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="759c7-133">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="759c7-133">User: %2</span></span>
- <span data-ttu-id="759c7-134">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="759c7-134">User Defined 3</span></span>
- <span data-ttu-id="759c7-135">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="759c7-135">User: %4</span></span>
- <span data-ttu-id="759c7-136">Пользователь 5</span><span class="sxs-lookup"><span data-stu-id="759c7-136">User 5</span></span>

<span data-ttu-id="759c7-137">Протестируйте многофакторную проверку подлинности только для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="759c7-137">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="759c7-138">Этап 6. Включение защиты идентификации Azure AD</span><span class="sxs-lookup"><span data-stu-id="759c7-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="759c7-139">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для защиты идентификации Azure AD](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="759c7-139">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="759c7-140">Этап 7. Включение современной проверки подлинности для Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="759c7-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="759c7-141">Для Exchange Online выполните [эти инструкции](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="759c7-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="759c7-142">Для Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="759c7-142">Skype for Business Online</span></span>

1. <span data-ttu-id="759c7-143">Подключитесь к [Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="759c7-143">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="759c7-144">Выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="759c7-144">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="759c7-145">Проверьте успешность изменения с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="759c7-145">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="759c7-146">Результатом является тестовая среда, соответствующая требованиям [предварительной настройки облачной среды](identity-access-prerequisites.md#prerequisites) для удостоверений и доступа к устройствам.</span><span class="sxs-lookup"><span data-stu-id="759c7-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="759c7-147">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="759c7-147">Next step</span></span>

<span data-ttu-id="759c7-148">См. статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и защитить удостоверения и устройства.</span><span class="sxs-lookup"><span data-stu-id="759c7-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="759c7-149">См. также</span><span class="sxs-lookup"><span data-stu-id="759c7-149">See also</span></span>

[<span data-ttu-id="759c7-150">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="759c7-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="759c7-151">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="759c7-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="759c7-152">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="759c7-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="759c7-153">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="759c7-153">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="759c7-154">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="759c7-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)