---
title: Создание DNS-записей для Майкрософт с помощью DNS на базе Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб DNS для Microsoft на основе Windows.
ms.openlocfilehash: 8f65a397552813f22d4bde82f7fcd51c478d82bd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400248"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Создание DNS-записей для Майкрософт с помощью DNS на базе Windows

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
   
Если у вас есть записи DNS, созданные с помощью DNS на базе Windows, в этой статье приведены сведения о том, как настроить записи для электронной почты, Skype для бизнеса online и т. д.
  
Чтобы приступить к работе, необходимо [найти записи DNS в DNS на основе Windows](#find-your-dns-records-in-windows-based-dns) , чтобы вы могли их обновить. Кроме того, если вы планируете синхронизировать локальную службу Active Directory с Майкрософт, просмотрите [адрес электронной почты, не поддерживающий маршрутизацию, который используется в качестве имени участника-пользователя в локальной службе Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Проблемы с процессом обработки почты или другими проблемами после добавления записей DNS в статье [Устранение неполадок, связанных с изменением имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Поиск DNS-записей в службе DNS на основе Windows
<a name="BKMK_find_your_dns_1"> </a> Перейдите на страницу с записями DNS для вашего домена. Если вы работаете в Windows Server 2008, перейдите к разделу **Start**  >  **Run**. Если вы работаете в Windows Server 2012, нажмите клавишу Windows и **r**. Введите **днсмгмнт. msc**и нажмите кнопку **ОК**. В диспетчере DNS разверните узел ** \<DNS server name\> \> зоны прямого просмотра  **. Выберите домен. You're now ready to create the DNS records.
   
## <a name="add-mx-record"></a>Добавление MX-записи
<a name="BKMK_add_MX"> </a>

Добавьте запись MX, чтобы электронная почта для вашего домена поступила в корпорацию Майкрософт.
- Добавляемая запись MX включает значение (значение **Point to Address** ), которое выглядит примерно так: \<MX token\> . mail.Protection.Outlook.com, где — это значение, \<MX token\> например мскскскскскскскс. 
- В строке "MX" в разделе Exchange Online на странице "Добавление записей DNS" в разделе "адрес" скопируйте значение из списка ссылки. Это значение будет использоваться в записи, которую вы создаете в этой задаче. 
- На странице "Диспетчер DNS" для домена перейдите к разделу **действие**  >  **почтового обменника (MX)**. Чтобы найти эту страницу для домена, ознакомьтесь со статьей [Поиск записей DNS в DNS на базе Windows](#find-your-dns-records-in-windows-based-dns).  
- В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям: 
    - Host Name (Имя узла):  
    - @Address: Вставьте точки в значение адреса, которое вы только что скопировали из Майкрософт.  
    - Преф: 
- Нажмите кнопку **сохранить изменения**.
- Удалите устаревшие записи MX. Если у вас есть старые записи MX для этого домена, которые перенаправляют электронную почту куда-то еще, установите флажок рядом с каждой старой записью, а затем нажмите кнопку **Удалить**  >  **ОК**. 
   
## <a name="add-cname-records"></a>Добавление записей CNAME
<a name="BKMK_add_CNAME"> </a>

Добавьте записи CNAME, необходимые для Майкрософт. Если в Microsoft указаны дополнительные записи CNAME, добавьте их, выполнив указанные ниже действия.
  
> [!IMPORTANT]
> Если у вас есть управление мобильными устройствами (MDM) для Майкрософт, необходимо создать две дополнительные записи CNAME. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (Если MDM нет, вы можете пропустить этот шаг.) 

- На странице "Диспетчер DNS" для домена перейдите к разделу CNAME **Action**  >  **(CNAME)**.
- В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    - Имя узла: автообнаружение
    - Тип: 
    - Кнамеаддресс: autodiscover.outlook.com
- Выберите **O**K.

Добавьте запись CNAME SIP. 
- На странице "Диспетчер DNS" для домена перейдите к разделу CNAME **Action** \> **(CNAME)**. 
- В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    - Имя узла: SIP
    - Тип: CNAME
    - Адрес: sipdir.online.lync.com
- Нажмите кнопку **ОК**.

Добавьте запись автообнаружения CNAME для Skype для бизнеса online.  
- На странице "Диспетчер DNS" для домена перейдите к разделу CNAME **Action** \> **(CNAME)**. В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    - Имя узла: lyncdiscover
    - Тип: CNAME
    - Адрес: webdir.online.lync.com
- Нажмите кнопку **ОК**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Добавление двух записей CNAME для управления мобильными устройствами (MDM) для Майкрософт

> [!IMPORTANT]
> Если у вас есть управление мобильными устройствами (MDM) для Майкрософт, необходимо создать две дополнительные записи CNAME. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (если MDM нет, вы можете пропустить этот шаг.) 
  

Добавьте запись CNAME MDM Enterpriseregistration.  
- На странице "Диспетчер DNS" для домена перейдите к разделу CNAME **Action** \> **(CNAME)**. 
- В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
- Имя узла: enterpriseregistration
- Тип: CNAME
- Адрес: enterpriseregistration.windows.net
- Нажмите кнопку **ОК**. 

Добавьте запись CNAME MDM Enterpriseenrollment. 
-  На странице "Диспетчер DNS" для домена перейдите к разделу CNAME **Action** \> **(CNAME)**. 
-  В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    - Имя узла: enterpriseenrollment
    - Тип: CNAME
    - Адрес: enterpriseenrollment-s.manage.microsoft.com
- Нажмите кнопку **ОК**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT. Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама. Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт. Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений. 
  
Добавьте запись SPF TXT для домена, чтобы предотвратить получение нежелательной почты.
  
- Возможно, для этой записи сохранены другие строки в поле значения TXT (например, строки для маркетинговых рассылок)  это нормально. Не удаляйте их. Заключите добавляемую строку в двойные кавычки, чтобы отделить ее. 
- На странице "Диспетчер DNS" для вашего домена, перейдите **Action** к \> **тексту действия (txt)**. 
-  В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, точно равное приведенным ниже значениям. 
 > [!IMPORTANT]
> В некоторых версиях диспетчера DNS Windows домен мог быть настроен таким образом, что при создании записи TXT в качестве имени дома используется родительский домен. В этом случае при добавлении записи TXT задайте для имени узла пустое значение (без значения) вместо того, чтобы задать для параметра значение @ или доменное имя. 

-  Тип узла: @
-  Тип записи: TXT
-  Адрес: v = spf1 включает:SPF. Protection. Outlook. com-ALL 
         
-  Нажмите кнопку **ОК**.
   
## <a name="add-srv-records"></a>Добавление SRV-записей
<a name="BKMK_add_SRV"> </a>

Добавьте две записи SRV, необходимые для Майкрософт.

Добавьте запись SRV SIP для веб-конференций Skype для бизнеса online  <br/> 
-  На странице "Диспетчер DNS" для вашего домена, перейдите к разделу **действие действия** \> **других новых записей**. 
-   В окне **тип записи ресурса** выберите **расположение службы (SRV)**, а затем нажмите кнопку **создать запись**. 
-   В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    -  Служба: _sip
    -  Протокол: _tls
    -  Приоритет: 100
    -  Вес: 1
    -  Порт: 443
    -  Целевой объект (hostname): sipdir.online.lync.com
-  Нажмите кнопку **ОК**. 


Добавьте запись SRV SIP для федерации Skype для бизнеса online.  
-  На странице "Диспетчер DNS" для вашего домена, перейдите к разделу **действие действия** \> **других новых записей**.  
-  В окне **тип записи ресурса** выберите **расположение службы (SRV)**, а затем нажмите кнопку **создать запись**. 
-   В диалоговом окне **Создание записи ресурса** убедитесь, что в полях задано значение, равное точно следующим значениям:  
    -  Служба: _sipfederationtls
    -  Протокол: _tcp
    -  Приоритет: 100
    -  Вес: 1
    -  Порт: 5061
    -  Целевой объект (hostname): sipfed.online.lync.com
-  Нажмите кнопку **ОК**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Добавление записи для подтверждения владения доменом, если это еще не сделано
<a name="BKMK_verify"> </a>

Прежде чем добавлять записи DNS для настройки служб Майкрософт, корпорация Майкрософт должна подтвердить, что вы являетесь владельцем добавляемого домена. Для этого добавьте запись, выполнив приведенные ниже действия.
  
> [!NOTE]
> Эта запись используется только для проверки принадлежности домена. Она не используется для других целей. 
  

1. Сбор информации от корпорации Майкрософт.  <br/> 
2. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены). 
3. На странице **домены** в столбце **действия** для проверяемого домена нажмите кнопку **запустить программу установки**. 
4. На странице " **Добавление домена в Майкрософт** " выберите пункт **начать шаг 1**. 
5. На странице **Подтвердите, что вы владеете доменом** , в раскрывающемся списке в **разделе инструкции по выполнению этого шага** выберите **Общие инструкции**. 
6. В таблице скопируйте значение Destination (назначение) или точка на адрес. Он понадобится для следующего этапа. Мы рекомендуем копировать и вставлять это значение, чтобы все интервалы оставались правильными.

Добавьте запись TXT. 
-  На странице "Диспетчер DNS" для вашего домена, перейдите **Action** к \> **тексту действия (txt)**. 
-   В диалоговом окне **Создание записи ресурса** нажмите кнопку **изменить**.  
-  В области **настраиваемые имена узлов** диалогового окна **Новая запись ресурса** убедитесь, что для полей задано значение, точно равное приведенным ниже значениям. 

> [!IMPORTANT] 
> В некоторых версиях диспетчера DNS Windows домен мог быть настроен таким образом, что при создании записи TXT в качестве имени дома используется родительский домен. В этом случае при добавлении записи TXT задайте для имени узла пустое значение (без значения) вместо того, чтобы задать для параметра значение @ или доменное имя. 

- Имя узла: @
- Тип: TXT
- Адрес: вставьте назначение или указывает на значение адреса, которое вы только что скопировали из Майкрософт.  
- Нажмите кнопку **ОК**  >  **Done**.

Проверьте свой домен в Microsoft.  
> [!IMPORTANT]
> Подождите около 15 минут, пока созданная запись может быть обновлена в Интернете.       

- Вернитесь в корпорацию Майкрософт и выполните указанные ниже действия, чтобы запросить проверку. В ходе проверки выполняется поиск TXT-записи, добавленной на предыдущем этапе. Если обнаружена правильная TXT-запись, домен успешно проверен.  
1. В центре администрирования перейдите на страницу " **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> установки".
2. На странице **Domains (домены** ) в столбце **Action (действие** ) для проверяемого домена нажмите кнопку **запустить программу установки**. 
3. На странице **Подтвердите, что вы владеете доменом** , нажмите кнопку **Готово, проверить сейчас**, а затем в диалоговом окне подтверждения нажмите кнопку **Готово**. 
   
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Использование адреса электронной почты, не поддерживающего маршрутизацию, в качестве имени участника-пользователя в локальной службе Active Directory
<a name="BKMK_ADNote"> </a>

Если вы планируете синхронизировать локальную службу Active Directory с корпорацией Майкрософт, необходимо убедиться в том, что суффикс имени участника-пользователя Active Directory (UPN) является допустимым суффиксом домена, а не суффиксом домена, таким как @contoso. local. Если вам нужно изменить суффикс UPN, ознакомьтесь со статьей [Подготовка домена, не поддерживающего маршрутизацию, для синхронизации службы каталогов](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
