---
title: Сбор необходимых сведений для создания DNS-записей Office 365
f1.keywords:
- NOCSH
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Сведения о том, как найти значения и сведения, необходимые для создания записей DNS для Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255087"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="98cc0-103">Сбор необходимых сведений для создания DNS-записей Office 365</span><span class="sxs-lookup"><span data-stu-id="98cc0-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="98cc0-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="98cc0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="98cc0-105">Шаг 1: Найдите значение записи TXT и проверьте</span><span class="sxs-lookup"><span data-stu-id="98cc0-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="98cc0-106">В центре администрирования Microsoft 365 перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **установки** \> ".</span><span class="sxs-lookup"><span data-stu-id="98cc0-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="98cc0-107">Если вы используете Office 365 в Германии, перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> .</span><span class="sxs-lookup"><span data-stu-id="98cc0-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="98cc0-108">Если вы используете Office 365 под управлением 21Vianet, перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> .</span><span class="sxs-lookup"><span data-stu-id="98cc0-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="98cc0-109">На странице **домены** выберите свой домен, а затем нажмите кнопку **запустить программу установки**.</span><span class="sxs-lookup"><span data-stu-id="98cc0-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="98cc0-110">Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="98cc0-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="98cc0-111">На странице **Проверка домена** выберите **Добавить запись типа TXT**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="98cc0-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="98cc0-112">Скопируйте отображаемое **значение txt** .</span><span class="sxs-lookup"><span data-stu-id="98cc0-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="98cc0-113">Он выглядит следующим образом: **MS = мскскскскскскскскс**.</span><span class="sxs-lookup"><span data-stu-id="98cc0-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="98cc0-114">Перейдите к разделу [Создание записей DNS для любого поставщика услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md)и выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции.</span><span class="sxs-lookup"><span data-stu-id="98cc0-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="98cc0-115">Выполните действия, чтобы создать запись TXT (или MX) на своем узле DNS, а затем проверьте домен в Office 365.</span><span class="sxs-lookup"><span data-stu-id="98cc0-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="98cc0-116">Удалите запись TXT (или запись MX) с узла DNS, когда домен будет проверен в Office 365.</span><span class="sxs-lookup"><span data-stu-id="98cc0-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="98cc0-117">Шаг 2: поиск значения записи MX для электронной почты и т. д.</span><span class="sxs-lookup"><span data-stu-id="98cc0-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="98cc0-118">В центре администрирования Microsoft 365 перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **установки** \> ".</span><span class="sxs-lookup"><span data-stu-id="98cc0-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="98cc0-119">Если вы используете Office 365 в Германии, перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">домены</a> .</span><span class="sxs-lookup"><span data-stu-id="98cc0-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="98cc0-120">Если вы используете Office 365 под управлением 21Vianet, перейдите на страницу эти <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">домены</a> .</span><span class="sxs-lookup"><span data-stu-id="98cc0-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="98cc0-121">На странице **Домены** щелкните свой домен.</span><span class="sxs-lookup"><span data-stu-id="98cc0-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="98cc0-122">В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="98cc0-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="98cc0-123">Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.</span><span class="sxs-lookup"><span data-stu-id="98cc0-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="98cc0-124">То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.</span><span class="sxs-lookup"><span data-stu-id="98cc0-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="98cc0-125">Перейдите к разделу [Создание DNS-записей на любом поставщике услуг размещения DNS](create-dns-records-at-any-dns-hosting-provider.md), а затем выберите узел DNS из списка регистраторов, чтобы просмотреть пошаговые инструкции по добавлению записей на веб-сайте узла DNS.</span><span class="sxs-lookup"><span data-stu-id="98cc0-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="98cc0-126">Следуйте указаниям, чтобы создать записи в своем узле DNS.</span><span class="sxs-lookup"><span data-stu-id="98cc0-126">Follow the steps for creating the records at your DNS host.</span></span>