---
title: Поиск и устранение неполадок после добавления домена и записей DNS
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Сведения о том, как отслеживать все проблемы, возникающие при настройке настраиваемого домена, убедившись, что DNS-записи настроены правильно.
ms.openlocfilehash: e3c66e10a673d840cfddad81a057739b6dfac721
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399948"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Поиск и устранение неполадок после добавления домена и записей DNS

 Если вы не нашли то, что вы ищете, обратитесь к разделу **[вопросы и ответы по доменам](../setup/domains-faq.md)**. 
  
Настройка домена для работы с Microsoft 365 может быть проблематичной. Система DNS работает с нитпикки, а Настройка DNS для домена влияет на важные бизнес-действия, например на электронную почту.

> [!NOTE]
> Чтобы проверить наличие проблем с доменом, необходимо проверить его состояние. Перейдите в раздел **Настройка**  >  **доменов** и просмотрите уведомления в столбце **состояние** . Если отображается сообщение о неполадке, выберите пункт Дополнительные действия (три точки), а затем нажмите кнопку **проверить работоспособность**. В открывшейся области будут описаны все проблемы, возникающие при работе с доменом.
  
## <a name="whats-going-on"></a>Почему?

- [Не удается проверить ваш домен?](#cant-verify-your-domain)
    
- [Outlook не работает?](#outlook-isnt-working)
    
- [Сообщения электронной почты для всех пользователей были переключены в Microsoft 365, и вы хотите, чтобы вы хотели переключить электронную почту?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Не можете подтвердить состояние учетной записи без дохода или учебной учетной записи?](#cant-confirm-non-profit-or-school-account-status)

- [Службы не работают с вашим доменом?](#services-not-working-with-your-domain)
    
- [Доступ к веб-сайту не работает?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Не удается проверить свой домен?
<a name="BKMK_verify"> </a>

Вот несколько причин, по которым может не удаваться проверить домен:
  
1. **Проверочная запись неправильная.** Убедитесь, что вы скопировали и вставили точное значение в проверочную запись TXT на узле DNS. Часто пользователи забывают указать "MS =". Эта часть тоже нужна! 
    
2. **Запись не была сохранена.** На некоторых узлах DNS необходимо выполнить дополнительное действие для сохранения файла зоны (в котором хранится запись DNS), чтобы он обновился в Интернете. Убедитесь, что вы сохранили изменения, чтобы Microsoft 365 мог просматривать и проверять запись. 
    
3. **Запись не обновилась в Интернете.** Обычно новая запись становится доступна через несколько минут, но иногда ее обновление может занять до нескольких часов. 
    
## <a name="outlook-isnt-working"></a>Не работает Outlook?
<a name="BKMK_OutlookBroken"> </a>

Если вы настроили свою запись MX и другие записи DNS для домена правильно, но почта не работает, мы поможем [устранить неполадки с Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Сообщения электронной почты для всех пользователей были переключены в Microsoft 365, и вы хотите, чтобы вы хотели переключить электронную почту?
<a name="BKMK_EmailSwitched"> </a>

Когда вы добавляете свой домен в Microsoft 365, обычно запись MX вашего домена обновляется (или с помощью Microsoft 365), чтобы она ссылалась на Microsoft 365, а все сообщения, отправленные в этот домен, появятся в Microsoft 365. Перед изменением записи MX убедитесь, что вы создали почтовые ящики в Microsoft 365 для всех, у которых есть электронная почта в вашем домене.
  
Что делать, если вы не хотите перемещать электронную почту для всех пользователей вашего домена в Microsoft 365? Вы можете выполнить действия для [пилотного развертывания Microsoft 365 с использованием всего нескольких адресов электронной почты](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Не можете подтвердить состояние учетной записи без дохода или учебной учетной записи?
<a name="BKMK_validateAcct"> </a>

Существует несколько сценариев, когда необходимо только проверить домен организации и не настраивать какие бы то ни было службы. Например, чтобы доказать, что в Microsoft 365 ваша организация соответствует подписке учебного заведения.
  
Ознакомьтесь с рекомендациями, приведенными в статье [Проверка домена Microsoft 365 на получение сведений о владении, некоммерческих или образовательных состояниях, а также активацию Yammer,](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) чтобы убедиться, что все необходимые действия выполнены. Для каждой ситуации это немного другое. 
  
## <a name="services-not-working-with-your-domain"></a>Службы не работают с вашим доменом?
<a name="BKMK_Test"> </a>

Мы поможем вам выявить проблемы с настройкой DNS для домена. Средство устранения неполадок с доменами в Microsoft 365 покажет вам все записи, которые необходимо исправить, и точно то, для чего нужно задать записи. 

> [!TIP]
> DNS настроена правильно, но почта не работает в Outlook на рабочем столе? Узнайте о [различных сценариях обработки почты, которые можно получить с помощью Microsoft 365](https://www.microsoft.com/?ref=go) , чтобы убедиться, что вы правильно настроили свои бизнес. Дополнительную помощь по устранению неполадок с электронной почтой можно найти здесь: [Устранение неполадок в Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Ваш веб-сайт недоступен?
<a name="BKMK_Website"> </a>

Если вы устранили все неполадки DNS, но у вас по-прежнему возникают проблемы, попробуйте одно из указанных ниже действий.
  
- Пользователи не могут войти на ваш веб-сайт в www.mydomain.com: [Диагностика неполадок веб-сайта](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Вы не можете обновить запись A или CNAME для ссылки на ваш веб-сайт: [Обновление настраиваемых записей DNS в Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
