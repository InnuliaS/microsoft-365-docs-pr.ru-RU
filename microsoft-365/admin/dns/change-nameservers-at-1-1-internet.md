---
title: Изменить серверов доменных имен, чтобы настроить Майкрософт с 1&1 ИОНОС
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Узнайте, как настроить Office 365 под управлением 21Vianet для управления записями DNS, когда 1&1 Интернет-поставщик услуг хостинга DNS.
ms.openlocfilehash: 79870d534e7d825fd59dbbbec54c796227f5faf1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780377"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>Измените серверов доменных имен, чтобы настроить Microsoft 365 с 1&1 ИОНОС

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Следуйте этим инструкциям, если вы хотите, чтобы Microsoft 365 управляла записями DNS Майкрософт 365. (При желании вы можете [управлять всеми своими записями DNS для Microsoft 365 на 1&1 ионос](create-dns-records-at-1-1-internet.md).) 
  

    
## <a name="add-a-txt-record-for-verification"></a>Добавление записи TXT для проверки


Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
1. Чтобы приступить к работе, перейдите на страницу с доменами по адресу 1&1 ИОНОС 1 с помощью [этой ссылки](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. В разделе **Мои домены**выберите **Управление доменами**.
    
3. На странице " **центр домена** " найдите домен, который вы хотите обновить; затем выберите элемент управления **Panel** ( **v**) для этого домена.
    
4. В области **Параметры домена** выберите **изменить параметры DNS**.
    
5. В разделе **txt and SRV Records (записи TXT и SRV** ) выберите **Добавить запись**.
    
    (You may have to scroll down.) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Type (Тип)** <br/> |**Prefix (Префикс)** <br/> |**Name Value (Значение имени)** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **Примечание**: это пример. Используйте здесь собственное значение **Назначение или адрес "указывает на"** из таблицы в Microsoft 365. [Как его найти?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. Нажмите кнопку **сохранить**, а затем **Сохраните** еще раз. 
    
8. В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.
    
9. Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.
    
Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.
  
Если Microsoft 365 обнаружит правильную запись TXT, это значит, что домен проверен.
  
1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).
    
2. На странице **Domains** (Домены) выберите домен, который нужно проверить. 
    
3. На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).
    
4. На странице **Проверка домена** выберите **Проверить**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Если при добавлении записей DNS возникают проблемы с почтовыми сообщениями или другими проблемами, ознакомьтесь со статьей [Поиск и устранение проблем после добавления домена или записей DNS в Microsoft 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Изменение записей сервера доменных имен

Чтобы завершить настройку домена с помощью Microsoft 365, измените записи NS домена в регистраторе доменных имен, чтобы они ссылались на основной и дополнительный серверы имен Microsoft 365. При этом Microsoft 365 настраивается на обновление записей DNS домена. Мы добавим все записи, так что электронная почта, Skype для бизнеса online и общедоступный веб-сайт будут работать в вашем домене и вам больше не придется ничего настраивать.
  
> [!CAUTION]
> Когда вы изменяете записи NS домена так, чтобы они ссылались на серверы имен Microsoft 365, затрагиваются все службы, которые в настоящее время связаны с вашим доменом. Например, все сообщения электронной почты, отправленные в ваш домен (например, rob@ *your_domain* . com), появятся в Microsoft 365 после внесения этого изменения. 
  
Вы готовы изменить записи сервера доменных имен, чтобы Microsoft 365 мог настроить ваш домен? Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).
  
> [!IMPORTANT]
>  В следующей процедуре показано, как удалить любые другие нежелательные серверов доменных имен из списка, а также как добавить правильный серверов доменных имен, если они еще не указаны. > после выполнения действий, описанных в этом разделе, необходимо указать только следующие четыре серверов доменных имен: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Чтобы приступить к работе, перейдите на страницу своих доменов по адресу 1&1 ИОНОС, используя [эту ссылку](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. В разделе **Мои домены**выберите **Управление доменами**.
    
3. На странице " **центр домена** " найдите домен, который необходимо обновить, а затем выберите элемент управления **Panel** ( **v**) для этого домена.
    
4. В области **Параметры домена** выберите **изменить параметры DNS**.
    
5. В разделе **Name Server Settings** (Параметры сервера доменных имен) выберите **Other name servers** (Другие серверы доменных имен).
    
    (Возможно, потребуется прокрутить страницу вниз.)
    
6. В зависимости от того, указаны ли уже серверы доменных имен на странице, которая отображается на экране, воспользуйтесь одной из двух процедур.
    
  - Если на странице **НЕ УКАЗАНЫ** серверы доменных имен, [На странице НЕ УКАЗАНЫ серверы доменных имен](#if-there-are-no-nameservers-already-listed).
    
  - Если на странице **УКАЗАНЫ** серверы доменных имен, [На странице УКАЗАНЫ серверы доменных имен](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>На странице НЕ УКАЗАНЫ серверы доменных имен

1. В поле **Name server 1** (Сервер доменных имен 1) введите (или скопируйте и вставьте) значение из таблицы ниже. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![Ввод значения в поле "сервер имен 1"](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. В раскрывающемся списке **Additional name servers** (Дополнительные серверы доменных имен) выберите **My secondary name servers** (Мои дополнительные серверы доменных имен).
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. В полях **Name server 2, 3, and 4** (Серверы доменных имен 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
|||
|:-----|:-----|
|**Name Server 2** (Сервер доменных имен 2) <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![Ввод значений сервера имен](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. Нажмите кнопку **Сохранить**.
    
    ![Выбор параметра "Сохранить" на странице "Параметры сервера имен"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.
    
    ![Выбор параметра "Сохранить" в диалоговом окне изменения параметров DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом. 
  
### <a name="if-there-are-nameservers-already-listed"></a>На странице УКАЗАНЫ серверы доменных имен

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. Если в полях **Name server** (Сервер доменных имен) указаны другие серверы доменных имен, удалите их: выберите каждый из них и нажмите клавишу **DELETE**. 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. В полях **Name server 1, 2, 3, and 4** (Серверы доменных имен 1, 2, 3 и 4) введите (или скопируйте и вставьте) значения из таблицы ниже. 
    
|||
|:-----|:-----|
|**Name server 1** (Сервер доменных имен 1) <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** (Сервер доменных имен 3) <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** (Сервер доменных имен 4) <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Ввод значений сервера имен](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. Нажмите кнопку **Сохранить**.
    
    ![Выбор параметра "Сохранить" на странице "Параметры сервера имен"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. В диалоговом окне **изменение параметров DNS** нажмите **кнопку Да**.
    
    ![Выбор параметра "Сохранить" в диалоговом окне изменения параметров DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. После этого ваша электронная почта Майкрософт и другие службы будут настроены для работы с вашим доменом. 
  


