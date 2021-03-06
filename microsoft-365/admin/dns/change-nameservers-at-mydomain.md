---
title: Изменение серверов доменных имен для настройки Майкрософт с параметром MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Узнайте, как настроить Майкрософт для управления записями DNS в пользовательском домене на MyDomain.
ms.openlocfilehash: d8fc61c3adbe8b5b865bd82b8c4e0944198921e7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400633"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a>Изменение серверов доменных имен для настройки Майкрософт с параметром MyDomain

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**.
  
Если вы хотите, чтобы корпорация Майкрософт управляла своими записями DNS, следуйте приведенным ниже инструкциям. (При желании вы можете [управлять всеми своими записями Microsoft DNS на сервере mydomain](create-dns-records-at-mydomain.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки

Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.
  
> [!NOTE]
> Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже. 
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview** (Обзор) выберите **DNS**.
    
5. В раскрывающемся списке **Modify** (Изменить) выберите **TXT/SPF Record** (Запись TXT/SPF).
    
6. В разделе **Content** (Контент) в поле для новой записи введите (или скопируйте и вставьте) значение из приведенной ниже таблицы.
    
||
|:-----|
|**Контент** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Примечание**: это пример. Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы. [Как его найти?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Нажмите кнопку **Add** (Добавить).
    
8. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.
  
Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.
  
1. В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.

    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Verify domain** (Проверка домена) выберите **Verify** (Проверить).
    
> [!NOTE]
> Обычно на применение изменений DNS требуется около 15 минут. Однако иногда распространение изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникает проблема с обменом почтовыми сообщениями или другие неполадки, см. статью [Поиск и устранение проблем после добавления домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Изменение записей сервера доменных имен

Чтобы завершить настройку домена с помощью корпорации Майкрософт, измените записи NS своего домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Майкрософт. Эта настройка позволяет настроить Microsoft для обновления записей DNS домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.
  
> [!CAUTION]
> Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Майкрософт, затрагиваются все службы, связанные с вашим доменом. Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain.* com) после внесения этого изменения будет начато до корпорацию Майкрософт. 
  
> [!IMPORTANT]
> В приведенной ниже процедуре показано, как удалить из списка все остальные, нежелательные серверы имен, а также как добавить правильные серверы имен, если их еще нет в данном списке.<br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. Чтобы приступить к работе, откройте страницу со своими доменами на сайте MyDomain по предоставленной ссылке. Сначала вам потребуется [выполнить вход](https://www.mydomain.com/controlpanel).
    
2. В разделе **My Favorites** (Избранное) выберите **Domain Central** (Центральный домен).
    
3. В поле **Domain** (Домен) выберите доменное имя, которое хотите изменить.
    
4. В строке **Overview (обзор** ) выберите **серверов доменных имен**.
    
    ![MyDomain — BP — redelegate — 1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. В разделе **Update Name Servers** (Обновление серверов доменных имен) выберите **Use different name servers** (Использовать другие серверы доменных имен).
    
    ![MyDomain — BP — redelegate — 1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. В зависимости от того, есть ли у вас уже серверов доменных имен на отображаемой странице, перейдите к одной из двух указанных ниже процедур.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Если указаны правильные серверы доменных имен

- Если правильные серверы доменных имен уже указаны, пропустите этот шаг.
    
    ![MyDomain — BP — redelegate — 1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Если правильные серверы доменных имен не указаны

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (То есть удалите только те текущие серверов доменных имен, которые *не* называются **NS1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**или **NS4.BDM.microsoftonline.com**.) 
  
1. Удалите существующие серверы доменных имен, выбирая соответствующие записи в поле **Nameserver:** (Сервер доменных имен:) и нажимая на клавиатуре клавишу **DELETE**. 
    
    ![MyDomain — BP — redelegate — 1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Дважды нажмите кнопку **Добавить** , чтобы добавить две новые строки серверов доменных имен. 
    
    ![MyDomain — BP — redelegate — 1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. В поля для записей введите (или скопируйте и вставьте) значения для серверов доменных имен из таблицы ниже.
    
|||
|:-----|:-----|
|**Nameserver 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MyDomain — BP — redelegate — 1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Нажмите кнопку **Сохранить**.
    
    ![MyDomain — BP — redelegate — 1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> На распространение изменений, внесенных вами в записи серверов имен, в системе DNS по всему Интернету может потребоваться несколько часов. После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом. 
