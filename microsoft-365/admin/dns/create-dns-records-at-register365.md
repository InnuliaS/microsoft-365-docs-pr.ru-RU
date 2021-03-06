---
title: Создание записей DNS на сайте Register365 для Майкрософт
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register365 для Майкрософт.
ms.openlocfilehash: e580779ce674375564c1b3ab6123ef1b19f50be0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400320"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>Создание записей DNS на сайте Register365 для Майкрософт

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  Register365, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб. 
  
Ниже перечислены основные записи, которые нужно добавить.  
  
- [Добавление записи TXT для проверки](#add-a-txt-record-for-verification)
    
- [Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Добавление шести записей CNAME, необходимых для Майкрософт](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Когда вы добавите эти записи в корпорацию Майкрософт, ваш домен будет настроен для работы со службами Майкрософт.
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS). 
    
    (You may have to scroll down.)
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Host Name (Имя узла)**|**Type (Тип)**|**Результат**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.           [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (You may have to scroll down.)
    
    ![Нажмите кнопку Сохранить](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
    
  
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
    
  
4. На странице **Проверка домена** выберите **Проверить**.
    
    
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS). 
    
    (You may have to scroll down.)
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Mail exchange records** (Записи обмена электронной почтой) в поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (You may have to scroll down.)
    
    |**Host Name (Имя узла)**|**Priority (Приоритет)**|**Результат**|
    |:-----|:-----|:-----|
    |(Оставьте это поле пустым.)  <br/> |1   <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).    <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **Примечание:** Получение *\<domain-key\>* учетной записи Майкрософт.  [Как его найти?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (You may have to scroll down.)
    
    ![Нажмите кнопку Сохранить](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Если в разделе **Mail exchange records** (Записи обмена электронной почтой) указаны какие-либо другие записи MX, удалите каждую из них, выделив ее и нажав на клавиатуре клавишу **DELETE**. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Нажмите кнопку **Сохранить**.
    
    (You may have to scroll down.)
    
    ![Нажмите кнопку Сохранить](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Добавление шести записей CNAME, необходимых для Майкрософт
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS). 
    
    (You may have to scroll down.)
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **A, CNAME, AAAA, TXT and NS records** (Записи A, CNAME, AAAA, TXT и NS) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |****Host Name** (Имя узла)**|****Type** (Тип)**|****Result** (Результат)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Нажмите кнопку **Сохранить**.
    
    ![Нажмите кнопку Сохранить](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений. 
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS). 
    
    (You may have to scroll down.)
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Если необходимо добавить строку, выберите **добавить записи a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Host Name (Имя узла)**|**Type (Тип)**|**Результат**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![Ввод значений на странице "Добавление и изменение зоны DNS"](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (You may have to scroll down.)
    
    ![Нажмите кнопку Сохранить](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register365 по [этой ссылке](https://admin.register365.com/dns/). Сначала вам потребуется выполнить вход.
    
    ![Страница входа на панель управления](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. На странице **Dashboard** (Панель мониторинга) найдите доменное имя, которое хотите обновить, и выберите в раскрывающемся списке пункт **DNS Settings** (Параметры DNS). 
    
    (You may have to scroll down.)
    
    ![Выбор параметров DNS в списке](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. На странице **Add/Modify DNS Zone** (Добавить/изменить зону DNS) в разделе **Service records** (Записи службы) в поля для новых записей введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
    |**Name (Имя)**|**Priority** (Приоритет)|**Weight** (Вес)|**Port** (Порт)|**Result (Результат)**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Ввод значений в раздел "записи службы"](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Нажмите кнопку **Сохранить**.
    
    (You may have to scroll down.)
    
    ![Нажмите кнопку Сохранить](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
