---
title: Вопросы и ответы о доменах
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Дополнительные сведения о доменах можно найти в ответах на часто задаваемые вопросы.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068107"
---
# <a name="domains-faq"></a>Вопросы и ответы о доменах

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

В этой статье приведены ответы на часто задаваемые вопросы о доменах в Microsoft 365.

Если вы не нашли ответ на свой вопрос, оставьте комментарий и мы добавим его в список.

В этой статье

- [Что такое приоритет записей MX?](#what-is-mx-priority)
- [Как проверить записи SPF для домена?](#how-can-i-validate-spf-records-for-my-domain)
- [Что такое доменное имя?](#what-is-a-domain-name)
- [Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Как задать или изменить домен по умолчанию в Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Почему у меня есть домен onmicrosoft.com?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Почему у меня есть домен "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain)
- [Как проверить статус некоммерческой или образования?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Что такое приоритет записей MX?

Почта доставляется на сервер почтового обменника, который имеет наименьший номер предпочтения (наивысший приоритет), поэтому у записи MX, которая используется для маршрутизации, должен быть наименьший номер предпочтения (обычно 0) или  *высокий*  приоритет. 
  
- При создании записи MX большинство поставщиков услуг размещения DNS требуют указать номер предпочтения.
    
- В некоторых службах соответствующий параметр называется  *предпочтением*  , а в некоторых   *приоритетом*  . 
    
- В некоторых требуется указать число, а в некоторых  выбрать значение  *Низкий*  ,  *Средний*  или  *Высокий*  . 
    
- Если у вас только одна запись MX, подойдет любое значение.
    
- Если у вас есть несколько таких записей, убедитесь, что запись MX, используемая для маршрутизации почты, имеет более высокий приоритет, чем та, которая применяется для подтверждения владения доменом.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Как проверить записи SPF для домена?

Важно иметь или создать **только одну запись TXT для SPF**. Если у вас уже есть запись SPF, добавьте к ней новые значения Microsoft 365, а не создайте новую. После добавления или обновления записи SPF для электронной почты Майкрософт необходимо убедиться в правильности синтаксиса с помощью одного из следующих средств: 
  
- [Инструменты для тестирования записей SPF](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Веб-интерфейс Dig](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Что такое доменное имя?

A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
Использование собственного домена, например "**роб \@ contoso.com**" с Microsoft 365, поможет вам создавать сведения о доходе и распознавание для вашей фирменной символики. 
  
Вы можете [приобрести домен в Microsoft 365, а также настроить его автоматически](../get-help-with-domains/buy-a-domain-name.md)или приобрести у регистратора доменных имен, которым вы уже владеете.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Что произойдет, если поставщик DNS не поддерживает некоторые типы записей?

Если вы управляете собственными DNS-записями, а узел DNS не поддерживает все записи DNS, необходимые для Microsoft 365, некоторые функции Microsoft 365 не будут работать. Мы рекомендуем передать домен регистратору, который поддерживает все необходимые записи DNS.
  
Поставщики, поддерживающие все необходимые записи DNS:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Как задать или изменить домен по умолчанию в Microsoft 365?

Вы должны иметь по крайней мере один личный домен, добавленный в Microsoft 365, прежде чем вы сможете выбрать домен по умолчанию.

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).

::: moniker-end
    
2. На странице **Domains (домены** ) выберите домен, который требуется установить в качестве значения по умолчанию для новых адресов электронной почты. 
    
3. Нажмите кнопку **По умолчанию**.
    
::: moniker range="o365-worldwide"

Изменить имя первоначального домена  *.onmicrosoft.com*  невозможно. 

::: moniker-end

::: moniker range="o365-germany"

Имя начального домена *onmicrosoft.de* нельзя изменить. 

::: moniker-end

::: moniker range="o365-21vianet"

Имя начального домена *Partner.onmschina.CN* нельзя изменить. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Можно ли добавить настраиваемые поддомены или несколько доменов в Microsoft 365?

::: moniker range="o365-worldwide"

Да. Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора. Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.

::: moniker-end

::: moniker range="o365-germany"

Нет! Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора. Если вы разработаны Майкрософт для управления параметрами DNS с записями NS или если вы приобрели домен от корпорации Майкрософт, вы не сможете добавить поддомены.

::: moniker-end

::: moniker range="o365-21vianet"

Нет! Чтобы добавить поддомены, необходимо управлять собственными параметрами DNS на веб-сайте регистратора. Если вы разпозволяете 21Vianet управлять параметрами DNS с записями NS, вы не можете добавлять поддомены.

::: moniker-end

Как правило, в подписку Microsoft 365 можно добавить до 900 доменов.
  
Например, вы можете добавить домены contoso.com и contosomarketing.com, а затем  поддомены www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com и т. д.
  
При добавлении дочернего домена он автоматически проверяется в соответствии с проверяемым родительским доменом.
  
При добавлении нескольких доменов в Microsoft 365 можно разместить любую службу (например, электронную почту) для всех добавленных доменов.  *Когда вы изменяете электронную почту на Microsoft 365, обновляя запись MX в домене, все сообщения, отправленные на этот домен, начнут приходить в Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Если вы добавили домен contoso.com в подписку на Microsoft 365, вы также можете добавить xyz.contoso.com дочернего домена в другую организацию Microsoft 365. При добавлении поддомена вам будет предложено добавить запись TXT в поставщик услуг хостинга DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Почему у меня есть домен onmicrosoft.com?

Microsoft 365 создает домен, например *contoso.onmicrosoft.com*, при регистрации в службе. Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.com*. 
  
 **Если вы хотите, чтобы ваша электронная почта выглядела как *Сергей \@ contoso.com*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в статье [Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если у вас уже есть. 
  
- **Домен onmicrosoft невозможно переименовать после регистрации.** Например, если первоначально вы выбрали домен fourthcoffee.onmicrosoft.com, его не удастся переименовать в fabrikam.onmicrosoft.com. Чтобы использовать другой домен onmicrosoft.com, вам потребуется начать новую подписку с помощью Microsoft 365. 
    
- **Вы не можете переименовать URL-адрес сайта группы.** URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.com. К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы. 
    
- **Домен onmicrosoft невозможно удалить.** Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки. Несмотря на это, вы можете им не пользоваться, если добавите личный домен. 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Почему у меня есть домен "onmicrosoft.de"?

Microsoft 365 создает домен, например *contoso.onmicrosoft.de*, при регистрации в службе. Идентификатор пользователя, который вы создаете при регистрации, включает домен, например *Alan@contoso.onmicrosoft.de*. 
  
 **Если вы хотите, чтобы ваша электронная почта выглядела как *Alan@contoso.de*:** [купите домен](../get-help-with-domains/buy-a-domain-name.md) или просто выполните действия, описанные в [статье Добавление пользователей и доменов в Microsoft 365](add-domain.md) , если вы уже являетесь ее владельцем. 
  
- **Домен onmicrosoft невозможно переименовать после регистрации.** Например, если исходный домен, который вы выбрали, был fourthcoffee.onmicrosoft.de, его нельзя изменить на fabrikam.onmicrosoft.de. Чтобы использовать другой домен onmicrosoft.de, вам потребуется начать новую подписку с помощью Microsoft 365. 
    
- **Вы не можете переименовать URL-адрес сайта группы.** URL-адрес сайта группы основан на вашем доменном имени onmicrosoft.de. К сожалению, из-за способа работы архитектуры SharePoint Online нельзя переименовать сайт группы. 
    
- **Домен onmicrosoft невозможно удалить.** Microsoft 365 необходимо обойти, так как она используется в фоновом режиме для вашей подписки. Несмотря на это, вы можете им не пользоваться, если добавите личный домен. 
    
Вы можете продолжить работу с исходным доменом onmicrosoft.de, даже после добавления домена. Он будет поддерживаться в электронной почте и других службах.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Как проверить статус некоммерческой или образования?

1. В [центре администрирования](https://docs.microsoft.com/microsoft-365/admin/admin-home) выберите пункт **Настройка** , чтобы запустить мастер. (Сначала войдите в Microsoft 365.) 
    
2. Чтобы стать администратором учебного заведения, выберите параметр **становится** администратором в Microsoft 365. 
    
3. Вам будет предложено добавить запись DNS в формате TXT на веб-сайт узла DNS для вашего домена. Почему? Так как при входе на узел DNS и добавлении записи в домен вы подтверждаете в Microsoft 365, что вы владеете доменным именем.
    
4. После добавления записи вы вернетесь на портал Microsoft 365 и подтвердите, что она добавлена, поэтому Microsoft 365 может проверить.
    
У вас есть некоммерческие и хотите получить Microsoft 365? [Убедитесь, что ваша организация](https://www.microsoft.com/en-us/nonprofits/eligibility) поддается уточнению и зарегистрируйте ее. 
  
Хотите узнать больше о том, как стать администратором учебного заведения? [Узнайте больше об этом](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).