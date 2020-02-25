---
title: Создание записей DNS для Office 365 в Netregistry
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Netregistry для Office 365.
ms.openlocfilehash: de4e16fa20f950edef8d30b4c6d02214e3753b9c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254674"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="44f60-103">Создание записей DNS для Office 365 в Netregistry</span><span class="sxs-lookup"><span data-stu-id="44f60-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="44f60-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="44f60-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="44f60-105">Если ваш поставщик услуг размещения DNS  Netregistry, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="44f60-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="44f60-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="44f60-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="44f60-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="44f60-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="44f60-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f60-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="44f60-109">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="44f60-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="44f60-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="44f60-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="44f60-111">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="44f60-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="44f60-112">Когда вы добавите эти записи на сайте Netregistry, ваш домен будет настроен для работы со службами Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f60-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="44f60-113">Дополнительные сведения о веб-хостинге и DNS для веб-сайтов в Office 365 см. в статье [Работа с общедоступным веб-сайтом в Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="44f60-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="44f60-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44f60-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="44f60-117">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="44f60-117">Add a TXT record for verification</span></span>
<span data-ttu-id="44f60-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="44f60-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="44f60-p102">Прежде чем вы сможете использовать свой домен в Office 365, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, это послужит для Office 365 подтверждением того, что вы владеете данным доменом.</span><span class="sxs-lookup"><span data-stu-id="44f60-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44f60-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="44f60-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="44f60-p104">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="44f60-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="44f60-126">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="44f60-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="44f60-128">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="44f60-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="44f60-130">В разделе **Добавление записи зоны**выберите **запись TXT** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="44f60-132">Перед и после записи в поле TXT необходимо использовать кавычки.</span><span class="sxs-lookup"><span data-stu-id="44f60-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="44f60-133">В форме **New TXT Record** (Новая запись типа TXT) введите (или скопируйте и вставьте) значения из следующей таблицы:</span><span class="sxs-lookup"><span data-stu-id="44f60-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="44f60-134">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="44f60-134">**Name**</span></span>|<span data-ttu-id="44f60-135">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="44f60-135">**TTL (SEC)**</span></span>|<span data-ttu-id="44f60-136">**TXT (Адрес "указывает на" или значение)**</span><span class="sxs-lookup"><span data-stu-id="44f60-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="44f60-137">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="44f60-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="44f60-138">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-139">"MS = Мскскскскскскскскс"</span><span class="sxs-lookup"><span data-stu-id="44f60-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="44f60-140">**Примечание:** Это пример.</span><span class="sxs-lookup"><span data-stu-id="44f60-140">**Note:** This is an example.</span></span> <span data-ttu-id="44f60-141">Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f60-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="44f60-142">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="44f60-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="44f60-144">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-144">Select **Add record**.</span></span>
    
<span data-ttu-id="44f60-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="44f60-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="44f60-146">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="44f60-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="44f60-147">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="44f60-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="44f60-148">На странице **Domains (домены** ) выберите домен, который вы хотите проверить.</span><span class="sxs-lookup"><span data-stu-id="44f60-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="44f60-149">На странице **Настройка** выберите пункт **Запуск программы установки**.</span><span class="sxs-lookup"><span data-stu-id="44f60-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="44f60-150">На странице **Проверка домена** нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="44f60-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="44f60-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44f60-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="44f60-154">Добавление записи MX, необходимой для доставки сообщений электронной почты для вашего домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="44f60-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="44f60-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="44f60-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="44f60-p107">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="44f60-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="44f60-159">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="44f60-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="44f60-161">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="44f60-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="44f60-163">В разделе **текущие записи зоны**удалите записи MX по умолчанию, нажав кнопку **Удалить** рядом с каждой записью MX в списке.</span><span class="sxs-lookup"><span data-stu-id="44f60-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="44f60-165">В разделе **Добавление записи зоны**выберите **запись MX** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="44f60-167">В **новой форме MX Record (запись MX** ) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="44f60-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="44f60-168">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="44f60-168">**Name**</span></span>|<span data-ttu-id="44f60-169">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="44f60-169">**TTL (SEC)**</span></span>|<span data-ttu-id="44f60-170">**Exchange (указывает на адрес или значение)**</span><span class="sxs-lookup"><span data-stu-id="44f60-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="44f60-171">**Является полным узлом?**</span><span class="sxs-lookup"><span data-stu-id="44f60-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="44f60-172">**Предпочтения (приоритет)**</span><span class="sxs-lookup"><span data-stu-id="44f60-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44f60-173">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="44f60-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="44f60-174">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="44f60-175">*\<ключ-домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="44f60-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="44f60-176">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f60-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="44f60-177">Как найти это значение?</span><span class="sxs-lookup"><span data-stu-id="44f60-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="44f60-178">(установите флажок)</span><span class="sxs-lookup"><span data-stu-id="44f60-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="44f60-179">10 </span><span class="sxs-lookup"><span data-stu-id="44f60-179">10</span></span>  <br/> <span data-ttu-id="44f60-180">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="44f60-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="44f60-182">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="44f60-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="44f60-184">Добавление записей CNAME, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="44f60-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="44f60-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="44f60-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="44f60-p109">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="44f60-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="44f60-189">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="44f60-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="44f60-191">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="44f60-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="44f60-193">В разделе **Добавление записи зоны**выберите **запись CNAME** в списке и нажмите кнопку **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="44f60-195">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="44f60-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="44f60-196">**Имя**</span><span class="sxs-lookup"><span data-stu-id="44f60-196">**Name**</span></span>|<span data-ttu-id="44f60-197">**Тип**</span><span class="sxs-lookup"><span data-stu-id="44f60-197">**Type**</span></span>|<span data-ttu-id="44f60-198">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="44f60-198">**TTL**</span></span>|<span data-ttu-id="44f60-199">**УЗЕЛ (значение "точка" или "адрес")**</span><span class="sxs-lookup"><span data-stu-id="44f60-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44f60-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="44f60-200">autodiscover</span></span>  <br/> |<span data-ttu-id="44f60-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="44f60-201">CNAME</span></span>  <br/> |<span data-ttu-id="44f60-202">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="44f60-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="44f60-204">sip</span><span class="sxs-lookup"><span data-stu-id="44f60-204">sip</span></span>  <br/> |<span data-ttu-id="44f60-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="44f60-205">CNAME</span></span>  <br/> |<span data-ttu-id="44f60-206">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="44f60-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="44f60-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="44f60-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="44f60-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="44f60-209">CNAME</span></span>  <br/> |<span data-ttu-id="44f60-210">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="44f60-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="44f60-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="44f60-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="44f60-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="44f60-213">CNAME</span></span>  <br/> |<span data-ttu-id="44f60-214">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="44f60-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="44f60-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="44f60-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="44f60-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="44f60-217">CNAME</span></span>  <br/> |<span data-ttu-id="44f60-218">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="44f60-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="44f60-221">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="44f60-223">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="44f60-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="44f60-224">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="44f60-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="44f60-225">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="44f60-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="44f60-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="44f60-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="44f60-227">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="44f60-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="44f60-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="44f60-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="44f60-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="44f60-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="44f60-230">Вместо этого добавьте необходимые значения Office 365 к текущей записи, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="44f60-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="44f60-p111">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="44f60-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="44f60-234">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="44f60-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="44f60-236">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="44f60-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="44f60-238">В разделе **Добавление записи зоны**выберите **запись TXT** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="44f60-240">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="44f60-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="44f60-241">Перед и после записи в поле TXT необходимо использовать кавычки.</span><span class="sxs-lookup"><span data-stu-id="44f60-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="44f60-242">**Имя**</span><span class="sxs-lookup"><span data-stu-id="44f60-242">**Name**</span></span>|<span data-ttu-id="44f60-243">**Тип**</span><span class="sxs-lookup"><span data-stu-id="44f60-243">**Type**</span></span>|<span data-ttu-id="44f60-244">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="44f60-244">**TTL**</span></span>|<span data-ttu-id="44f60-245">**Данные TXT (Target)**</span><span class="sxs-lookup"><span data-stu-id="44f60-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44f60-246">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="44f60-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="44f60-247">TXT</span><span class="sxs-lookup"><span data-stu-id="44f60-247">TXT</span></span>  <br/> |<span data-ttu-id="44f60-248">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-249">"v = spf1 включает:SPF. Protection. Outlook. com-ALL"</span><span class="sxs-lookup"><span data-stu-id="44f60-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="44f60-250">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="44f60-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF Ткствалуес](../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="44f60-252">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="44f60-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="44f60-254">Добавление двух записей SRV, необходимых для Office 365</span><span class="sxs-lookup"><span data-stu-id="44f60-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="44f60-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="44f60-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="44f60-p112">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="44f60-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="44f60-259">Рядом с доменом, которым вы хотите управлять, выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="44f60-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="44f60-261">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="44f60-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="44f60-263">В разделе **Добавление записи зоны**выберите **запись SRV** из списка и нажмите кнопку **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="44f60-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="44f60-265">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="44f60-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44f60-266">Поле Name — это сочетание службы (например, _sip) и протокола (например, _tls).</span><span class="sxs-lookup"><span data-stu-id="44f60-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="44f60-267">**Тип**</span><span class="sxs-lookup"><span data-stu-id="44f60-267">**Type**</span></span>|<span data-ttu-id="44f60-268">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="44f60-268">**Name**</span></span>|<span data-ttu-id="44f60-269">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="44f60-269">**TTL (SEC)**</span></span>|<span data-ttu-id="44f60-270">**Priority (Приоритет)**</span><span class="sxs-lookup"><span data-stu-id="44f60-270">**Priority**</span></span>|<span data-ttu-id="44f60-271">**Weight (Вес)**</span><span class="sxs-lookup"><span data-stu-id="44f60-271">**Weight**</span></span>|<span data-ttu-id="44f60-272">**Port (Порт)**</span><span class="sxs-lookup"><span data-stu-id="44f60-272">**Port**</span></span>|<span data-ttu-id="44f60-273">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="44f60-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44f60-274">SRV (служба)</span><span class="sxs-lookup"><span data-stu-id="44f60-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="44f60-275">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="44f60-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="44f60-276">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-277">100</span><span class="sxs-lookup"><span data-stu-id="44f60-277">100</span></span>  <br/> |<span data-ttu-id="44f60-278">1,1</span><span class="sxs-lookup"><span data-stu-id="44f60-278">1</span></span>  <br/> |<span data-ttu-id="44f60-279">443</span><span class="sxs-lookup"><span data-stu-id="44f60-279">443</span></span>  <br/> |<span data-ttu-id="44f60-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="44f60-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="44f60-281">SRV (служба)</span><span class="sxs-lookup"><span data-stu-id="44f60-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="44f60-282">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="44f60-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="44f60-283">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="44f60-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="44f60-284">100</span><span class="sxs-lookup"><span data-stu-id="44f60-284">100</span></span>  <br/> |<span data-ttu-id="44f60-285">1,1</span><span class="sxs-lookup"><span data-stu-id="44f60-285">1</span></span>  <br/> |<span data-ttu-id="44f60-286">5061</span><span class="sxs-lookup"><span data-stu-id="44f60-286">5061</span></span>  <br/> |<span data-ttu-id="44f60-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="44f60-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="44f60-289">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="44f60-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="44f60-291">Повторите эти действия для другой записи SRV.</span><span class="sxs-lookup"><span data-stu-id="44f60-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="44f60-292">В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="44f60-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="44f60-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44f60-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
