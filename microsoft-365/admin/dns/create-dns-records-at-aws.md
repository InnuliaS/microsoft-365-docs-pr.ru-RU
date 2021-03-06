---
title: Создание записей DNS на веб-службах Amazon (AWS) для Майкрософт
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб в веб-службах Amazon (AWS) для Майкрософт.
ms.openlocfilehash: fcc4da3a5841e9df2f6edabd540363fe70bb73ad
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400573"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Создание записей DNS на веб-службах Amazon (AWS) для Майкрософт

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Если AWS является поставщиком услуг хостинга DNS, выполните действия, описанные в этой статье, чтобы проверить домен и настроить записи DNS для электронной почты, Skype Online для бизнеса и т. д.
  
Когда вы добавите эти записи на сайте AWS, ваш домен будет настроен для работы со службами Майкрософт.
  

  
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки
<a name="BKMK_verify"> </a>

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.
    
2. На странице **ресурсы** выберите пункт **размещенные зоны**.
    
3. На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить. 
    
4. Выберите **создать набор записей**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Тип** <br/> |**Alias (Псевдоним)** <br/> |**TTL (Seconds) (Срок жизни, в секундах)** <br/> |**Value (Значение)** <br/> |**Routing Policy (Политика маршрутизации)** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |Нет  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Примечание.** Это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |Simple (Простая)  <br/> |
   
6. Нажмите кнопку **Создать**.
    
7. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда вы добавили запись на сайт регистратора доменных имен, вернитесь в корпорацию Майкрософт и запросите Поиск записи.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Добавьте запись MX, чтобы электронная почта для вашего домена поступила в Microsoft 365
<a name="BKMK_add_MX"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.
    
2. На странице **ресурсы** выберите пункт **размещенные зоны**.
    
3. На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить. 
    
4. Выберите **создать набор записей**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**Name**|**Тип**|**Alias (Псевдоним)**|**TTL (Seconds) (Срок жизни, в секундах)**|**Value (Значение)**|**Routing Policy (Политика маршрутизации)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(Оставьте это поле пустым.)  <br/> |MX  почтовый обменник  <br/> |Нет  <br/> |300  <br/> |0 *\<domain-key\>* . mail.Protection.Outlook.com.  <br/> 0  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> **Примечание:** Получите свою \<*domain-key*\> учетную запись от вашей учетной записи Microsoft 365. [Как найти это значение?](../get-help-with-domains/information-for-dns-records.md)          |Simple (Простая)  <br/> |
       
    ![AWS — BP — configure – 2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Нажмите кнопку **Создать**.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Если есть другие записи MX, удалите их.
    
    > [!IMPORTANT]
    > AWS хранит записи MX в виде наборов, которые могут содержать сразу несколько записей. **Не** выбирайте параметр **Удалить набор записей**, так как это приведет к удалению всех записей MX, включая только что добавленный. Вместо этого сделайте следующее: 
  
    Сначала выберите набор записей MX.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    Затем в области **Edit Record Set** (Изменить набор записей) удалите каждую из устаревших записей MX, выбрав ее в поле **Value** (Значение) и нажав клавишу **DELETE**. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Выберите **сохранить набор записей**.
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Добавьте пять записей CNAME, необходимых для Microsoft 365
<a name="BKMK_add_CNAME"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.
    
2. На странице **ресурсы** выберите пункт **размещенные зоны**.
    
3. На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить. 
    
4. Выберите **создать набор записей**.
    
5. Добавьте первую запись CNAME.
    
    В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже. 
    
    Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации). 
    
    |**Name**|**Тип**|**Alias (Псевдоним)**|**TTL (Seconds) (Срок жизни, в секундах)**|**Value (Значение)**|**Routing Policy (Политика маршрутизации)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  каноническое имя  <br/> |No (Нет)  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |Это совсем не сложно.  <br/> |
    |sip  <br/> |CNAME  каноническое имя  <br/> |No (Нет)  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |Это совсем не сложно.  <br/> |
    |lyncdiscover  <br/> |CNAME  каноническое имя  <br/> |No (Нет)  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |Это совсем не сложно.  <br/> |
    |enterpriseregistration  <br/> |CNAME  каноническое имя  <br/> |No (Нет)  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |Simple (Простая)  <br/> |
    |enterpriseenrollment  <br/> |CNAME  каноническое имя  <br/> |No (Нет)  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Это значение ДОЛЖНО оканчиваться точкой (.).** <br/> |Это совсем не сложно.  <br/> |
   
    ![AWS — BP — configure – 3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Нажмите кнопку **Создать**.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Добавьте остальные четыре записи CNAME.
    
    На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись. 
    
    Повторяйте эту процедуру, пока не будут созданы все пять записей CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений. Нужны примеры? Ознакомьтесь с этими [записями системы внешних доменных имен для продуктов корпорации Майкрософт](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Чтобы проверить запись SPF, можно использовать один из этих[средств проверки SPF](../setup/domains-faq.md). 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.
    
2. На странице **ресурсы** выберите пункт **размещенные зоны**.
    
3. На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить. 
    
4. Выберите набор записей **txt** . 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. В области **Edit Record Set** (Изменение набора записей) в конце текущего элемента в поле **Value:** (Значение) существующей записи нажмите клавишу ВВОД, чтобы перейти на новую строку, а затем в этой новой строке (под существующим значением) введите или вставьте значение из таблицы ниже. (Пример приведен на рисунке под таблицей.) 
    
    |**Значение:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (Кавычки, которые требуются в инструкциях на экране, добавляются автоматически. Вводить их вручную не нужно.)  <br/> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |
   
    ![AWS — BP — configure – 4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Выберите **сохранить набор записей**.
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Добавьте две записи SRV, необходимые для Microsoft 365
<a name="BKMK_add_SRV"> </a>

1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте AWS по [этой ссылке](https://console.aws.amazon.com/route53/home). Сначала вам потребуется выполнить вход.
    
2. На странице **ресурсы** выберите пункт **размещенные зоны**.
    
3. На странице " **размещенные зоны** " в столбце **доменное имя** выберите доменное имя, которое требуется изменить. 
    
4. Выберите **создать набор записей**.
    
5. Добавьте первую запись SRV.
    
    В поля для новой записи в области **Create Record Set** (Создание набора записей) введите (или скопируйте и вставьте) значения из первой строки таблицы ниже. 
    
    Выберите в раскрывающихся списках значения параметров **Type** (Тип) и **Routing Policy** (Политика маршрутизации). 
    
    |**Name**|**Тип**|**Alias (Псевдоним)**|**TTL (Seconds) (Срок жизни, в секундах)**|**Value (Значение)**|**Routing Policy (Политика маршрутизации)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV  указатель служб|No (Нет)|300|100 1 443 sipdir.online.lync.com. **Это значение должно заканчиваться точкой (.).**><br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |Simple (Простая)|
    |_sipfederationtls. _tcp|SRV  указатель служб|No (Нет)|300|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.               |Простое|
   
    ![AWS — BP — configure – 5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Нажмите кнопку **Создать**.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. Добавьте вторую запись SRV.
    
    На странице " **размещенные зоны** " выберите **создать набор записей**, создайте запись, используя значения из следующей строки таблицы, а затем еще раз нажмите кнопку **создать** , чтобы завершить эту запись. 
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
