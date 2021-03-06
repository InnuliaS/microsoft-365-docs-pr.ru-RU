---
title: Создать записи DNS на сайте MyDomain для работы с продуктами корпорации Майкрософт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Узнайте, как проверить свой домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб корпорации Майкрософт на сайте My Domain.
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400416"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a>Создать записи DNS на сайте MyDomain для работы с продуктами корпорации Майкрософт


  
 Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
> [!CAUTION]
> The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider. 
  
Если вы хотите управлять своими записями DNS при работе с продуктами корпорации Майкрософт на сайте MyDomain несмотря на ограничения в работе служб, выполните действия, описанные в этой статье, чтобы настроить записи DNS для электронной почты, Skype для бизнеса Online и т. д.
    
Когда вы добавите эти записи на сайте MyDomain, ваш домен будет настроен для работы со службами Майкрософт.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).
    
6. В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.
    
    ||
    |:-----|
    |**Контент** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Нажмите кнопку **Add** (Добавить).
    
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **MX Record** (Запись MX).
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**Priority**|**Host**|**Points To** (Указывает на)|
    |:-----|:-----|:-----|
    |0  <br/> Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Примечание.**  Получите свой \<*domain-key*\> из учетной записи Майкрософт. > [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. Нажмите кнопку **Add** (Добавить).
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. Если в списке указаны другие существующие записи MX, для каждой из них выберите команду **Remove** (Удалить) в столбце **Action** (Действие). 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. Нажмите кнопку **ОК**.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **CNAME Alias** (Псевдоним CNAME).
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. Добавьте первую запись CNAME.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    |**Host**|**Points To** (Указывает на)|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. Нажмите **Add** (Добавить), чтобы добавить первую запись. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. Добавьте вторую запись CNAME.
    
    Введите значения из второй строки приведенной выше таблицы, а затем нажмите кнопку **Add** (Добавить), чтобы создать вторую запись. 
    
    Точно так же добавьте остальные записи, используя значения из третьей, четвертой, пятой и шестой строк таблицы.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавление записи TXT для SPF, предотвращающей рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.
    
    |**Контент**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. Нажмите кнопку **Add** (Добавить).
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
