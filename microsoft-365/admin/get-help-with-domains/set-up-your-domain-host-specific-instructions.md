---
title: Настройка домена (инструкции для конкретных узлов)
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
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Узнайте, как управлять собственными записями DNS или разрешать Office 365 управлять своими записями DNS.
ms.custom: okr_smb
ms.openlocfilehash: 2313aa6c629c76a852e38b4da9093576a3b75d6e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255082"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="90aa3-103">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="90aa3-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="90aa3-104">Чтобы приступить к работе с пользовательским доменом (contoso.com) с Office 365, необходимо проверить домен и настроить записи DNS вашего домена.</span><span class="sxs-lookup"><span data-stu-id="90aa3-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="90aa3-105">Вы можете добавлять DNS-записи и управлять ими с помощью средств администрирования на узле домена, а также предоставлять Office 365 управлять записями домена, а также настраивать их.</span><span class="sxs-lookup"><span data-stu-id="90aa3-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="90aa3-106">Выберите узел домена ниже, чтобы выполнить точные действия.</span><span class="sxs-lookup"><span data-stu-id="90aa3-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="90aa3-107">Если вы не знаете, что такое ваш узел, ознакомьтесь со статьей [Поиск регистратора доменных](find-your-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="90aa3-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="90aa3-108">Разрешите Office 365 управлять записями DNS</span><span class="sxs-lookup"><span data-stu-id="90aa3-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="90aa3-109">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="90aa3-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="90aa3-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="90aa3-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="90aa3-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="90aa3-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="90aa3-112">Домены Google</span><span class="sxs-lookup"><span data-stu-id="90aa3-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="90aa3-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="90aa3-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="90aa3-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="90aa3-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="90aa3-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="90aa3-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="90aa3-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="90aa3-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="90aa3-117">Или Узнайте, как [изменить серверов доменных имен, чтобы настроить Office 365 с помощью любого регистратора доменных](change-nameservers-at-any-domain-registrar.md)имен.</span><span class="sxs-lookup"><span data-stu-id="90aa3-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="90aa3-118">Управление собственными записями DNS</span><span class="sxs-lookup"><span data-stu-id="90aa3-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="90aa3-119">1&1 ИОНОС</span><span class="sxs-lookup"><span data-stu-id="90aa3-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="90aa3-120">Hover</span><span class="sxs-lookup"><span data-stu-id="90aa3-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="90aa3-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="90aa3-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="90aa3-122">Управляется Google (eNom Central)</span><span class="sxs-lookup"><span data-stu-id="90aa3-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="90aa3-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="90aa3-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="90aa3-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="90aa3-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="90aa3-125">Зоны DNS Azure</span><span class="sxs-lookup"><span data-stu-id="90aa3-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="90aa3-126">name.com</span><span class="sxs-lookup"><span data-stu-id="90aa3-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="90aa3-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="90aa3-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="90aa3-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="90aa3-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="90aa3-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="90aa3-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="90aa3-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="90aa3-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="90aa3-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="90aa3-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="90aa3-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="90aa3-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="90aa3-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="90aa3-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="90aa3-134">Сетевые решения</span><span class="sxs-lookup"><span data-stu-id="90aa3-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="90aa3-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="90aa3-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="90aa3-136">OVH</span><span class="sxs-lookup"><span data-stu-id="90aa3-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="90aa3-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="90aa3-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="90aa3-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="90aa3-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="90aa3-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="90aa3-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="90aa3-140">Register365 для Office 365</span><span class="sxs-lookup"><span data-stu-id="90aa3-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="90aa3-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="90aa3-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="90aa3-142">web.com</span><span class="sxs-lookup"><span data-stu-id="90aa3-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="90aa3-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="90aa3-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="90aa3-144">DNS-сервер под управлением Windows</span><span class="sxs-lookup"><span data-stu-id="90aa3-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="90aa3-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="90aa3-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="90aa3-146">Технологии</span><span class="sxs-lookup"><span data-stu-id="90aa3-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="90aa3-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="90aa3-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="90aa3-148">Yahoo!   Малый бизнес</span><span class="sxs-lookup"><span data-stu-id="90aa3-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="90aa3-149">Мне нужны общие инструкции, так как узел домена не включен в этот список.</span><span class="sxs-lookup"><span data-stu-id="90aa3-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   