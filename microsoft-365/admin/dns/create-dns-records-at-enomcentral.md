---
title: Создание записей DNS на сайте eNomCentral для Майкрософт
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу eNomCentral для Майкрософт.
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780401"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Создание записей DNS на сайте eNomCentral для Майкрософт

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  eNomCentral, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
Когда вы добавите эти записи на сайте eNomCentral, ваш домен будет настроен для работы со службами Майкрософт.

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).
    
    ![eNom Central — BP — Verify – 1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    В раскрывающемся списке выберите значение **тип записи** .
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Record Type** <br/> |**Address** (Адрес) <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom Central — BP — Verify – 1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. Нажмите кнопку **сохранить**.
    
    ![eNom Central — BP — Verify – 1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Email Settings** (Параметры электронной почты).
    
    ![eNom Central — BP — configure – 1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. В раскрывающемся списке **Service Selection** (Выбор службы) выберите пункт **User (MX)** (Пользователь (MX).
    
    ![eNom Central — BP — configure – 1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Host Name**|**Address**|**Pref (Предпочтение)**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<domain-key\>*. mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Примечание:** Получение *\<domain-key\>* учетной записи Майкрософт.           [Где это находится?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).    <br/> |
       
   ![eNom Central — BP — configure – 2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. Нажмите кнопку **сохранить**.
    
    ![eNom Central — BP — configure – 2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. Если в списке указаны другие существующие записи MX, установите для них флажки, чтобы выбрать их.
    
    ![eNom Central — BP — configure – 2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. Выберите вариант **Удалить проверено**.
    
    ![eNom Central — BP — configure – 2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт 
<a name="BKMK_add_CNAME"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Выберите пункт **создать строку**.
    
    ![eNom Central — BP — configure – 3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. В поля для шести новых записей введите (или скопируйте и вставьте) следующие значения.
    
В раскрывающемся списке выберите значение **тип записи** .
        
    |**Host Name**|**Record Type**|**Address (Адрес)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (Alias)  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME (Alias)  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (Alias)  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (Alias)  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |enterpriseenrollment  <br/> |CNAME (Alias)  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. Нажмите кнопку **сохранить**.
    
    ![eNom Central — BP — configure – 3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. В поля для новой записи введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.
    
В раскрывающемся списке выберите значение **тип записи** .
    
    |**Host Name**|**Record Type**|**Address** (Адрес)|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
   ![eNom Central — BP — configure – 4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. Нажмите кнопку **сохранить**.
    
    ![eNom Central — BP — configure – 4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Справа от **новой строки**выберите **Добавить запись SRV или SPF**.
    
    ![eNom Central — BP — configure – 5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |**Service (Служба)**|**Protocol (Протокол)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Target          (Hostname) (Узел назначения)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |
   
    ![eNom Central — BP — configure – 5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. Нажмите кнопку **сохранить**
    
    ![eNom Central — BP — configure – 5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

