---
title: Создание записей DNS для Office 365 в easyDNS
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу easyDNS для Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255370"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a><span data-ttu-id="7bfa0-103">Создание записей DNS для Office 365 в easyDNS</span><span class="sxs-lookup"><span data-stu-id="7bfa0-103">Create DNS records at easyDNS for Office 365</span></span>

<span data-ttu-id="7bfa0-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7bfa0-105">Вам потребуется добавить все указанные ниже записи DNS на веб-сайте регистратора для маршрутизации почты в Office 365, использовать домен для Teams и Skype для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="7bfa0-106">NOTE: записи SRV в настоящее время недоступны в пакетах службы easyDNS.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="7bfa0-107">Для добавления записей SRV, необходимых для Office 365 Skype для бизнеса, вам может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="7bfa0-108">Проверка принадлежности домена к записи TXT</span><span class="sxs-lookup"><span data-stu-id="7bfa0-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="7bfa0-109">Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7bfa0-110">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7bfa0-111">В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7bfa0-112">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="7bfa0-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7bfa0-113">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-113">**Host**</span></span>|<span data-ttu-id="7bfa0-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7bfa0-115">MS = Мскскскскскскскскс (используйте значение, указанное на странице "домены центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="7bfa0-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="7bfa0-116">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7bfa0-117">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="7bfa0-118">Подождите несколько минут, прежде чем продолжить, чтобы созданная запись могла быть передана через Интернет и обнаружена в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.</span></span>
    
8. <span data-ttu-id="7bfa0-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-119">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
    
9. <span data-ttu-id="7bfa0-120">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="7bfa0-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="7bfa0-121">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="7bfa0-122">На странице **Настройка** выберите пункт **Запуск программы установки.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="7bfa0-123">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a><span data-ttu-id="7bfa0-124">Добавление записи MX для маршрутизации электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="7bfa0-124">Add an MX record to route email to Office 365</span></span>

