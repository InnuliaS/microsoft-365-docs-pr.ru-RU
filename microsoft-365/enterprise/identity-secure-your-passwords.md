---
title: Шаг 2. Защита паролей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Необходимо обеспечить надежность и управляемость ваших паролей в масштабах организации.
ms.openlocfilehash: 06d936a68432b55912b1c10839336dc94e698f51
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090810"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="59700-103">Шаг 2. Защита паролей</span><span class="sxs-lookup"><span data-stu-id="59700-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="59700-104">Запрет слабых паролей</span><span class="sxs-lookup"><span data-stu-id="59700-104">Prevent bad passwords</span></span>

<span data-ttu-id="59700-105">*Это необязательная процедура, применимая к версиям Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="59700-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59700-106">Все пользователи должны использовать [Руководство по паролям корпорации Майкрософт](https://www.microsoft.com/research/publication/password-guidance/) для создания своих паролей учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="59700-106">All you users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="59700-107">Чтобы запретить пользователям создавать легко подбираемые пароли, применяйте службу защиты паролей Azure AD, в которой используется как глобальный список запрещенных паролей, так и необязательный настраиваемый список запрещенных паролей, указываемый вами.</span><span class="sxs-lookup"><span data-stu-id="59700-107">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="59700-108">Например, вы можете указать следующие термины, относящиеся к вашей организации:</span><span class="sxs-lookup"><span data-stu-id="59700-108">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="59700-109">Фирменные названия</span><span class="sxs-lookup"><span data-stu-id="59700-109">Brand names</span></span>
- <span data-ttu-id="59700-110">Названия продуктов</span><span class="sxs-lookup"><span data-stu-id="59700-110">Product names</span></span>
- <span data-ttu-id="59700-111">Расположения (например, штаб-квартира компании)</span><span class="sxs-lookup"><span data-stu-id="59700-111">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="59700-112">Внутренние термины, относящиеся к компании</span><span class="sxs-lookup"><span data-stu-id="59700-112">Company-specific internal terms</span></span>
- <span data-ttu-id="59700-113">Сокращения с определенным значением в компании</span><span class="sxs-lookup"><span data-stu-id="59700-113">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="59700-114">Вы можете запретить слабые пароли в [облачной среде](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) и [локальных доменных службах Active Directory (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="59700-114">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="59700-115">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-password-prot).</span><span class="sxs-lookup"><span data-stu-id="59700-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="59700-116">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="59700-116">Simplify password resets</span></span>

<span data-ttu-id="59700-117">*Это необязательная процедура, применимая к наборам Microsoft 365 корпоративный E3 и E5*</span><span class="sxs-lookup"><span data-stu-id="59700-117">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59700-118">В этом разделе описывается включение самостоятельного сброса паролей (SSPR), позволяющего пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="59700-118">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="59700-119">Чтобы получать оповещения о неправильном или несанкционированном использовании, можно использовать подробные отчеты, которые позволяют отслеживать доступ пользователей к системе, а также уведомления.</span><span class="sxs-lookup"><span data-stu-id="59700-119">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="59700-120">Прежде чем развертывать функцию сброса паролей необходимо включить обратную запись паролей.</span><span class="sxs-lookup"><span data-stu-id="59700-120">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="59700-121">См. [инструкции по развертыванию функции сброса паролей](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="59700-121">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="59700-123">Руководство по лаборатории тестирования: сброс пароля</span><span class="sxs-lookup"><span data-stu-id="59700-123">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="59700-124">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-pw-reset).</span><span class="sxs-lookup"><span data-stu-id="59700-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="59700-125">Упрощение входа пользователей</span><span class="sxs-lookup"><span data-stu-id="59700-125">Simplify user sign-in</span></span>

<span data-ttu-id="59700-126">*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="59700-126">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59700-127">В этом разделе описывается настройка эффективного единого входа в Azure Active Directory в сочетании с синхронизацией хэша паролей (PHS) и сквозной проверкой подлинности (PTA), чтобы разрешить пользователям входить в службы, использующие учетные записи пользователей Azure AD, не вводя свои пароли и (во многих случаях) имена пользователей.</span><span class="sxs-lookup"><span data-stu-id="59700-127">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="59700-128">Это упрощает доступ пользователей к облачным приложениям, например Office 365, без необходимости в дополнительных локальных компонентах, таких как серверы федерации удостоверений.</span><span class="sxs-lookup"><span data-stu-id="59700-128">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="59700-129">Вы настроите простой единый вход для Azure AD с помощью средства Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="59700-129">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="59700-130">См. [инструкции по настройке простого единого входа для Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="59700-130">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Руководства для лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="59700-132">Руководство по лаборатории тестирования: простой единый вход Azure AD</span><span class="sxs-lookup"><span data-stu-id="59700-132">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="59700-133">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-sso).</span><span class="sxs-lookup"><span data-stu-id="59700-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="59700-134">Настройка страницы входа в Office 365</span><span class="sxs-lookup"><span data-stu-id="59700-134">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="59700-135">*Этот шаг не является обязательным. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="59700-135">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="59700-136">В этом разделе описывается, как помочь пользователям узнавать страницу входа в систему вашей организации, добавив на нее название и логотип компании, а также другие отличительные элементы.</span><span class="sxs-lookup"><span data-stu-id="59700-136">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="59700-137">С помощью Microsoft 365 корпоративный вы можете настроить внешний вид страницы входа и страниц Панели доступа так, чтобы на них отображались логотип вашей компании, цветовые схемы и настраиваемая пользовательская информация.</span><span class="sxs-lookup"><span data-stu-id="59700-137">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="59700-138">Дополнительные сведения см. в статье [Добавление фирменной символики компании на страницу входа в Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="59700-138">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="59700-139">Инструкции по настройке см. в статье [Краткое руководство по добавлению фирменной символики организации на страницу входа в Azure Active Directory](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="59700-139">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="59700-140">Промежуточной контрольной точкой в данном разделе служат [критерии завершения](identity-exit-criteria.md#crit-identity-custom-sign-in).</span><span class="sxs-lookup"><span data-stu-id="59700-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="59700-141">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="59700-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="59700-142">Защита пользовательских входов и управление ими</span><span class="sxs-lookup"><span data-stu-id="59700-142">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |