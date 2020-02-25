---
title: Создание записей DNS для Office 365 на сайте 123-reg.co.uk
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
- BCS160
- MET150
- MOE150
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу 123-reg.co.uk для Office 365.
ms.openlocfilehash: acbc0f1c8a7eb7dcbe5f274d0f2c8b2c403e7de0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246881"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="b08ab-103">Создание записей DNS для Office 365 на сайте 123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="b08ab-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="b08ab-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b08ab-105">Если ваш поставщик услуг размещения DNS  123-reg.co.uk, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="b08ab-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b08ab-106">Когда вы добавите эти записи на сайте 123-reg.co.uk, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08ab-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b08ab-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="b08ab-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b08ab-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b08ab-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b08ab-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="b08ab-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b08ab-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b08ab-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b08ab-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="b08ab-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b08ab-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="b08ab-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b08ab-117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b08ab-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b08ab-118">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b08ab-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b08ab-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="b08ab-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b08ab-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="b08ab-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b08ab-121">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="b08ab-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b08ab-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b08ab-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b08ab-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b08ab-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b08ab-124">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-124">**Hostname**</span></span> <br/> |<span data-ttu-id="b08ab-125">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-125">**Type**</span></span> <br/> |<span data-ttu-id="b08ab-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="b08ab-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b08ab-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="b08ab-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="b08ab-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b08ab-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b08ab-129">**Примечание:** Это пример.</span><span class="sxs-lookup"><span data-stu-id="b08ab-129">**Note:** This is an example.</span></span> <span data-ttu-id="b08ab-130">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08ab-130">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="b08ab-131">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="b08ab-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="b08ab-132">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="b08ab-133">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b08ab-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b08ab-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="b08ab-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b08ab-135">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="b08ab-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b08ab-136">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="b08ab-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b08ab-137">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="b08ab-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b08ab-138">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b08ab-139">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b08ab-p106">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b08ab-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b08ab-143">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="b08ab-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b08ab-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b08ab-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b08ab-p107">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b08ab-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b08ab-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="b08ab-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b08ab-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="b08ab-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b08ab-149">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="b08ab-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b08ab-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b08ab-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b08ab-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b08ab-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b08ab-152">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-152">**Hostname**</span></span>|<span data-ttu-id="b08ab-153">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-153">**Type**</span></span>|<span data-ttu-id="b08ab-154">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-154">**Priority**</span></span>|<span data-ttu-id="b08ab-155">**Destination MX (Запись MX назначения)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b08ab-156">MX</span><span class="sxs-lookup"><span data-stu-id="b08ab-156">MX</span></span>  <br/> |<span data-ttu-id="b08ab-157">1,1</span><span class="sxs-lookup"><span data-stu-id="b08ab-157">1</span></span>  <br/> <span data-ttu-id="b08ab-158">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).   </span><span class="sxs-lookup"><span data-stu-id="b08ab-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="b08ab-159">*\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b08ab-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b08ab-161">**Примечание:** Получите ключ \<\> домена из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08ab-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="b08ab-162">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="b08ab-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Копирование и вставка значений из таблицы](../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="b08ab-164">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-164">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="b08ab-166">Если есть какие-либо другие записи MX, удалите каждую из них, щелкнув соответствующий значок с изображением **корзины**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Нажмите кнопку Удалить (значок корзины).](../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b08ab-168">Добавление шести записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b08ab-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b08ab-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b08ab-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b08ab-p109">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b08ab-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b08ab-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="b08ab-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b08ab-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="b08ab-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b08ab-174">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="b08ab-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b08ab-175">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b08ab-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b08ab-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b08ab-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b08ab-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b08ab-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b08ab-178">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-178">**Hostname**</span></span>|<span data-ttu-id="b08ab-179">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-179">**Type**</span></span>|<span data-ttu-id="b08ab-180">**Destination CNAME (Запись CNAME назначения)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b08ab-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b08ab-181">autodiscover</span></span>  <br/> |<span data-ttu-id="b08ab-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="b08ab-182">CNAME</span></span>  <br/> |<span data-ttu-id="b08ab-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b08ab-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b08ab-185">sip</span><span class="sxs-lookup"><span data-stu-id="b08ab-185">sip</span></span>  <br/> |<span data-ttu-id="b08ab-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="b08ab-186">CNAME</span></span>  <br/> |<span data-ttu-id="b08ab-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b08ab-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b08ab-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b08ab-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b08ab-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="b08ab-190">CNAME</span></span>  <br/> |<span data-ttu-id="b08ab-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b08ab-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b08ab-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b08ab-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b08ab-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="b08ab-194">CNAME</span></span>  <br/> |<span data-ttu-id="b08ab-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b08ab-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b08ab-196">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="b08ab-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b08ab-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b08ab-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b08ab-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="b08ab-198">CNAME</span></span>  <br/> |<span data-ttu-id="b08ab-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b08ab-200">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="b08ab-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="b08ab-202">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-202">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="b08ab-204">Добавьте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b08ab-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="b08ab-205">В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="b08ab-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="b08ab-206">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="b08ab-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b08ab-207">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="b08ab-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b08ab-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b08ab-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b08ab-209">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="b08ab-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b08ab-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="b08ab-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b08ab-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="b08ab-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="b08ab-212">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="b08ab-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b08ab-213">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="b08ab-213">Need examples?</span></span> <span data-ttu-id="b08ab-214">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="b08ab-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="b08ab-215">Проверить запись SPF можно с помощью одного из этих [специальных средств](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b08ab-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b08ab-216">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="b08ab-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="b08ab-217">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b08ab-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b08ab-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="b08ab-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b08ab-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="b08ab-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b08ab-220">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="b08ab-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b08ab-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b08ab-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b08ab-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b08ab-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b08ab-223">**Hostname (Имя узла)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-223">**Hostname**</span></span>|<span data-ttu-id="b08ab-224">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-224">**Type**</span></span>|<span data-ttu-id="b08ab-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="b08ab-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b08ab-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="b08ab-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="b08ab-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b08ab-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b08ab-228">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b08ab-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg — BP — configure – 4-1](../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="b08ab-230">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-230">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b08ab-232">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="b08ab-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b08ab-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b08ab-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b08ab-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте 123-reg.co.uk по [этой ссылке](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="b08ab-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b08ab-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="b08ab-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="b08ab-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="b08ab-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="b08ab-238">На странице " **Управление DNS** " перейдите на вкладку **Advanced DNS (дополнительно** ).</span><span class="sxs-lookup"><span data-stu-id="b08ab-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="b08ab-239">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="b08ab-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="b08ab-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b08ab-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b08ab-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b08ab-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b08ab-242">Hostname (Имя узла)</span><span class="sxs-lookup"><span data-stu-id="b08ab-242">Hostname</span></span>|<span data-ttu-id="b08ab-243">Type (Тип)</span><span class="sxs-lookup"><span data-stu-id="b08ab-243">Type</span></span>|<span data-ttu-id="b08ab-244">Priority (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="b08ab-244">Priority</span></span>|<span data-ttu-id="b08ab-245">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="b08ab-245">TTL</span></span>|<span data-ttu-id="b08ab-246">Destination SRV (Запись SRV назначения)</span><span class="sxs-lookup"><span data-stu-id="b08ab-246">Destination SRV</span></span>|
    |<span data-ttu-id="b08ab-247">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="b08ab-247">_sip._tls</span></span>|<span data-ttu-id="b08ab-248">SRV</span><span class="sxs-lookup"><span data-stu-id="b08ab-248">SRV</span></span>|<span data-ttu-id="b08ab-249">100</span><span class="sxs-lookup"><span data-stu-id="b08ab-249">100</span></span>|<span data-ttu-id="b08ab-250">3600</span><span class="sxs-lookup"><span data-stu-id="b08ab-250">3600</span></span>|<span data-ttu-id="b08ab-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="b08ab-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="b08ab-253">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b08ab-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="b08ab-254">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="b08ab-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="b08ab-255">SRV</span><span class="sxs-lookup"><span data-stu-id="b08ab-255">SRV</span></span>|<span data-ttu-id="b08ab-256">100</span><span class="sxs-lookup"><span data-stu-id="b08ab-256">100</span></span>|<span data-ttu-id="b08ab-257">3600</span><span class="sxs-lookup"><span data-stu-id="b08ab-257">3600</span></span>|<span data-ttu-id="b08ab-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b08ab-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="b08ab-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b08ab-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="b08ab-260">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="b08ab-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Скопируйте и вставьте значения из таблицы](../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="b08ab-262">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b08ab-262">Select **Add**.</span></span>
    
    ![Нажмите кнопку Добавить](../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="b08ab-264">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="b08ab-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="b08ab-265">В разделе **Advanced DNS (Расширенный DNS** ) создайте запись, используя значения из второй строки таблицы, а затем еще раз нажмите кнопку **Добавить** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="b08ab-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b08ab-p115">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b08ab-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  