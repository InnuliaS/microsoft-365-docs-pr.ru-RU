---
title: Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как удалять пользователей с портала "Пользователи с ограниченным доступом" в Office 365. Пользователи попадают на портал "Пользователи с ограниченным доступом" за отправку исходящей нежелательной почты. Обычно это происходит в результате компрометации учетных записей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726728"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом" в Office 365

Если пользователь превысит один из лимитов отправки исходящей почты, указанных в разделе [лимитов служб](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) или [политик исходящей нежелательной почты](configure-the-outbound-spam-policy.md), он потеряет возможность отправлять почту, но по-прежнему сможет принимать ее.

В этом случае пользователь будет добавлен на портал "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям. Если он попытается отправить электронное письмо, оно вернется в отчете о недоставке (также называемом сообщением о недоставке) с кодом ошибки [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) и следующим текстом:

> "Не удалось доставить сообщение, так как система не распознала вас как допустимого отправителя. Причина проблемы чаще всего связана с предположительной рассылкой нежелательной почты с вашего электронного адреса. Поэтому с него не разрешено отправлять сообщения.  Обратитесь за помощью к администратору электронной почты. Удаленный сервер вернул ошибку "550 5.1.8. Отказано в доступе: недопустимый отправитель".

Администраторы могут удалять пользователей с портала "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям или в Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>. Перейдите на страницу **Пользователи с ограниченным доступом** по ссылке <https://protection.office.com/restrictedusers>.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.

  - Чтобы удалить каких-либо пользователей из портала «Пользователи с ограниченным доступом», вы должны быть участником одной из следующих групп ролей:

    - **Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Чтобы получить доступ только для чтения к порталу «Пользователи с ограниченным доступом», вы должны быть участником одной из следующих групп ролей:

    - **Читатель сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Если отправитель превысил лимит сообщений исходящей почты, это свидетельствует о возможной компрометации учетной записи. Прежде чем удалить пользователя с портала "Пользователи с ограниченным доступом", выполните необходимые действия, чтобы восстановить контроль над его учетной записью. Дополнительные сведения см. в статье [Реагирование на компрометацию учетной записи электронной почты в Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Удаление пользователя из списка "Пользователи с ограниченным доступом" с помощью Центра безопасности и соответствия требованиям

1. В Центре безопасности и соответствия требованиям последовательно выберите пункты **Управление угрозами** \> **Просмотр** \> **Пользователи с ограниченным доступом**.

2. Найдите и выберите пользователя, которого необходимо разблокировать. В столбце **Действия** щелкните **Разблокировать**.

3. Откроется всплывающее окно со сведениями об учетной записи, которой запрещено отправлять почту. Просмотрите рекомендации, чтобы убедиться, что вы принимаете надлежащие меры в случае фактической компрометации учетной записи. По завершении нажмите кнопку **Далее**.

4. На следующем экране представлены рекомендации по предотвращению компрометации в будущем. Включение многофакторной проверки подлинности (MFA) и изменение паролей обеспечивают хорошую защиту. По завершении нажмите кнопку **Разблокировать пользователя**.

5. Нажмите кнопку **Да**, чтобы подтвердить изменение.

   > [!NOTE]
   > Для снятия ограничений может потребоваться 30 минут или более.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Проверка параметров оповещений для пользователей с ограниченным доступом

Используемая по умолчанию политика оповещений **Пользователи, которым запрещено отправлять почту** автоматически уведомляет администраторов о введении запрета на отправку исходящей почты для пользователя. Вы можете проверить эти параметры и добавить дополнительных пользователей, которым необходимо отправлять уведомления. Дополнительные сведения о политиках оповещений см. в статье [Политики оповещений в Центре безопасности и соответствия требованиям](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Чтобы оповещения работали, должен быть включен поиск в журнале аудита. Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

1. В Центре безопасности и соответствия требованиям последовательно выберите пункты **Оповещения** \> **Политики оповещений**.

2. Найдите и выберите оповещение **Пользователю запрещена отправка электронной почты**.

3. В открывшемся окне проверьте или настройте указанные ниже параметры.

   - **Состояние**: убедитесь, что оповещение включено ![Переключатель включен](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Получатели электронной почты**: щелкните **Изменить** и в открывшемся окне **Изменение получателей** проверьте или настройте указанные ниже параметры.

     - **Отправлять уведомления по электронной почте**: убедитесь, что флажок установлен (**Включен**).

     - **Получатели электронной почты**: по умолчанию используется значение **TenantAdmins** (то есть участники группы **Глобальный администратор**). Чтобы добавить дополнительных получателей, щелкните пустую область в поле. Отобразится список получателей, после чего можно начать вводить имя, чтобы отфильтровать список и выбрать нужного получателя. Чтобы удалить существующего получателя из поля, щелкните значок ![Удалить](../../media/scc-remove-icon.png) рядом с именем этого получателя.

     - **Ограничение на ежедневные уведомления**: по умолчанию используется значение **Без ограничений**, но вы можете выбрать ограничение для максимального количества уведомлений в день.

     Выполнив необходимые действия, нажмите кнопку **Сохранить**.

4. Вернитесь в окно **Пользователю запрещена отправка электронной почты** и щелкните **Закрыть**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Просмотр пользователей в списке "Пользователи с ограниченным доступом" и удаление их из этого списка с помощью Exchange Online PowerShell

Чтобы отобразить список пользователей, которым запрещено отправлять почту, выполните следующую команду:

```powershell
Get-BlockedSenderAddress
```

Чтобы отобразить сведения об определенном пользователе, выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Подробные сведения о синтаксисе и параметрах см. в статье [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).

Чтобы удалить пользователя из списка "Пользователи с ограниченным доступом", выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Подробные сведения о синтаксисе и параметрах см. в статье [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).
