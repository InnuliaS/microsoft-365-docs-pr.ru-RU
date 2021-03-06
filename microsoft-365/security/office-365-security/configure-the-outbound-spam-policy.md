---
title: Настроить фильтрацию исходящего спама
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как просматривать, создавать, изменять и удалять политики исходящей нежелательной почты в Exchange Online Protection (EOP).
ms.openlocfilehash: 7102f858e0293f2a55fe68a55d4dc2cf3ab38a33
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024586"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Настройка фильтрации исходящих нежелательных сообщений в EOP

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online сообщения исходящей электронной почты, отправляемые через EOP, автоматически проверяются на наличие нежелательной почты и нестандартных действий

Исходящая Нежелательная почта от пользователя в организации обычно указывает на скомпрометированную учетную запись. Подозрительные исходящие сообщения помечаются как спам (независимо от вероятности нежелательной почты или ВЕРОЯТНОсти нежелательной почты) и направляются через [пул доставки с высоким уровнем риска](high-risk-delivery-pool-for-outbound-messages.md) , чтобы обеспечить защиту репутации службы (то есть, храните исходные почтовые серверы Microsoft 365 из списков заблокированных IP-адресов). Администраторы автоматически получают уведомление о подозрительных действиях с исходящей электронной почтой и заблокированных пользователях с помощью [политик оповещений](../../compliance/alert-policies.md).

EOP использует политики исходящей нежелательной почты в рамках общей защиты Организации от спама. Дополнительные сведения см. в статье [Защита от нежелательной почты](anti-spam-protection.md).

Администраторы могут просматривать, изменять и настраивать (но не удалять) политику исходящей нежелательной почты по умолчанию. Для большей детализации можно также создать настраиваемые политики исходящей почты, которые применяются к определенным пользователям, группам или доменам в Организации. Настраиваемые политики всегда имеют приоритет перед политикой по умолчанию, но вы можете изменить приоритеты (порядок применения) своих настраиваемых политик.

Политики исходящей нежелательной почты можно настроить в центре безопасности & соответствия требованиям или в PowerShell (Exchange Online PowerShell для Microsoft 365 организации с почтовыми ящиками в Exchange Online; изолированная оболочка EOP PowerShell для организаций без почтовых ящиков Exchange Online).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a>Политики исходящей нежелательной почты в центре безопасности & соответствия требованиям VS PowerShell

Основными элементами политики исходящей нежелательной почты в EOP являются:

- **Политика фильтрации исходящей нежелательной почты**определяет действия для фильтрации исходящих нежелательной почты вердиктс и параметры уведомлений.

- **Правило фильтрации нежелательной почты**определяет приоритет и фильтры получателей (к которым применяется политика) для политики фильтрации исходящей нежелательной почты.

Различия между этими двумя элементами не очевидны при управлении политиками исходящей нежелательной почты в центре безопасности & соответствия требованиям:

- При создании политики нежелательной почты в центре безопасности & соответствия требованиям вы фактически создаете правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одинаковыми именами.

- При изменении политики исходящей нежелательной почты в центре безопасности & соответствия требованиям параметры, связанные с фильтрами имен, приоритетов, включенных или отключенных и получателей, изменяют правило фильтрации исходящих сообщений о нежелательной почте. Все остальные параметры изменяют соответствующую политику фильтрации нежелательной почты.

- При удалении политики исходящей нежелательной почты из центра безопасности & соответствия требованиям правило фильтрации исходящей почты и связанная политика фильтрации нежелательной почты удаляются.

В Exchange Online PowerShell или отдельном EOP PowerShell разница между политиками фильтрации исходящей спама и правилом фильтрации нежелательной почты очевидна. Управление политиками фильтрации нежелательной почты осуществляется с помощью командлетов ** \* – хостедаутбаундспамфилтерполици** и управление правилами фильтрации нежелательной почты с помощью командлетов ** \* – хостедаутбаундспамфилтерруле** .

