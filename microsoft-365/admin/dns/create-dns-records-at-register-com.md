---
title: Создание записей DNS на сайте Register.com для Майкрософт
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Register.com для Майкрософт.
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780329"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Создание записей DNS на сайте Register.com для Майкрософт

 **[Вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если ваш поставщик услуг размещения DNS  Register.com, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.
  
Ниже перечислены основные записи, которые нужно добавить. Воспользуйтесь инструкциями ниже или [посмотрите видеоролик](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
- [Добавление записи TXT на сайте Register.com для подтверждения владения доменом](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Когда вы добавите эти записи на сайте Register.com, ваш домен будет настроен для работы со службами Майкрософт.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Добавление записи TXT на сайте Register.com для подтверждения владения доменом
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.
    
2. Выберите раздел **Домены**.
    
3. Выберите **Управление**.
    
4. Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.
    
5. Прокрутите окно вниз до раздела **Дополнительные технические параметры** и выберите команду **изменить записи TXT (SPF)**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Примечание.** Это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Нажмите кнопку **продолжить**.
    
8. На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения. 
    
9. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.
<a name="BKMK_add_MX"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.
    
2. Выберите раздел **Домены**.
    
3. Выберите **Управление**.
    
4. Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.
    
5. Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи почтового обменника**.
    
    ![Выберите Изменить записи почтового обменника](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    В раскрывающемся списке выберите значение **Priority (приоритет** ). 
    
    |****Host Name** (Имя узла)**|****Priority** (Приоритет)**|****Mail Server** (Почтовый сервер)**|
    |:-----|:-----|:-----|
    |@  <br/> |High (Высокий)  <br/> Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).    <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/>  <br/>**Примечание:** Получение \<*domain-key*\> учетной записи Майкрософт. <br> [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Скопируйте и вставьте значение из таблицы](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Если уже указаны какие-либо другие записи MX, выделите каждую из них и удалите.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Нажмите кнопку **продолжить**.
    
    ![Нажмите кнопку продолжить.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения. 
    
    ![Нажмите кнопку продолжить.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_CNAME"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.
    
2. Выберите раздел **Домены**.
    
3. Выберите **Управление**.
    
4. Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.
    
5. Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи псевдонимов домена**.
    
    ![Выберите пункт "изменить записи псевдонимов домена"](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Выберите **добавить дополнительные псевдонимы доменов**.
    
    ![Выберите Добавить другие псевдонимы доменов](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Добавьте необходимые записи CNAME.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    |****Первое поле (без подписи)****|****Points to** (Указывает на)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Копирование и вставка значений DNS из таблицы](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. После добавления всех необходимых записей CNAME нажмите кнопку **продолжить**.
    
    ![Нажмите кнопку продолжить.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения. 
    
    ![Нажмите кнопку продолжить.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения для продуктов корпорации Майкрософт в текущую запись. Таким образом, в одной записи SPF будут указаны оба набора значений.  
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Чтобы приступить к работе, перейдите на свою страницу доменов на сайте Register.com по [этой ссылке](https://www.register.com/myaccount/). Сперва вам потребуется войти в систему.
    
2. Выберите раздел **Домены**.
    
3. Выберите **Управление**.
    
4. Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.
    
5. Перейдите к разделу **Дополнительные технические параметры** , а затем выберите команду **изменить записи TXT (SPF)**.
    
    ![Выберите команду Изменить записи TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.
    
    |****Host Name** (Имя узла)**|****TXT Record** (Запись TXT)**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.      |
   
     ![Скопируйте и вставьте значения из таблицы](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Нажмите кнопку **продолжить**.
    
    ![Нажмите кнопку продолжить.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения. 
    
    ![Нажмите кнопку продолжить.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт
<a name="BKMK_add_SRV"> </a>

Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.
    
2. Выберите раздел **Домены**.
    
3. Выберите **Управление**.
    
4. Найдите строку, содержащую имя домена, который требуется изменить; затем в этой строке выберите **Управление**.
    
5. Перейдите к разделу **Дополнительные технические параметры** , а затем выберите **изменить записи SRV**.
    
    ![Выберите Изменить записи SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Добавьте первую из двух записей SRV.
    
    В поля для новой записи введите (или скопируйте и вставьте) значения из первой строки приведенной ниже таблицы.
    
    В раскрывающемся списке выберите значение **Priority (приоритет** ). 
    
    |****Service** (Служба)**|****Proto** (Протокол)**|****Name** (Имя)**|****Priority** (Приоритет)**|****Weight** (Вес)**|****Port** (Порт)**|****Target** (Целевое значение)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High (Высокий)  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High (Высокий)  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Скопируйте и вставьте значения из таблицы](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Выберите **добавить дополнительные записи SRV**.
    
    ![Выберите добавить дополнительные записи SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Добавьте вторую запись SRV.
    
    В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.
    
9. После добавления обеих записей SRV нажмите кнопку **продолжить**.
    
    ![Нажмите кнопку продолжить.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. На следующей странице нажмите кнопку **продолжить** еще раз, чтобы подтвердить изменения и сохранить изменения. 
    
    ![Нажмите кнопку продолжить.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
