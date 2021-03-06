---
title: Переключение планов Microsoft 365 для бизнеса вручную
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: Вручную переключите подписки на Microsoft 365 для бизнеса, приобретая новую подписку и убедившись, что обе подписки указаны и активны.
ms.openlocfilehash: 6d6f28dc45f1d5c8efc7202f1be718f8517cf12f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403202"
---
# <a name="switch-microsoft-365-for-business-plans-manually"></a>Переключение планов Microsoft 365 для бизнеса вручную

::: moniker range="o365-worldwide"
> [!NOTE]
> Эта статья относится к старому центру администрирования. Чтобы просмотреть статью о новом центре администрирования, ознакомьтесь со статьей [изменение планов вручную](change-plans-manually.md). Новый центр администрирования доступен всем администраторам Microsoft 365, и вы можете принять участие в этой группе, выбрав пункт **попробовать новый переключатель центр администрирования** в верхней части домашней страницы. Дополнительные сведения см. в статье [О новом Центре администрирования Microsoft 365](../../admin/microsoft-365-admin-center-preview.md).
::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a>Шаг 1: выбор способа переключения планов

Лучший способ переключить всех пользователей из одного плана в другой — использовать [кнопку Переключить планы](switch-to-a-different-plan.md#use-the-switch-plans-button). Иногда это невозможно. Выполните переключение вручную в следующих случаях:
  
- Отсутствует кнопка **Переключить планы**.

- Если при нажатии кнопки **Переключить планы** нужный план не отображается в списке.

- Если вы не хотите переключать всех пользователей одинаковым образом. Некоторым организациям необходимо, чтобы разные пользователи были подписаны на разные планы. Используйте для этого переключение вручную.

Чтобы продолжить переключение вручную, прочтите [Шаг 2: купить новую подписку](#step-2-buy-a-new-subscription) в этой статье.
  
## <a name="step-2-buy-a-new-subscription"></a>Шаг 2: приобретение новой подписки

 **Уже приобрели?** Если у вас уже есть подписка, в которую вы хотите переместить пользователей, пропустите этот шаг и перейдите к [шагу 3: проверьте новую подписку и лицензии,](#step-3-check-your-new-subscription-and-licenses) приведенные в этом разделе.
  
- ИЛИ -
  
 **Приобретение новой подписки и лицензий:** Выполните действия, описанные в статье [Покупка другой подписки на Microsoft 365 для бизнеса](../buy-another-subscription.md) , чтобы приобрести новую подписку.
  
Убедитесь в том, что покупаете подписку для той же организации, в которой сейчас находятся пользователи. Например, проверьте адреса электронной почты тех пользователей, которых вы хотите переместить. Если в их почтовых адресах есть часть @contoso.com, вам необходимо приобрести новую подписку для contoso.com. Добавьте лицензию для каждого пользователя, которого хотите переместить.
  
 **Если вам нужна помощь по выбору плана**, посетите страницу [сравнение продуктов Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/p/?linkid=842056) или обратитесь в [службу поддержки](../../admin/contact-support-for-business-products.md).
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a>Шаг 3: Проверка новой подписки и лицензий

::: moniker range="o365-worldwide"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Подписки</a>.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Выставление счетов** ><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Выставление счетов** ><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.

::: moniker-end

2. **Проверка того, что обе подписки указаны и активны**

    Должны быть указаны обе подписки: та, из которой вы перемещаете пользователей, и та, в которую вы их перемещаете. Если при первой проверке новой подписки нет, попробуйте еще раз позже. Убедитесь, что обе подписки указаны в разделе **АКТИВНЫЕ**. [Новая подписка не указана или неактивна](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Убедитесь, что лицензий достаточно для всех пользователей**

    Каждому пользователю необходима лицензия, соответствующая подписке. Таким образом, если вы хотите переместить десять пользователей в Microsoft 365 бизнес премиум, вам необходимо убедиться, что у вас есть десять лицензий. 

4. **Нужно больше лицензий для новой подписки?** Перейдите на страницу **подписки** и [купите лицензии на вашу подписку на Microsoft 365 для бизнеса](../licenses/buy-licenses.md).
  
    [Что насчет старых лицензий?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Новая подписка не указана или неактивна

- **Если вы оплачивали подписку на по счету** и потребовалась проверка кредитоспособности, подписка может быть недоступна в течение двух рабочих дней.

- **Если вы приобрели две подписки, и они обе не указаны**, возможно, они были приобретены для разных организаций (разных доменов). Подписки не распространяются за пределы организаций.

- **Если вы знаете, что у вас есть дополнительная подписка**, она не указана здесь или не указана в разделе **активна**, [обратитесь в службу поддержки](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Что насчет старых лицензий?

Лицензии для текущей подписки будут удалены позже. С этого момента вы будете платить только за новые пользовательские лицензии.
  
## <a name="step-4-reassign-licenses"></a>Шаг 4: переназначение лицензий

### <a name="reassign-a-license-for-one-user"></a>Переназначение лицензии для одного пользователя

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. На странице **Активные пользователи** установите флажок рядом с именем пользователя, которому вы хотите назначить лицензию.

3. В правой части в строке **лицензии на продукты** выберите **изменить**.

4. В области **Лицензии на продукты** установите выключатель для лицензии, которую вы хотите назначить, в положение **Вкл.** По умолчанию пользователю автоматически назначаются все службы, связанные с этой лицензией.

    > [!TIP]
    > Чтобы ограничить доступ пользователя к определенным службам, установите выключатель для каждой такой службы в положение **Выкл.** Например, чтобы пользователь имел доступ ко всем имеющимся службам, кроме Skype для бизнеса online, установите выключатель для службы Skype для бизнеса online в положение **Выкл.**
  
5. Установите переключатель в положение **выкл** . для лицензий, которые больше не требуются этому пользователю.

6. В нижней части области **лицензии на продукты** выберите команду **назначить** \> **закрытие** \> **закрытия**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Переназначение лицензий сразу для нескольких пользователей

::: moniker range="o365-worldwide"

1. В центре администрирования перейдите на страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a> .

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

::: moniker-end

2. Установите флажки рядом с именами пользователей, для которых необходимо заменить лицензии.

3. В области **массового действия** выберите пункт **Изменение лицензии продуктов**.

4. In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.

5. Установите выключатель для продукта, лицензию на который вы хотите назначить, в положение **Вкл.**

    > [!TIP]
    > - Чтобы ограничить доступ пользователей к службам, переключитесь в режим **отключения** для служб, которые нужно удалить для этого пользователя. Например, чтобы пользователь имел доступ ко всем имеющимся службам, кроме Skype для бизнеса online, установите выключатель для службы Skype для бизнеса online в положение **Выкл.**
    > - Все предыдущие назначения лицензий для выбранных пользователей будут удалены.
  
6. В нижней части области **Заменить имеющиеся продукты** нажмите **Заменить** \> **Закрыть**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Шаг 5: Отмена подписки или удаление лицензий, которые больше не нужны (необязательно)

Если вы переместили всех пользователей с одной подписки на другую и вам больше не нужна исходная подписка, вы можете [отменить ее](cancel-your-subscription.md).
  
Если вы переместили в другую подписку только часть пользователей, [удалите лицензии](../licenses/remove-licenses-from-subscription.md), которые вам больше не нужны.
  
## <a name="call-support-to-help-you-switch-plans"></a>Обращение в службу поддержки за помощью в переключении планов

[Позвоните в службу поддержки](../../admin/contact-support-for-business-products.md)