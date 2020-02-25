---
title: Создание записей DNS в Amazon Web Services (AWS) для Office 365
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в веб-службах Amazon (AWS) для Office 365.
ms.openlocfilehash: 307ef7fd81093360c8546dadc28ea7974995518f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246923"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="0fab5-103">Создание записей DNS в Amazon Web Services (AWS) для Office 365</span><span class="sxs-lookup"><span data-stu-id="0fab5-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="0fab5-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0fab5-105">Если AWS является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype Online для бизнеса и т. д.</span><span class="sxs-lookup"><span data-stu-id="0fab5-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="0fab5-106">Когда вы добавите эти записи на сайте AWS, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fab5-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="0fab5-107">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="0fab5-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fab5-p101">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fab5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0fab5-111">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="0fab5-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0fab5-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0fab5-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0fab5-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fab5-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0fab5-117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="0fab5-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="0fab5-118">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fab5-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0fab5-119">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0fab5-120">На странице \* \* Hosted Zones \* \* в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0fab5-121">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0fab5-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0fab5-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0fab5-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="0fab5-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0fab5-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fab5-126">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fab5-126">**Name**</span></span> <br/> |<span data-ttu-id="0fab5-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fab5-127">**Type**</span></span> <br/> |<span data-ttu-id="0fab5-128">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-128">**Alias**</span></span> <br/> |<span data-ttu-id="0fab5-129">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="0fab5-130">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-130">**Value**</span></span> <br/> |<span data-ttu-id="0fab5-131">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="0fab5-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="0fab5-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0fab5-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="0fab5-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="0fab5-134">Нет</span><span class="sxs-lookup"><span data-stu-id="0fab5-134">No</span></span>  <br/> |<span data-ttu-id="0fab5-135">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-135">300</span></span>  <br/> |<span data-ttu-id="0fab5-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0fab5-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="0fab5-137">**Примечание:** Это пример.</span><span class="sxs-lookup"><span data-stu-id="0fab5-137">**Note:** This is an example.</span></span> <span data-ttu-id="0fab5-138">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fab5-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="0fab5-139">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="0fab5-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0fab5-140">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0fab5-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="0fab5-141">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="0fab5-142">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0fab5-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0fab5-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="0fab5-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0fab5-144">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="0fab5-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0fab5-145">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="0fab5-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0fab5-146">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0fab5-147">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0fab5-148">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0fab5-p107">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fab5-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="0fab5-152">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="0fab5-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="0fab5-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0fab5-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0fab5-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0fab5-156">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0fab5-157">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0fab5-158">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0fab5-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0fab5-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0fab5-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="0fab5-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="0fab5-161">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fab5-161">**Name**</span></span>|<span data-ttu-id="0fab5-162">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fab5-162">**Type**</span></span>|<span data-ttu-id="0fab5-163">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-163">**Alias**</span></span>|<span data-ttu-id="0fab5-164">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="0fab5-165">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-165">**Value**</span></span>|<span data-ttu-id="0fab5-166">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fab5-167">(Оставьте это поле пустым.)</span><span class="sxs-lookup"><span data-stu-id="0fab5-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="0fab5-168">MX  почтовый обменник</span><span class="sxs-lookup"><span data-stu-id="0fab5-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="0fab5-169">Нет</span><span class="sxs-lookup"><span data-stu-id="0fab5-169">No</span></span>  <br/> |<span data-ttu-id="0fab5-170">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-170">300</span></span>  <br/> |<span data-ttu-id="0fab5-171">0  *\<ключ_домена\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0fab5-p109">0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="0fab5-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="0fab5-174">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0fab5-175">**Примечание:** \<Получите *ключ* \> домена из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fab5-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="0fab5-176">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="0fab5-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0fab5-177">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0fab5-177">Simple</span></span>  <br/> |
       
    ![AWS — BP — configure – 2-1](../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="0fab5-179">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="0fab5-181">Если есть другие записи MX, удалите их.</span><span class="sxs-lookup"><span data-stu-id="0fab5-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0fab5-182">AWS хранит записи MX в виде наборов, которые могут содержать сразу несколько записей.</span><span class="sxs-lookup"><span data-stu-id="0fab5-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="0fab5-183">**Не** выбирайте параметр **Удалить набор записей**, так как это приведет к удалению всех записей MX, включая только что добавленный.</span><span class="sxs-lookup"><span data-stu-id="0fab5-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="0fab5-184">Вместо этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0fab5-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="0fab5-185">Сначала выберите набор записей MX.</span><span class="sxs-lookup"><span data-stu-id="0fab5-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="0fab5-187">Затем в области **Edit Record Set** (Изменить набор записей) удалите каждую из устаревших записей MX, выбрав ее в поле **Value** (Значение) и нажав клавишу **DELETE**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="0fab5-189">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="0fab5-191">Добавление пяти записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="0fab5-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="0fab5-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0fab5-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0fab5-p112">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0fab5-195">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0fab5-196">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0fab5-197">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0fab5-198">Добавьте первую запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="0fab5-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="0fab5-199">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fab5-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="0fab5-200">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="0fab5-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="0fab5-201">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fab5-201">**Name**</span></span>|<span data-ttu-id="0fab5-202">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fab5-202">**Type**</span></span>|<span data-ttu-id="0fab5-203">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-203">**Alias**</span></span>|<span data-ttu-id="0fab5-204">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="0fab5-205">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-205">**Value**</span></span>|<span data-ttu-id="0fab5-206">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fab5-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0fab5-207">autodiscover</span></span>  <br/> |<span data-ttu-id="0fab5-208">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="0fab5-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="0fab5-209">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-209">No</span></span>  <br/> |<span data-ttu-id="0fab5-210">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-210">300</span></span>  <br/> |<span data-ttu-id="0fab5-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0fab5-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0fab5-213">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="0fab5-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="0fab5-214">sip</span><span class="sxs-lookup"><span data-stu-id="0fab5-214">sip</span></span>  <br/> |<span data-ttu-id="0fab5-215">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="0fab5-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="0fab5-216">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-216">No</span></span>  <br/> |<span data-ttu-id="0fab5-217">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-217">300</span></span>  <br/> |<span data-ttu-id="0fab5-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0fab5-219">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0fab5-220">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="0fab5-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="0fab5-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0fab5-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0fab5-222">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="0fab5-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="0fab5-223">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-223">No</span></span>  <br/> |<span data-ttu-id="0fab5-224">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-224">300</span></span>  <br/> |<span data-ttu-id="0fab5-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0fab5-226">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0fab5-227">Это совсем не сложно.</span><span class="sxs-lookup"><span data-stu-id="0fab5-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="0fab5-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0fab5-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0fab5-229">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="0fab5-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="0fab5-230">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-230">No</span></span>  <br/> |<span data-ttu-id="0fab5-231">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-231">300</span></span>  <br/> |<span data-ttu-id="0fab5-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="0fab5-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0fab5-233">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0fab5-234">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0fab5-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="0fab5-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0fab5-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0fab5-236">CNAME  каноническое имя</span><span class="sxs-lookup"><span data-stu-id="0fab5-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="0fab5-237">Нет</span><span class="sxs-lookup"><span data-stu-id="0fab5-237">No</span></span>  <br/> |<span data-ttu-id="0fab5-238">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-238">300</span></span>  <br/> |<span data-ttu-id="0fab5-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0fab5-240">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="0fab5-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="0fab5-241">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0fab5-241">Simple</span></span>  <br/> |
   
    ![AWS — BP — configure – 3-1](../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="0fab5-243">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="0fab5-245">Добавьте остальные четыре записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="0fab5-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="0fab5-246">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="0fab5-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="0fab5-247">Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="0fab5-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0fab5-248">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="0fab5-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0fab5-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0fab5-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fab5-250">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="0fab5-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0fab5-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="0fab5-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0fab5-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="0fab5-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="0fab5-253">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="0fab5-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0fab5-254">Нужны примеры?</span><span class="sxs-lookup"><span data-stu-id="0fab5-254">Need examples?</span></span> <span data-ttu-id="0fab5-255">Ознакомьтесь с этими [сведениями и образцами записей SPF](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="0fab5-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="0fab5-256">Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="0fab5-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="0fab5-257">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="0fab5-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="0fab5-258">Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fab5-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0fab5-259">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0fab5-260">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0fab5-261">Выберите набор записей **txt** .</span><span class="sxs-lookup"><span data-stu-id="0fab5-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="0fab5-p115">В области **Edit Record Set** (Изменение набора записей) в конце текущего элемента в поле **Value:** (Значение) существующей записи нажмите клавишу ВВОД, чтобы перейти на новую строку, а затем в этой новой строке (под существующим значением) введите или вставьте значение из таблицы ниже. (Пример приведен на рисунке под таблицей.)</span><span class="sxs-lookup"><span data-stu-id="0fab5-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="0fab5-265">**Значение:**</span><span class="sxs-lookup"><span data-stu-id="0fab5-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="0fab5-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0fab5-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0fab5-p116">(Кавычки, которые требуются в инструкциях на экране, добавляются автоматически. Вводить их вручную не нужно.)  </span><span class="sxs-lookup"><span data-stu-id="0fab5-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="0fab5-269">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0fab5-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS — BP — configure – 4-2](../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="0fab5-271">Выберите **сохранить набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="0fab5-273">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="0fab5-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="0fab5-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0fab5-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0fab5-p117">Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="0fab5-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0fab5-277">На странице **ресурсы** выберите пункт **размещенные зоны**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="0fab5-278">На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab5-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="0fab5-279">Выберите **создать набор записей**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="0fab5-280">Добавьте первую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="0fab5-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="0fab5-281">В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="0fab5-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="0fab5-282">Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации).</span><span class="sxs-lookup"><span data-stu-id="0fab5-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="0fab5-283">**Имя**</span><span class="sxs-lookup"><span data-stu-id="0fab5-283">**Name**</span></span>|<span data-ttu-id="0fab5-284">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0fab5-284">**Type**</span></span>|<span data-ttu-id="0fab5-285">**Alias (Псевдоним)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-285">**Alias**</span></span>|<span data-ttu-id="0fab5-286">**TTL (Seconds) (Срок жизни, в секундах)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="0fab5-287">**Value (Значение)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-287">**Value**</span></span>|<span data-ttu-id="0fab5-288">**Routing Policy (Политика маршрутизации)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0fab5-289">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="0fab5-289">_sip._tls</span></span>|<span data-ttu-id="0fab5-290">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="0fab5-290">SRV - Service locator</span></span>|<span data-ttu-id="0fab5-291">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-291">No</span></span>|<span data-ttu-id="0fab5-292">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-292">300</span></span>|<span data-ttu-id="0fab5-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="0fab5-294">**Это значение должно заканчиваться точкой (.).**></span><span class="sxs-lookup"><span data-stu-id="0fab5-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="0fab5-295">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0fab5-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="0fab5-296">Simple (Простая)</span><span class="sxs-lookup"><span data-stu-id="0fab5-296">Simple</span></span>|
    |<span data-ttu-id="0fab5-297">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="0fab5-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0fab5-298">SRV  указатель служб</span><span class="sxs-lookup"><span data-stu-id="0fab5-298">SRV - Service locator</span></span>|<span data-ttu-id="0fab5-299">No (Нет)</span><span class="sxs-lookup"><span data-stu-id="0fab5-299">No</span></span>|<span data-ttu-id="0fab5-300">300</span><span class="sxs-lookup"><span data-stu-id="0fab5-300">300</span></span>|<span data-ttu-id="0fab5-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0fab5-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="0fab5-302">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0fab5-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="0fab5-303">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="0fab5-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="0fab5-304">Простое</span><span class="sxs-lookup"><span data-stu-id="0fab5-304">Simple</span></span>|
   
    ![AWS — BP — configure – 5-1](../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="0fab5-306">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0fab5-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="0fab5-308">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="0fab5-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="0fab5-309">На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись.</span><span class="sxs-lookup"><span data-stu-id="0fab5-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0fab5-p120">Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с потоком обработки почты или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS в Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0fab5-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  