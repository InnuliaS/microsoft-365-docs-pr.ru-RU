---
title: Управление профилями выставления счетов
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Узнайте, как профили выставления счетов поддерживают накладные.
keywords: Профиль выставления счетов, счета, расходы, управляемые расходы
ms.openlocfilehash: 2979909e3b916cc4bc8704f32a821b13fa6090e0
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741710"
---
# <a name="manage-billing-profiles"></a>Управление профилями выставления счетов

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Для коммерческих клиентов, которые покупают продукты и услуги от Майкрософт, профили выставления счетов позволяют настраивать, какие товары включаются в счет, а также как вы оплачиваете счета.

Профили выставления счетов включают следующие сведения:

- Счет для выставления **счетов** &ndash; Имя учетной записи выставления счетов, с которой связан профиль
- **Способы оплаты** &ndash; Кредитные или дебетовые карты, банковские счета, проверка или передача данных по кабелю
- **Контактные данные** &ndash; Адрес выставления счетов и имя контакта
- Параметры накладных **Invoice settings** &ndash; Валюта, основанная на стране счета выставления счетов, необязательный номер ЗП и возможность получения счетов в виде вложений электронной почты
- **Разрешения** &ndash; Разрешения, позволяющие изменить профиль выставления счетов, счета оплаты или использовать метод оплаты в профиле выставления счетов, чтобы совершать покупки

Использование профилей выставления счетов для управления покупками и настройки счетов. Для продуктов, приобретенных в профиле выставления счетов, создается ежемесячный счет. Вы можете настроить накладную, например, обновить номер заказа на покупку и настройку накладных по электронной почте.

Профиль выставления счетов автоматически создается для счета выставления счетов при первой покупке. Вы можете создать профили выставления счетов на странице <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Профили выставления счетов</a> , чтобы настроить дополнительные счета. Например, вы можете использовать различные профили выставления счетов при совершении покупок для каждого отдела в Организации. На следующей дате выставления счетов вы получите счет для каждого профиля выставления счетов.

## <a name="billing-profile-roles"></a>Роли профиля выставления счетов

Роли в профилях выставления счетов имеют разрешения на управление покупками и просмотр и управление накладными. Назначьте эти роли пользователям, которые отслеживают, упорядочивают и платят по накладным, например участникам группы закупаемой продукции в Организации.

| Role                          | Описание                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Владелец профиля выставления счетов         | Управление всеми для профиля выставления счетов                                           |
| Корреспондент профиля выставления счетов   | Управление всеми, кроме разрешений, в профиле выставления счетов                         |
| Средство чтения профилей выставления счетов        | Представление "только для чтения" всего в профиле выставления счетов                                 |
| Менеджер по накладным               | Просмотр и оплата ведомостей, а так же доступное только для чтения представление всех элементов в профиле выставления счетов   |

## <a name="view-billing-profiles"></a>Просмотр профилей выставления счетов

1. В центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Счета и платежи</a>.

2. Выберите **Профили выставления счетов**, а затем выберите из списка профиль выставления счетов.

    - На вкладке **Обзор** можно изменить сведения профиля выставления счетов, а также включить или отключить отправку счета по электронной почте.

    - На вкладке **разрешения** можно назначить роли пользователям для оплаты счетов.

    - На вкладке **Azure Credit Balance** клиенты Azure могут просматривать историю сальдо проводок для кредитов Azure, используемых этим профилем выставления счетов.

    - На вкладке **кредиты Azure** клиенты Azure могут просматривать список кредитов Azure, связанных с этим профилем выставления счетов, и даты их истечения срока действия.

    > [!NOTE]
    > Если у вас нет кредитов в Azure, вы не увидите вкладки **Azure кредитный баланс** или **Azure кредиты** .

## <a name="need-help-contact-support"></a>Нужна помощь? Обратитесь за поддержкой.

Если у вас возникли вопросы или вам нужна помощь по работе с платами Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Создайте запрос в службу поддержки с поддержкой Azure</a>.

Если у вас возникли вопросы или вам нужна помощь по профилю выставления счетов в центре администрирования Microsoft 365, [обратитесь в службу поддержки продуктов для бизнеса](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