1. <span data-ttu-id="7bfa0-125">Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7bfa0-126">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7bfa0-127">В заголовке **MX Record (запись MX** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7bfa0-128">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="7bfa0-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7bfa0-129">**ПОЧТА ДЛЯ ЗОНЫ**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="7bfa0-130">**ПОЧТОВЫЙ СЕРВЕР**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-130">**MAIL SERVER**</span></span>|<span data-ttu-id="7bfa0-131">**преф**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7bfa0-132">\<Domain-key\>. mail.Protection.Outlook.com (получение значения \<ключа\> домена из страницы "домены центра администрирования")</span><span class="sxs-lookup"><span data-stu-id="7bfa0-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="7bfa0-133">нуль</span><span class="sxs-lookup"><span data-stu-id="7bfa0-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="7bfa0-134">Если вы хотите сохранить другие записи MX для целей резервного копирования, скопируйте их в любое место.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="7bfa0-135">Перед перемещением удалите все остальные записи MX здесь.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="7bfa0-136">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7bfa0-137">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="7bfa0-138">Добавление необходимых записей CNAME</span><span class="sxs-lookup"><span data-stu-id="7bfa0-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="7bfa0-139">Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7bfa0-140">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7bfa0-141">В разделе **записи CNAME/Alias** нажмите кнопку Изменить (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7bfa0-142">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="7bfa0-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="7bfa0-143">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-143">**HOST**</span></span>|<span data-ttu-id="7bfa0-144">**Address (должен заканчиваться на ".")**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="7bfa0-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7bfa0-145">autodiscover</span></span>  <br/> |<span data-ttu-id="7bfa0-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="7bfa0-147">sip</span><span class="sxs-lookup"><span data-stu-id="7bfa0-147">sip</span></span>  <br/> |<span data-ttu-id="7bfa0-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7bfa0-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7bfa0-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7bfa0-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="7bfa0-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7bfa0-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7bfa0-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="7bfa0-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7bfa0-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7bfa0-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="7bfa0-155">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7bfa0-156">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7bfa0-157">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="7bfa0-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="7bfa0-158">Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7bfa0-159">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7bfa0-160">В разделе **txt Records (записи TXT** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7bfa0-161">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="7bfa0-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7bfa0-162">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-162">**Host**</span></span>|<span data-ttu-id="7bfa0-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="7bfa0-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7bfa0-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="7bfa0-165">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7bfa0-166">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7bfa0-167">Добавьте две записи SRV, необходимые для Office 365</span><span class="sxs-lookup"><span data-stu-id="7bfa0-167">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="7bfa0-168">NOTE: записи SRV в настоящее время недоступны в easyDNS "домен и служба".</span><span class="sxs-lookup"><span data-stu-id="7bfa0-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="7bfa0-169">Для добавления записей SRV может потребоваться выполнить обновление до более высокого уровня обслуживания с easyDNS</span><span class="sxs-lookup"><span data-stu-id="7bfa0-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="7bfa0-170">Перейдите на [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) страницу и войдите с помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="7bfa0-171">В заголовке **все домены** выберите **DNS.**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="7bfa0-172">В разделе **SRV Records (записи SRV** ) нажмите кнопку Edit (значок вренч).</span><span class="sxs-lookup"><span data-stu-id="7bfa0-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="7bfa0-173">Введите в текстовые поля следующие записи:</span><span class="sxs-lookup"><span data-stu-id="7bfa0-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="7bfa0-174">**SERVICE (СЛУЖБА)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-174">**SERVICE**</span></span>|<span data-ttu-id="7bfa0-175">**ЗАДАННОЕ**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-175">**PROTO**</span></span>|<span data-ttu-id="7bfa0-176">**HOST (УЗЕЛ)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-176">**HOST**</span></span>|<span data-ttu-id="7bfa0-177">**ОСНОВНОЙ**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-177">**PRI**</span></span>|<span data-ttu-id="7bfa0-178">**вгт**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-178">**WGT**</span></span>|<span data-ttu-id="7bfa0-179">**PORT (ПОРТ)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-179">**PORT**</span></span>|<span data-ttu-id="7bfa0-180">**TARGET (должно оканчиваться на ".")**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="7bfa0-181">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="7bfa0-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7bfa0-182">_sip</span><span class="sxs-lookup"><span data-stu-id="7bfa0-182">_sip</span></span>  <br/> |<span data-ttu-id="7bfa0-183">TLS</span><span class="sxs-lookup"><span data-stu-id="7bfa0-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="7bfa0-184">100</span><span class="sxs-lookup"><span data-stu-id="7bfa0-184">100</span></span>  <br/> |<span data-ttu-id="7bfa0-185">1,1</span><span class="sxs-lookup"><span data-stu-id="7bfa0-185">1</span></span>  <br/> |<span data-ttu-id="7bfa0-186">443</span><span class="sxs-lookup"><span data-stu-id="7bfa0-186">443</span></span>  <br/> |<span data-ttu-id="7bfa0-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7bfa0-188">1800</span><span class="sxs-lookup"><span data-stu-id="7bfa0-188">1800</span></span>  <br/> |
    |<span data-ttu-id="7bfa0-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7bfa0-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="7bfa0-190">TCP</span><span class="sxs-lookup"><span data-stu-id="7bfa0-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="7bfa0-191">100</span><span class="sxs-lookup"><span data-stu-id="7bfa0-191">100</span></span>  <br/> |<span data-ttu-id="7bfa0-192">1,1</span><span class="sxs-lookup"><span data-stu-id="7bfa0-192">1</span></span>  <br/> |<span data-ttu-id="7bfa0-193">5061</span><span class="sxs-lookup"><span data-stu-id="7bfa0-193">5061</span></span>  <br/> |<span data-ttu-id="7bfa0-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="7bfa0-195">1800</span><span class="sxs-lookup"><span data-stu-id="7bfa0-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="7bfa0-196">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="7bfa0-197">Убедитесь, что запись верна, а затем нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="7bfa0-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