- В PowerShell сначала создается политика фильтрации исходящей нежелательной почты, а затем создается правило фильтрации исходящих сообщений, определяющее политику, к которой применяется правило.

- В PowerShell параметры политики фильтрации исходящей нежелательной почты и фильтрации исходящих сообщений можно изменить отдельно.

- При удалении политики фильтрации исходящей нежелательной почты из PowerShell соответствующее правило фильтрации нежелательной почты не удаляется автоматически, и наоборот.

### <a name="default-outbound-spam-policy"></a>Политика исходящих сообщений по умолчанию

Каждая организация имеет встроенную политику исходящей почты с именем Default, которая имеет следующие свойства:

- Политика фильтрации исходящих сообщений по умолчанию применяется ко всем получателям в Организации, несмотря на то, что правило фильтрации исходящих сообщений (фильтры получателей) связано с политикой.

- Для политики с именем "По умолчанию" задано специальное значение приоритета **Самый низкий**, которое невозможно изменить (эта политика всегда применяется последней). Все созданные специальные политики всегда имеют более высокий приоритет, чем политика с именем "По умолчанию".

- Политика с именем "По умолчанию" является стандартной (для свойства **IsDefault** задано значение `True`), и удалить стандартную политику невозможно.

Чтобы повысить эффективность фильтрации исходящей нежелательной почты, можно создать настраиваемые политики нежелательной почты с более жесткими параметрами, которые применяются к определенным пользователям или группам пользователей.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>. Чтобы сразу перейти к странице **Параметры защиты от нежелательной почты**, используйте ссылку <https://protection.office.com/antispam>.

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.

  - Для добавления, изменения и удаления политик исходящей нежелательной почты необходимо быть участником одной из следующих групп ролей:

    - **Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Для доступа только для чтения к политикам исходящей нежелательной почты необходимо быть членом одной из следующих групп ролей:

    - **Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).
    - **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Наши Рекомендуемые параметры политик нежелательной почты приведены в разделе [Параметры политики фильтрации исходящих сообщений EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- [Политики оповещений](../../compliance/alert-policies.md) по умолчанию с именем " **лимит отправки электронной почты" превышены**, **обнаружены подозрительные шаблоны отправки электронной почты**, а пользователь, использующий **отправку сообщений** электронной почты, уже отправит уведомления участникам группы **тенантадминс** (**Глобальные администраторы**) о необычных действиях с исходящей электронной почтой и заблокированных пользователях Дополнительные сведения см. [в статье Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Рекомендуется использовать эти политики оповещений вместо параметров уведомлений в политиках исходящей нежелательной почты.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Использование центра безопасности & соответствия требованиям для создания политик исходящей нежелательной почты

Создание настраиваемой политики нежелательной почты в центре безопасности & соответствия требованиям создает правило фильтрации нежелательной почты и связанную политику фильтрации нежелательной почты одновременно с одним и тем же именем.

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **Параметры защиты от нежелательной почты** нажмите кнопку **создать политику исходящей**почты.

3. В открывшемся диалоговом окне **Политика фильтрации нежелательной почты** настройте указанные ниже параметры.

   - **Имя**. Укажите уникальное, понятное имя политики.

   - **Описание**. Укажите необязательное описание политики.

4. Необязательно Разверните раздел **уведомления** , чтобы настроить дополнительных пользователей, которые должны получать копии и уведомления о подозрительных исходящих сообщениях электронной почты:

   - **Отправлять копии подозрительных исходящих сообщений электронной почты определенным людям**: этот параметр добавляет указанных пользователей в качестве получателей скрытой копии в подозрительные исходящие сообщения.

     > [!NOTE]
     > Этот параметр работает только в политике исходящей нежелательной почты по умолчанию. Она не работает в настраиваемых политиках исходящей почты.

     Чтобы включить этот параметр, выполните указанные ниже действия.

     1. Установите этот флажок, чтобы включить параметр.

     1. Нажмите кнопку **Добавить пользователей**. В появившемся всплывающем окне **Добавление или удаление получателей** :

     1. Введите электронный адрес отправителя. Можно указать несколько адресов электронной почты, разделенных точкой с запятой (;) или по одному получателю в строке.

     1. Щелкните ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) для добавления получателей.

        Повторите эти действия необходимое количество раз.

        Добавленные получатели отображаются в разделе **список получателей** в всплывающем меню. Чтобы удалить получателя, нажмите кнопку ![ удалить кнопку ](../../media/scc-remove-icon.png) .

     1. По завершении нажмите кнопку **Сохранить**.

        Чтобы отключить этот параметр, снимите этот флажок.

   - **Уведомлять определенных людей, если отправитель блокируется из-за отправки нежелательной почты**.

     > [!NOTE]
     > [Политика оповещений](../../compliance/alert-policies.md) по умолчанию с именем "пользователь", которая **ограничена отправкой электронной почты** , уже отправляет уведомления по электронной почте членам группы **тенантадминс** (**Глобальные администраторы**), когда пользователи блокируются из-за превышения ограничений в разделе **ограничения получателей** . Мы рекомендуем использовать политику оповещений, а не этот параметр в политике исходящей нежелательной почты для уведомления администраторов и других пользователей. Инструкции приведены в разделе [Проверка параметров оповещений для пользователей с ограниченным доступом](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). <br/><br/> Этот параметр работает только в политике исходящей нежелательной почты по умолчанию. Она не работает в настраиваемых политиках исходящей почты.

     Чтобы включить этот параметр, выполните указанные ниже действия.

     а. Установите этот флажок, чтобы включить параметр.

     б. Нажмите кнопку **Добавить пользователей**. В появившемся всплывающем окне **Добавление или удаление получателей** :

     в. Введите электронный адрес отправителя. Можно указать несколько адресов электронной почты, разделенных точкой с запятой (;) или по одному получателю в строке.

     г. Щелкните ![Значок добавления](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) для добавления получателей.

        Повторите эти действия необходимое количество раз.

        Добавленные получатели отображаются в разделе **список получателей** в всплывающем меню. Чтобы удалить получателя, нажмите кнопку ![ удалить кнопку ](../../media/scc-remove-icon.png) .

     e. По завершении нажмите кнопку **Сохранить**.

     Чтобы отключить этот параметр, снимите этот флажок.

5. Необязательно Разверните раздел **ограничения получателей** , чтобы настроить ограничения и действия для подозрительных исходящих сообщений электронной почты.

   > [!NOTE]
   > Эти параметры применяются только к облачным почтовым ящикам.

   - **Максимальное количество получателей на одного пользователя**

     Допустимые значения: от 0 до 10000. Значение по умолчанию — 0, что означает, что используются значения по умолчанию для службы. Более подробную информацию можно узнать в статье [limiting Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Внешнее почасовое ограничение**: максимальное число внешних получателей в час.

     - **Внутреннее почасовое ограничение**: максимальное число внутренних получателей в час.

     - **Ежедневное ограничение**: максимальное общее количество получателей в день.

   - **Действие, когда пользователь превышает указанные выше пределы**: Настройте действие, которое будет выполняться при превышении одного из **пределов получателей** . Для всех действий получатели, указанные в **учетной записи пользователя, имеют ограниченную отправку политики оповещений по электронной почте** (и в разделе теперь избыточность **уведомлять определенных людей, если отправитель заблокирован из-за отправки параметра нежелательной почты** в политике нежелательной почты получать уведомления по электронной почте

     - **Запретить пользователю отправлять почту до следующего дня**: это значение по умолчанию. Уведомления по электронной почте отправляются, и пользователь не сможет отправлять больше сообщений до следующего дня, исходя из времени в формате UTC. Администратор не может переопределить этот блок.

       - Оповещение об активности с именем **User Restricted from Send e-mail** уведомляет администраторов (через электронную почту и на странице " **Просмотр оповещений** ").

       - Все получатели, указанные в поле **уведомлять определенных людей, если отправитель заблокирован из-за отправки настройки исходящей нежелательной почты** в политике, также получают уведомления.

       - Пользователь не сможет отправлять больше сообщений до следующего дня, основываясь на времени в формате UTC. Администратор не может переопределить этот блок.

     - **Запретить пользователю отправлять почту**: отправляются уведомления по электронной почте, пользователь добавляется на портал **[пользователи с ограниченными правами] <https://sip.protection.office.com/restrictedusers> ** в центре безопасности & соответствия требованиям, и пользователь не может отправлять электронную почту до тех пор, пока администратор не удалит их из портала **ограниченных пользователей** . После того как администратор удалит пользователя из списка, он не будет снова ограничен в течение этого дня. Инструкции приведены в статье [Удаление пользователя с портала ограниченных пользователей после отправки нежелательной почты](removing-user-from-restricted-users-portal-after-spam.md).

     - **Без действия, только оповещение**: отправляются уведомления по электронной почте.
6. Необязательно Разверните раздел **Автоматическая пересылка** , чтобы настроить управление процессом автоматической пересылки пользователями.

   > [!NOTE]
   > Эти параметры применяются только к облачным почтовым ящикам.
   
   - **Автоматическая переадресация**
  
      Выберите один из вариантов, чтобы управлять процессом автоматической пересылки.
    
      - **Автоматический**: параметр по умолчанию, который позволяет системе управлять автоматическим пересылкой с отключенной автоматической переадресацией по умолчанию.
      - **On**: внешняя переадресация включена в политике без ограничений.
      - **Выключен**: внешняя переадресация отключена и будет заблокирована

7. Потребоваться Разверните раздел **применено** , чтобы определить внутренних отправителей, к которым применяется политика.

    Условие или исключение можно использовать только один раз, но можно указать для них несколько значений. Указать несколько значений в одном условии или исключении можно с помощью оператора OR (например, _\<sender1\>_ or _\<sender2\>_). Между разными условиями и исключениями используется оператор AND (например, _\<sender1\>_ and _\<member of group 1\>_).

    Проще всего нажать кнопку **Добавить условие** три раза, чтобы увидеть все доступные условия. Чтобы удалить условия, которые не нужно настраивать, можно щелкнуть ![Кнопка удаления](../../media/scc-remove-icon.png).

    - **Домен отправителя**: указывает отправители из одного или нескольких настроенных обслуживаемых доменов в Организации. Щелкните поле **Добавить тег**, чтобы просмотреть и выбрать домен. Еще раз щелкните поле **Добавить тег**, чтобы выбрать дополнительные домены, если доступно несколько доменов.

    - **Отправитель**: указывает одного или нескольких пользователей в Организации. Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список. Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.

    - **Отправитель является участником**: указывает одну или несколько групп в Организации. Щелкните в поле **Добавить тег** и начните вводить текст, чтобы отфильтровать список. Еще раз щелкните поле **Добавить тег** , чтобы выбрать дополнительных отправители.

    - **За исключением случаев, когда**. Чтобы добавить исключение из правила, щелкните **Добавьте условие** три раза, чтобы увидеть все доступные исключения. Параметры и поведение полностью идентичны условиям.

8. По завершении нажмите кнопку **Сохранить**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Использование центра безопасности & соответствия требованиям для просмотра политик нежелательной почты

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.

   - Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.

   - Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.

3. Параметры политики отображаются в отображаемых сведениях расширенной политики или можно щелкнуть **изменить политику**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Использование центра безопасности & соответствия требованиям для изменения политик исходящей нежелательной почты

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть политику нежелательной почты.

   - Политика по умолчанию с именем **Исходящая политика фильтрации нежелательной почты**.

   - Создана настраиваемая политика, где значение в столбце **тип** является **настраиваемой политикой исходящих сообщений о нежелательной почте**.

3. Щелкните **Изменение политики**.

Для настраиваемых политик нежелательной почты доступные параметры в всплывающем меню идентичны тем, которые описаны в разделе [использование & безопасности центра соответствия требованиям для создания раздела политики исходящих сообщений о нежелательной почте](#use-the-security--compliance-center-to-create-outbound-spam-policies) .

Для политики исходящих сообщений по умолчанию с именем " **Политика фильтрации нежелательной почты**" раздел **применено к** (политика применяется для всех), и вы не можете переименовать политику.

Сведения о включении или отключении политики, настройке приоритета политики или настройке уведомлений пользователей о карантине см. в следующих разделах.

### <a name="enable-or-disable-outbound-spam-policies"></a>Включение и отключение политик исходящей нежелательной почты

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **Параметры защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть созданную настраиваемую политику (значение в столбце **тип** — **настраиваемая политика исходящей почты**).

3. В развернутых сведениях политики обратите внимание на значение в столбце **Вкл**.

   Чтобы отключить политику, переместите переключатель влево: ![Выключенный переключатель](../../media/scc-toggle-off.png)

   Чтобы включить политику, переместите переключатель вправо: ![Включенный переключатель](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Отключить политику исходящей почты по умолчанию невозможно.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Установка приоритета настраиваемых политик нежелательной почты

По умолчанию политикам исходящих сообщений по умолчанию назначен приоритет, основанный на порядке, в котором они были созданы (более новые политики имеют более высокий приоритет, чем старые политики). Чем ниже значение, тем выше приоритет политики (0 — наивысший приоритет), а порядок обработки политик зависит от их приоритетов (политики с высоким приоритетом обрабатываются раньше, чем политики с низким приоритетом). Приоритеты двух политик не могут совпадать.

Настраиваемые политики исходящей почты отображаются в порядке их обработки (первая политика имеет значение **приоритета** 0). По умолчанию политика **фильтрации** нежелательной почты имеет значение Priority **наименьшее**, и вы не можете изменить его.

Чтобы изменить приоритет политики, переместите ее вверх или вниз в списке (в Центре безопасности и соответствия требованиям невозможно напрямую изменить значение свойства **Приоритет**).

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **Параметры защиты от нежелательной почты** найдите политики, в которых значение столбца **тип** является **настраиваемой политикой исходящих сообщений**о нежелательной почте. Обратите внимание на значения в столбце **Приоритет**:

   - Настраиваемая политика нежелательной почты с наивысшим приоритетом имеет ![ значок стрелки вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Настраиваемая политика нежелательной почты с наименьшим приоритетом имеет ![ значок стрелки вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (например, ![ значок со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Если у вас есть три или более настраиваемых политик нежелательной почты, политики между самым высоким и самым низким приоритетом имеют значок стрелка ![ вверх со ](../../media/ITPro-EAC-UpArrowIcon.png)![ стрелкой вниз ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (например, значок ![ со стрелкой вверх ](../../media/ITPro-EAC-UpArrowIcon.png)![ вниз значок ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Щелкните ![Значок "Стрелка вверх"](../../media/ITPro-EAC-UpArrowIcon.png) или ![Значок "Стрелка вниз"](../../media/ITPro-EAC-DownArrowIcon.png) Перемещение настраиваемой политики нежелательной почты в списке приоритет.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Использование центра безопасности & соответствия требованиям для удаления политик нежелательной почты

1. В Центре безопасности и соответствия требованиям выберите **Управление угрозами** \> **Политика** \> **Защита от спама**.

2. На странице **параметров защиты от нежелательной почты** нажмите ![ развернуть значок, ](../../media/scc-expand-icon.png) чтобы развернуть пользовательскую политику, которую нужно удалить (в столбце **тип** — **настраиваемая политика нежелательной почты**).

3. В развернутых сведениях политики щелкните **Удалить политику**.

4. Нажмите **Да** в появившемся предупреждающем диалоговом окне.

Политику по умолчанию удалить невозможно.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Настройка политик нежелательной почты с помощью Exchange Online PowerShell или изолированной EOP PowerShell

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Создание политик нежелательной почты с помощью PowerShell

Процесс создания политики нежелательной почты в PowerShell состоит из двух этапов:

1. Создайте политику фильтрации исходящих сообщений.

2. Создайте правило фильтрации исходящих сообщений о нежелательной почте, которое указывает политику фильтрации исходящих сообщений, к которой применяется правило.

 **Примечания**.

- Вы можете создать новое правило фильтрации нежелательной почты и назначить для него существующую, не связанную с ней политику фильтрации нежелательной почты. Правило фильтрации исходящих сообщений не может быть связано с несколькими политиками фильтрации исходящей почты.

- Вы можете настроить следующие параметры для новых политик фильтрации нежелательной почты в PowerShell, которые недоступны в центре безопасности & соответствия требованиям, пока не будет создана политика:

  - Создайте новую политику как отключенную (_включена_ `$false` в командлете **New-хостедаутбаундспамфилтерруле** ).

  - Задайте приоритет политики при создании (_приоритет_ _\<Number\>_ ) для командлета **New-хостедаутбаундспамфилтерруле** .

- Новая политика фильтрации исходящих сообщений, созданная в PowerShell, не отображается в центре безопасности &, пока политика не будет назначена правилу фильтрации спама.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Шаг 1: использование PowerShell для создания политики фильтрации исходящей нежелательной почты

Чтобы создать политику фильтрации нежелательной почты, используйте следующий синтаксис:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

В этом примере создается политика фильтрации исходящих сообщений с именем Contoso Executives со следующими параметрами:

- Ограничения скорости получателя ограничены меньшими значениями, используемыми по умолчанию. Для получения дополнительных сведений [365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)см.

- По истечении одного из этих пределов пользователю запрещено отправлять сообщения.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Шаг 2: использование PowerShell для создания правила фильтрации исходящей нежелательной почты

Чтобы создать правило фильтрации исходящих сообщений, используйте следующий синтаксис:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

В этом примере создается правило фильтрации исходящих сообщений с именем Contoso Executives с этими параметрами:

- Политика фильтрации исходящей нежелательной почты с именем Contoso Executives связана с правилом.

- Правило применяется к участникам группы Contoso Executives (Руководители Contoso).

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [New – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Просмотр политик фильтрации исходящей нежелательной почты с помощью PowerShell

Чтобы получить сводный список всех политик фильтрации нежелательной почты, выполните следующую команду:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Чтобы получить подробные сведения о конкретной политике фильтрации нежелательной почты, используйте следующий синтаксис:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

В этом примере возвращаются все значения свойств для политики фильтрации исходящей нежелательной почты с именем Executives.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Просмотр правил фильтрации исходящей нежелательной почты с помощью PowerShell

Чтобы просмотреть существующие правила фильтрации нежелательной почты, используйте следующий синтаксис:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Чтобы получить сводный список всех правил фильтрации нежелательной почты, выполните следующую команду:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Чтобы отфильтровать список по включенным или отключенным правилам, выполните следующие команды:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Чтобы получить подробные сведения об определенном правиле фильтрации нежелательной почты, используйте следующий синтаксис:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

В этом примере возвращаются все значения свойств для правила фильтрации нежелательной почты Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Использование PowerShell для изменения политик фильтрации исходящей нежелательной почты

Те же параметры доступны при изменении политики фильтрации вредоносных программ в PowerShell так же, как и при создании политики, как описано в [шаге 1: с помощью PowerShell создайте в этой статье раздел Политика фильтрации исходящей нежелательной почты](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) .

> [!NOTE]
> Невозможно переименовать политику фильтра нежелательной почты (командлет **Set-хостедаутбаундспамфилтерполици** не имеет параметра _Name_ ). При переименовании политики исходящей нежелательной почты в центре безопасности & соответствия требованиям Вы переименовываете только _правило_фильтрации исходящей нежелательной почты.

Чтобы изменить политику фильтрации нежелательной почты, используйте следующий синтаксис:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Использование PowerShell для изменения правил фильтрации исходящей нежелательной почты

Единственный параметр, недоступный при изменении правила фильтрации нежелательной почты в PowerShell, это параметр _Enabled_ , позволяющий создать отключенное правило. Чтобы включить или отключить существующие правила фильтрации нежелательной почты, ознакомьтесь со статьей, приведенным в следующем разделе.

В противном случае дополнительные параметры не будут доступны при изменении правила фильтрации нежелательной почты в PowerShell. Те же параметры доступны при создании правила, как описано в [шаге 2: используйте PowerShell, чтобы создать раздел правил фильтрации нежелательной почты](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , приведенный ранее в этой статье.

Чтобы изменить правило фильтрации исходящих сообщений, используйте следующий синтаксис:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Включение и отключение правил фильтрации исходящих сообщений с помощью PowerShell

Включение или отключение правила фильтрации исходящей нежелательной почты в PowerShell включает или отключает полную политику исходящей нежелательной почты (правило фильтрации нежелательной почты и назначенную политику фильтрации нежелательной почты). Вы не можете включить или отключить политику исходящей почты по умолчанию (она всегда применяется ко всем получателям).

Чтобы включить или отключить правило фильтрации исходящих сообщений в PowerShell, используйте следующий синтаксис:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

В этом примере отключается правило фильтрации исходящих сообщений с именем Marketing Department.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

В этом примере включается то же правило.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Enable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Установка приоритета правил фильтрации исходящих сообщений с помощью PowerShell

Максимальный приоритет, который можно задать для правила, — 0. Минимальное значение зависит от количества правил. Например, если у вас есть пять правил, вы можете использовать значения 0–4. Изменение приоритета существующего правила оказывает каскадное влияние на другие правила. Например, если вы измените приоритет правила на 2, когда у вас есть пять настраиваемых правил (с приоритетами от 0 до 4), то для существующего правила с приоритетом 2 будет задан приоритет 3, а для правила с приоритетом 3 будет задан приоритет 4.

Чтобы задать приоритет правила фильтрации исходящей нежелательной почты в PowerShell, используйте следующий синтаксис:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 
> - Чтобы задать приоритет нового правила при его создании, используйте параметр _Priority_ в командлете **New – хостедаутбаундспамфилтерруле** .
>
> - Исходящая политика фильтрации нежелательной почты по умолчанию не имеет соответствующего правила фильтрации нежелательной почты и всегда имеет неизменяемое значение приоритета **.**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Удаление политик фильтрации нежелательной почты с помощью PowerShell

При использовании PowerShell для удаления политики фильтрации исходящей нежелательной почты соответствующее правило фильтрации нежелательной почты не удаляется.

Чтобы удалить политику фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

В этом примере удаляется политика фильтрации исходящей нежелательной почты с именем Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерполици](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Удаление правил фильтрации нежелательной почты с помощью PowerShell

При использовании PowerShell для удаления правила фильтрации нежелательной почты соответствующая политика фильтрации исходящих сообщений не удаляется.

Чтобы удалить правило фильтрации нежелательной почты в PowerShell, используйте следующий синтаксис:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

В этом примере удаляется правило фильтрации исходящих сообщений с именем Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Remove – хостедаутбаундспамфилтерруле](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Дополнительные сведения

[Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"](removing-user-from-restricted-users-portal-after-spam.md)

[Пул доставки сообщений с высоким уровнем опасности](high-risk-delivery-pool-for-outbound-messages.md)

[Вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.md)

[Отчет по автоматически пересылаемым сообщениям](mfi-auto-forwarded-messages-report.md)
