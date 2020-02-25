---
title: Выполнение внутреннего передачи управления администратора в Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Узнайте, как проверить, что ваша электронная почта и владение доменом могут принимать участие в неуправляемом клиенте в Office 365
ms.openlocfilehash: e3c89e122264808e2a8631c07269ea263c87fdaa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248101"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a><span data-ttu-id="37f36-103">Выполнение внутреннего передачи управления администратора в Office 365</span><span class="sxs-lookup"><span data-stu-id="37f36-103">Perform an internal admin takeover in Office 365</span></span>

 <span data-ttu-id="37f36-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="37f36-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="37f36-105">Если вы являетесь администратором и хотите принять участие в неуправляемом клиенте, созданном с помощью функции самостоятельной регистрации пользователей, это можно сделать с помощью внутреннего передачи управления администратора.</span><span class="sxs-lookup"><span data-stu-id="37f36-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="37f36-106">Самостоятельная регистрация любых облачных служб, использующих Azure AD, приведет к добавлению пользователя в неуправляемый каталог Azure AD, а также при создании неуправляемого клиента.</span><span class="sxs-lookup"><span data-stu-id="37f36-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="37f36-107">Неуправляемый клиент — это каталог без глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="37f36-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="37f36-108">Чтобы определить, является ли клиент управляемым или неуправляемым, ознакомьтесь со статьей [Определение типа клиента](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="37f36-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="37f36-109">Шаг 1: Проверка адреса электронной почты</span><span class="sxs-lookup"><span data-stu-id="37f36-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="37f36-110">Если в вашем клиенте включена самостоятельная служба, пользователи могут подписаться на бесплатные службы, например Power BI, самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="37f36-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="37f36-111">В этом разделе предполагается, что пользователь с собственной подпиской создал неуправляемый клиент, который вы хотите взять в качестве администратора. На первом этапе вы создаете пользовательский контекст в неуправляемом клиенте, используя Power BI, чтобы продемонстрировать путь к администратору передачи управления.</span><span class="sxs-lookup"><span data-stu-id="37f36-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="37f36-112">Чтобы зарегистрироваться в Power BI, перейдите на [сайт Power BI](https://powerbi.com) и выберите **начать бесплатную** > бесплатную**пробную версию** (в поле поделиться с Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="37f36-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="37f36-113">Подпишитесь с помощью учетной записи пользователя, использующей доменное имя организации `powerbiadmin@contoso.com`(например,).</span><span class="sxs-lookup"><span data-stu-id="37f36-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="37f36-114">Если ваша учетная запись уже используется, войдите в систему, используя текущий пароль.</span><span class="sxs-lookup"><span data-stu-id="37f36-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="37f36-115">Проверьте электронную почту на наличие **кода проверки** и введите код для проверки адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="37f36-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="37f36-116">Шаг 2: создание новой учетной записи</span><span class="sxs-lookup"><span data-stu-id="37f36-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="37f36-117">При вводе кода проверки на страницу будет выведена страница, на которой можно создать новую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="37f36-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="37f36-118">Введите в полях имя пользователя и пароль ту учетную запись, которую необходимо использовать, и нажмите кнопку **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="37f36-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="37f36-119">Шаг 3: Проверка владения доменом и станьте администратором</span><span class="sxs-lookup"><span data-stu-id="37f36-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="37f36-120">Откроется мастер **администрирования** .</span><span class="sxs-lookup"><span data-stu-id="37f36-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="37f36-121">Если мастер не запустится, найдите плитку **Администратор** и выберите ее.</span><span class="sxs-lookup"><span data-stu-id="37f36-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="37f36-122">Выберите **Да, я хочу быть администратором**.</span><span class="sxs-lookup"><span data-stu-id="37f36-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="37f36-123">Убедитесь, что вы владеете доменом, который вы хотите принять, добавив запись TXT в ваш регистратор доменных имен.</span><span class="sxs-lookup"><span data-stu-id="37f36-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="37f36-124">Мастер предоставит добавляемую запись TXT, а также ссылку на веб-сайт регистратора и ссылку на пошаговые инструкции.</span><span class="sxs-lookup"><span data-stu-id="37f36-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="37f36-125">После добавления записи TXT на сайт регистратора вернитесь к мастеру и нажмите кнопку **ОК, чтобы добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="37f36-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37f36-126">Получение поверх теневого клиента не влияет на существующие сведения или службы.</span><span class="sxs-lookup"><span data-stu-id="37f36-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="37f36-127">Тем не менее, если пользователи в домене подписаны на службы, для которых требуется лицензия, вам будет предложено купить лицензии для них в ходе принятия роли администратора.</span><span class="sxs-lookup"><span data-stu-id="37f36-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="37f36-128">Вы можете добавить или удалить лицензии после завершения процесса настройки администрирования.</span><span class="sxs-lookup"><span data-stu-id="37f36-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="37f36-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="37f36-129">Related articles</span></span>

<span data-ttu-id="37f36-130">YouTube: [получение прав администратора для управления учетной записью Power BI или Office 365 в три этапа](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="37f36-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="37f36-131">Передачи управления администратора в Azure AD</span><span class="sxs-lookup"><span data-stu-id="37f36-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="37f36-132">Получение справки по доменам Office 365</span><span class="sxs-lookup"><span data-stu-id="37f36-132">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="37f36-133">Использование функции самостоятельной регистрации в Организации</span><span class="sxs-lookup"><span data-stu-id="37f36-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="37f36-134">Общие сведения о роли администратора службы Power BI</span><span class="sxs-lookup"><span data-stu-id="37f36-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)
