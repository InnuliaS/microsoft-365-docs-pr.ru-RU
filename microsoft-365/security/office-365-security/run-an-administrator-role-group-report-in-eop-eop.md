---
title: Запустите отчет группы ролей администратора в автономном EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как запустить отчет о группе ролей администраторов в автономной службе Exchange Online Protection (EOP). Этот отчет регистрируется, когда администратор добавляет или удаляет участников из групп ролей администраторов, EOP записывает каждое из них.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587368"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Запустите отчет группы ролей администратора в автономном EOP

В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, когда администратор добавляет или удаляет членов из групп административных ролей, служба регистрирует все вхождения. Дополнительные сведения о группах ролей в автономной EOP см [в разделе разрешения в автономной EOP](feature-permissions-in-eop.md).

При запуске отчета о группе ролей администраторов в центре администрирования Exchange записи отображаются в виде результатов поиска и включают затронутые группы ролей, которые изменяют членство в группе ролей, а также сведения о том, когда и как были сделаны обновления членства. Этот отчет можно использовать для отслеживания изменений в административных разрешениях, назначенных пользователям в организации.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть центр администрирования Exchange, обратитесь к [центру администрирования Exchange в автономной EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения. В частности, необходимы журналы аудита или роль только для просмотра журналов аудита, которые назначаются группам ролей Комплианцеманажемент, Организатионманажемент (глобальные администраторы) и Секуритядминистратор по умолчанию. Дополнительные сведения см. [в разделе разрешения в автономных EOP](feature-permissions-in-eop.md) и используйте центр администрирования Exchange для [изменения списка участников в группах ролей](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Возникли проблемы? Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Запуск отчета о группе ролей администраторов с помощью Центра администрирования Exchange

Запустите отчет о группе ролей администраторов, чтобы найти изменения в группах ролей управления в Организации в течение определенного промежутка времени.

1. В центре администрирования Exchange перейдите к разделу аудит **управления соответствием требованиям** \> **Auditing**, а затем выберите команду **запустить отчет о группе ролей администраторов**.

2. На открывшейся странице " **Поиск изменений в группах ролей администраторов** " настройте следующие параметры:

   - **Дата начала** и **Дата окончания**: введите диапазон дат. По умолчанию отчет выполняет поиск изменений в группе ролей администраторов за последние две недели.

   - **Выберите группы ролей**: по умолчанию поиск выполняется для всех групп ролей. Чтобы отфильтровать результаты по определенным группам ролей, нажмите кнопку **выбрать группы ролей**. В появившемся диалоговом окне выберите группу ролей и щелкните **добавить >**. Повторите это действие столько раз, сколько необходимо, а затем нажмите кнопку **ОК** , когда закончите.

3. По завершении нажмите кнопку **Поиск**.

Если будут найдены любые изменения, соответствующие заданным критериям, они появятся в области результатов. Чтобы в области сведений увидеть изменения, выберите группу ролей в результатах поиска.

## <a name="how-do-you-know-this-worked"></a>Как убедиться, что все получилось?

Если отчет о группе ролей администрирования запущен успешно, группы ролей, измененные в рамках диапазона дат, отображаются в области результатов поиска. Если результатов нет  в указанный диапазон дат группы ролей изменены не были. Если вы считаете, что результаты должны быть, измените диапазон дат и повторно запустите отчет.

## <a name="monitor-changes-to-role-group-membership"></a>Отслеживание изменений состава группы ролей

При добавлении или удалении участников группы ролей результаты поиска в области сведений указывают на изменение состава группы ролей с указанием ее текущих участников. В результатах не говорится явно, кто был добавлен или удален.

Чтобы определить, был ли добавлен или удален пользователь, следует сравнить две записи в отчете. Например, рассмотрим следующие записи журнала для группы ролей **HelpDesk**.

> 1/27/2018 4:43 PM <br> Администратор <br> Обновленные участники: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Администратор <br> Обновленные участники: Administrator;annb;florencef;tonip

В этом примере администратор внес следующие изменения:

- В 2/06/2018 они добавили пользователя tonip.

- В 2/19/2018 он удалил пользователя pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Поиск записей журнала аудита с помощью автономной консоли PowerShell с Exchange Online

Вы можете использовать Exchange Online PowerShell для поиска записей журнала аудита, соответствующих заданным условиям. Список критериев поиска представлен в статье Search [— AdminAuditLog Search Criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). В этой процедуре используется командлет **Search-AdminAuditLog** , а результаты поиска отображаются в Exchange Online PowerShell. Этот командлет можно использовать для возврата набора результатов, которые выходят за пределы, определенные в командлете **New – AdminAuditLogSearch** или в отчетах об отчетах по аудиту центра администрирования Exchange.

Чтобы выполнить поиск по указанному критерию журнала аудита, используйте следующий синтаксис.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Командлет **Search-AdminAuditLog** по умолчанию возвращает максимум 1000 записей журнала. Используйте параметр _ResultSize_ , чтобы указать до 250 000 записей журнала. Или используйте значение, `Unlimited` чтобы возвратить все записи.

В этом примере выполняется поиск всех записей журнала аудита со следующими критериями:

- **Дата начала**: 08/04/2018

- **Дата окончания**: 10/03/2018

- **Идентификаторы пользователей**: Davids, Крис, Kima

- **Командлеты**: **Set — Mailbox**

- **Параметры**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

В этом примере выполняется поиск изменений определенных почтовых ящиков. Это позволяет определить неполадку или предоставить сведения для диагностики. Используются следующие критерии:

- **Дата начала**: 05/01/2018

- **Дата окончания**: 10/03/2018

- **Идентификатор объекта**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Если поиск возвращает много записей журнала, рекомендуется использовать процедуру, описанную в статье **использование Exchange Online PowerShell для поиска записей журнала аудита и отправки результатов получателю** . Действия в этом разделе позволяют отправить XML-файл в виде вложения сообщения электронной почты указанным отправителям, чтобы быстрее извлечь интересующие данные.

Дополнительные сведения о синтаксисе и параметрах см. в разделе [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Просмотр подробных сведений о записях журнала аудита

Командлет **Search – AdminAuditLog** возвращает поля, описанные в разделе [содержимое журнала аудита](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). Поля **CmdletParameters** и **ModifiedProperties**, возвращаемые командлетом, содержат дополнительные сведения, которые невозможно просмотреть по умолчанию.

Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties**, выполните указанные ниже действия. Кроме того, вы можете использовать процедуру, описанную в статье **Использование PowerShell для Exchange Online, для поиска записей журнала аудита и отправки результатов получателю** в этой статье, чтобы создать XML-файл.

В этой процедуре используются следующие основные понятия:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Определите критерии поиска, запустите командлет **Search-AdminAuditLog** и сохраните результаты в переменной с помощью следующей команды.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Каждая запись журнала аудита хранится в виде элемента массива в переменной `$Results` . Чтобы выбрать элемент массива, укажите его индекс. Индексы элементов массива начинаются с 0 для первого элемента массива. Например, чтобы получить пятый элемент массива с индексом 4, используйте следующую команду.

    ```PowerShell
    $Results[4]
    ```

3. Предыдущая команда возвращает запись журнала, хранящуюся в элементе массива 4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedProperties** для этой записи журнала, используйте следующие команды.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Чтобы просмотреть содержимое полей **CmdletParameters** и **ModifiedParameters** в другой записи журнала, измените индекс элемента массива.