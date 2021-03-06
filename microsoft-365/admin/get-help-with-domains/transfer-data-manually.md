---
title: Ручная передача данных между двумя учетными записями
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Узнайте, как вручную перенести данные между двумя учетными записями Microsoft 365, когда вы изменили план или название компании, или объединили несколько подписок в одну.
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780173"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Ручная передача данных между двумя учетными записями

Подготовьтесь к развертыванию сливес и блокированию определенного времени в календаре: передача данных между двумя учетными записями Microsoft 365 — это процесс, выполняемый вручную, сложный и длительный процесс. Это не автоматическая процедура. Мы поможем вам приступить к работе.
  
> [!CAUTION]
> Во время процесса не будет работать Электронная почта, Skype для бизнеса и общедоступный веб-сайт, размещенный в Microsoft 365. Пользователи получат новые имена и пароли, и им придется сбросить параметры Outlook.

**Переносите данные вручную, следуя инструкциям в этой статье, только в указанных ниже случаях.**
  
- Вам требуется перейти на план из другого семейства.

- Название вашей организации изменилось, и вы решили создать новую подписку и перенести данные, так как хотите использовать другие доменные имена.

- Необходимо объединить несколько подписок в одну.

> [!IMPORTANT]
> Если вам нужно [изменить план подписки](../../commerce/subscriptions/switch-to-a-different-plan.md) и вы можете использовать для этого мастер переключения планов и если вы хотите перейти на новый план в том же семействе (даже если мастер переключения планов не работает), вам не потребуется вручную переносить данные, а простоя не возникнет.

|**Задачи**|**Действия**|
|:-----|:-----|
|Приобретите план, на который вы хотите перейти.  <br/> |When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com. You need to use a different  *yourcompany*  name than you did for any existing subscriptions.  <br/> > [!NOTE]>  После отмены подписки исходные доменные имена, в которых используется название  *kompania*  , обычно освобождаются только через несколько месяцев. Даже если вы планируете сохранить все ваши данные из старой подписки на Microsoft 365 и отменили эту подписку, старое значение *yourcompany* не будет немедленно доступно для использования в новой подписке.           |
|Удалите личный домен из старой подписки на Microsoft 365.  <br/> | Выполните [необходимые действия перед удалением домена](remove-a-domain.md), чтобы удалить доменное имя из адресов электронной почты пользователей, а также удалить записи DNS, связанные с электронной почтой и Lync, для личного домена. Если вы размещаете общедоступный веб-сайт в Microsoft 365, вам также потребуется удалить запись CNAME, указывающую на нее.  <br/> > [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users. When you remove the DNS records for Lync, Lync will stop working. And after you remove the CNAME record that points to your public website, it will not be available.           [Remove the domain](remove-a-domain.md) .  <br/> |
|Настройте личный домен для новой подписки и создайте пользователей.  <br/> | Настройте новую подписку, в том числе создав необходимые записи DNS для личного домена.  <br/>  Создайте пользователей с адресами электронной почты в вашем личном домене.  <br/> |
|Перенесите данные из старой подписки в новую.  <br/> | Войдите в обе учетные записи в разных окнах браузера:  <br/>  Right-click the Internet Explorer icon, and open two InPrivate browser windows. You can use different credentials in the two windows to sign in on both accounts.  <br/> [Перенос параметров администрирования из одной подписки в другую](#email) <br/> [Перенос структуры и данных сайта группы](#transfer-team-site-structure-and-data) <br/> [Перенос общедоступного веб-сайта из одной подписки в другую](#transfer-a-public-website-between-subscriptions) <br/> [Перенос параметров администрирования из одной подписки в другую](#email) <br/> |
|Отмените подписку на план, с которым вы сделали это, позвонив в службу поддержки Майкрософт для Microsoft 365.  <br/> | Убедитесь, что новая подписка работает, а все данные перенесены.  <br/>  [Обратитесь в службу поддержки пользователей](../contact-support-for-business-products.md) , чтобы отменить старую подписку.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Перенос параметров администрирования из одной подписки в другую

Откройте перечисленные ниже страницы для каждой учетной записи и настройте новую учетную запись на основе параметров старой.
  
Если вы переносите данные из Microsoft 365 в Microsoft 365 среднего бизнеса или Microsoft 365 корпоративный, страницы администрирования имеют разную структуру. Просмотрите [видео: введение в Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365/admin/), и перейдите в следующие места, чтобы просмотреть параметры администрирования.
  
Для Microsoft 365 Enterprise и Microsoft 365 для среднего бизнеса:
  
|**Расположение**|**Цель**|
|:-----|:-----|
|**Администратор** \> **Microsoft 365** \> **Параметры службы** <br/> |Выберите каждую вкладку для параметров почты, сайтов, Lync, пользовательского программного обеспечения, паролей, сообщества, управления правами и мобильных устройств.  <br/> |
|**Администратор** \> **Exchange** <br/> | Параметры Exchange Online  <br/> |
|**Администратор** \> **SharePoint** <br/> | Параметры SharePoint Online  <br/> |
|**Администратор** \> **Skype для бизнеса** <br/> |Дополнительные параметры Skype для бизнеса  <br/> |

Для Microsoft 365 для малого бизнеса
  
|**Расположение**|**Цель**|
|:-----|:-----|
|**Администратор** \> **Управление параметрами и обновлениями в масштабе организации** <br/> |Параметры администрирования  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Перенос общедоступного веб-сайта из одной подписки в другую

Если у вас есть общедоступный веб-сайт, размещенный в Microsoft 365, необходимо сохранить его и создать повторно в новой подписке.
  
> [!NOTE]
> If your public website is hosted at a DNS hosting provider, no changes are required. It will not be affected by your transition.
  
О том, как сохранить содержимое библиотеки документов или списка из среды SharePoint Online в общие папки или на локальный компьютер, читайте в статье [Перенос контента SharePoint Online вручную](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> С помощью приложения для миграции общедоступного веб-сайта невозможно перенести данные в другую подписку.
  
## <a name="transfer-team-site-structure-and-data"></a>Перенос структуры и данных сайта группы

Существует несколько способов сохранения или переноса данных сайта группы:
  
- Вы можете сохранить старый сайт как шаблон и импортировать его на новый сайт.

- Чтобы перенести документы, сначала создайте иерархию на новом сайте вручную. После этого вы сможете одновременно открыть и сайты группы SharePoint, открыть обе библиотеки документов с помощью проводника Windows, а затем скопировать и вставить документы. [Видео: копирование и перемещение файлов библиотеки с помощью команды "открыть в проводнике"](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Для переноса данных списков можно сохранить [шаблон списка](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) и воссоздать с помощью него список на новом сайте.

- Чтобы сохранить библиотеку документов или список контента из среды SharePoint Online (OneDrive для бизнеса или сайты групп) в файловые ресурсы или на локальный компьютер, ознакомьтесь со статьей [сведения о переносе содержимого SharePoint Online вручную](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Перенос данных пользователей из одной подписки в другую

### <a name="email"></a>Отправить по электронной почте:

Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription. They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Данные OneDrive для бизнеса:

Попросите пользователей скопировать или синхронизировать [контент OneDrive для бизнеса на своем компьютере](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd), а затем снова добавить его в новую подписку.
