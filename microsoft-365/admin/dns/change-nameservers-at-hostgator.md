---
title: Изменение серверов доменных имен для настройки Office 365 у регистратора Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Узнайте, как настроить Office 365 для управления записями DNS в пользовательском домене по адресу Hostgator.
ms.openlocfilehash: f0d3b495285685c3f666560816f99b07a1a5f6d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246668"
---
# <a name="change-nameservers-to-set-up-office-365-with-hostgator"></a><span data-ttu-id="68038-103">Изменение серверов доменных имен для настройки Office 365 у регистратора Hostgator</span><span class="sxs-lookup"><span data-stu-id="68038-103">Change nameservers to set up Office 365 with Hostgator</span></span>

 <span data-ttu-id="68038-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="68038-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="68038-p101">Следуйте этим инструкциям, если хотите передать управление своими записями DNS для Office 365 в Office 365. (При желании вы можете [управлять всеми своими записями DNS для Office 365 на сайте Hostgator](create-dns-records-at-hostgator.md).)</span><span class="sxs-lookup"><span data-stu-id="68038-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="68038-107">Настройка домена таким образом, чтобы он указывал на учетную запись размещения.</span><span class="sxs-lookup"><span data-stu-id="68038-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68038-108">Эту процедуру необходимо выполнить раньше процедуры **Добавление записи TXT для проверки**, описанной в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="68038-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="68038-109">Чтобы связать свой домен с учетными записями размещения, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="68038-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="68038-p102">Прежде всего перейдите по [этой ссылке](https://portal.hostgator.com/domain/manage), чтобы открыть свою страницу на клиентском портале Hostgator, а затем выполните вход.</span><span class="sxs-lookup"><span data-stu-id="68038-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="68038-113">Перейдите на вкладку **домены** .</span><span class="sxs-lookup"><span data-stu-id="68038-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="68038-115">На странице " **Управление доменами** " в разделе **My Domains (мои домены** ) выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="68038-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="68038-117">На странице " **Обзор доменов** " в области **серверы имен** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="68038-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="68038-119">На странице **серверы имен** для вашего домена в раскрывающемся списке **Выбор учетной записи размещения** выберите **учетную запись размещения** , связанную с доменом.</span><span class="sxs-lookup"><span data-stu-id="68038-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="68038-121">Выберите команду **сохранить серверы имен**.</span><span class="sxs-lookup"><span data-stu-id="68038-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="68038-123">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="68038-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68038-124">Перед выполнением этой процедуры необходимо сначала выполнить процедуру, описанную в первом разделе этой статьи, и [указать доменную учетную запись.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="68038-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="68038-p103">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="68038-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68038-p104">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="68038-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="68038-p105">Чтобы приступить к работе, перейдите на свою страницу cPanel на сайте Hostgator. Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="68038-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="68038-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span><span class="sxs-lookup"><span data-stu-id="68038-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="68038-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="68038-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="68038-135">Чтобы приступить к работе с Office 365, можно приобрести учетную запись хостинга из Hostgator или [изменить записи сервера доменных имен (NS)](#change-your-domains-nameserver-ns-records) , чтобы они ссылались на Office 365.</span><span class="sxs-lookup"><span data-stu-id="68038-135">To get started with Office 365, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Office 365.</span></span> 
  
2. <span data-ttu-id="68038-136">На странице " **Панель управления** " в разделе **домены** выберите **Расширенный редактор зоны DNS**.</span><span class="sxs-lookup"><span data-stu-id="68038-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="68038-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="68038-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="68038-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="68038-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="68038-139">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="68038-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="68038-140">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="68038-140">**Name**</span></span> <br/> |<span data-ttu-id="68038-141">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="68038-141">**TTL**</span></span> <br/> |<span data-ttu-id="68038-142">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="68038-142">**Type**</span></span> <br/> |<span data-ttu-id="68038-143">**TXT Data (Данные TXT)**</span><span class="sxs-lookup"><span data-stu-id="68038-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="68038-p108">Используйте свое  *доменное имя*  , например fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="68038-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="68038-146">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="68038-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="68038-147">1,1</span><span class="sxs-lookup"><span data-stu-id="68038-147">1</span></span>  <br/> |<span data-ttu-id="68038-148">TXT</span><span class="sxs-lookup"><span data-stu-id="68038-148">TXT</span></span>  <br/> |<span data-ttu-id="68038-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="68038-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="68038-150">**Примечание:** Это пример.</span><span class="sxs-lookup"><span data-stu-id="68038-150">**Note:** This is an example.</span></span> <span data-ttu-id="68038-151">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="68038-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="68038-152">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="68038-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="68038-153">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="68038-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="68038-154">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="68038-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="68038-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="68038-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="68038-156">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="68038-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="68038-157">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="68038-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="68038-158">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="68038-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="68038-159">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="68038-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="68038-160">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="68038-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68038-p110">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="68038-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="68038-164">Изменение записей сервера доменных имен</span><span class="sxs-lookup"><span data-stu-id="68038-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="68038-p111">Чтобы завершить настройку домена для использования в Office 365, измените для него записи серверов имен на сайте вашего регистратора доменных имен таким образом, чтобы они указывали на основной и дополнительный DNS-серверы Office 365. После этого Office 365 обновит записи DNS для вашего домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.</span><span class="sxs-lookup"><span data-stu-id="68038-p111">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="68038-p112">Когда вы изменяете записи серверов имен своего домена, чтобы они указывали на DNS-серверы Office 365, это оказывает влияние на все службы, которые в настоящий момент связаны с доменом. Например, все сообщения электронной почты, отправленные на адреса в вашем домене (вида kirill@ *ваш_домен*  .com), после этого изменения будут попадать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="68038-p112">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68038-170">В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны.</span><span class="sxs-lookup"><span data-stu-id="68038-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="68038-171">После выполнения действий, описанных в этом разделе, единственным серверов доменных имен, которые должны быть указаны, являются следующие четыре: **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**и **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="68038-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="68038-p114">Прежде всего перейдите по [этой ссылке](https://portal.hostgator.com/domain/manage), чтобы открыть вашу страницу на сайте Hostgator, а затем выполните вход.</span><span class="sxs-lookup"><span data-stu-id="68038-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="68038-175">Перейдите на вкладку **домены** .</span><span class="sxs-lookup"><span data-stu-id="68038-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="68038-177">На странице " **Управление доменами** " в разделе **My Domains (мои домены** ) выберите домен, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="68038-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="68038-179">На странице " **Обзор домена** " в области **серверы имен** нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="68038-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="68038-181">На странице **серверы имен** для вашего домена в раскрывающемся списке **Выбор учетной записи размещения** выберите **учетную запись размещения** , связанную с доменом.</span><span class="sxs-lookup"><span data-stu-id="68038-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="68038-183">Выберите **установку серверов имен вручную**.</span><span class="sxs-lookup"><span data-stu-id="68038-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="68038-185">**Внимание!** выполните эти действия только в том случае, если у вас есть серверов доменных имен, отличный от четырех правильных серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="68038-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="68038-186">(То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="68038-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="68038-187">На странице **Name Servers** (Серверы доменных имен) для вашего домена удалите из списка серверов доменных имен все серверы, выделяя каждый из них и нажимая на клавиатуре клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="68038-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="68038-189">В том же списке серверов доменных имен введите (или скопируйте и вставьте) первые два значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="68038-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="68038-190">**Name Server 1:** (Сервер доменных имен 1)</span><span class="sxs-lookup"><span data-stu-id="68038-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="68038-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="68038-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="68038-192">**Name Server 2:** (Сервер доменных имен 2)</span><span class="sxs-lookup"><span data-stu-id="68038-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="68038-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="68038-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="68038-194">**Name Server 3** (Сервер доменных имен 3)</span><span class="sxs-lookup"><span data-stu-id="68038-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="68038-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="68038-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="68038-196">**Name Server 4** (Сервер доменных имен 4)</span><span class="sxs-lookup"><span data-stu-id="68038-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="68038-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="68038-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator — BP — redelegate — 1-7-1](../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="68038-199">Добавьте значения для других серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="68038-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="68038-200">Нажмите кнопку **(+)** добавить, а затем введите (или скопируйте и вставьте) значение из следующей строки таблицы в поле для записи.</span><span class="sxs-lookup"><span data-stu-id="68038-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="68038-201">Повторяйте эти действия, пока не создадите все четыре записи серверов доменных имен.</span><span class="sxs-lookup"><span data-stu-id="68038-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="68038-203">Выберите команду **сохранить серверы имен**.</span><span class="sxs-lookup"><span data-stu-id="68038-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="68038-p116">На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта и все остальные службы Office 365 будут настроены на работу с новым доменом.</span><span class="sxs-lookup"><span data-stu-id="68038-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>