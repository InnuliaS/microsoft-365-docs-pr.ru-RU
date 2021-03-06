---
title: Удаление элементов из папки "облачный почтовый ящик" для хранения элементов с возможностью восстановления
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Узнайте, как удалять элементы в папке "элементы с возможностью восстановления" для почтового ящика Exchange Online, даже если этот почтовый ящик размещен на удержании по юридическим причинам.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d7babf231efba31a6f4cb1638d98669a9b938f9
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817878"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Удаление элементов из папки "элементы с возможностью восстановления" в облачных почтовых ящиках в справке для удержания

Папка "элементы с возможностью восстановления" для почтового ящика Exchange Online существует для защиты от случайных или вредоносных удалений. Он также используется для хранения элементов, которые поддерживаются и доступны для обеспечения соответствия требованиям, например для поиска удержаний и обнаружения электронных данных. Однако в некоторых ситуациях некоторые организации могут иметь непреднамеренно сохраненные данные в папке "элементы с возможностью восстановления", которые необходимо удалить. Например, пользователь может непреднамеренно отправить или переслать сообщение электронной почты, содержащее конфиденциальную информацию или информацию, которая может иметь серьезные последствия для бизнеса. Даже если сообщение окончательно удаляется, оно может храниться в течение неограниченного времени, так как для почтового ящика было включено юридическое удержание. Этот сценарий называется выпустка данных, так как данные были случайно перенесены в Office 365. В этом случае можно удалить элементы из папки "элементы с возможностью восстановления" для почтового ящика Exchange Online, даже если этот почтовый ящик включен в удержание с одной из различных функций хранения в Office 365. Эти типы удержаний включают судебные удержания, удержания на месте, удержания электронных данных и политики хранения, созданные в центре безопасности и соответствия требованиям в Office 365 или Microsoft 365.
  
 В этой статье объясняется, как удалять элементы из папки "элементы с возможностью восстановления" для почтовых ящиков в облаке, находящихся на удержании. Эта процедура включает в себя отключение доступа к почтовому ящику и отключение восстановления отдельных элементов, отключение помощника по работе с управляемыми папками от обработки почтового ящика, временное удаление удержания, удаление элементов из папки "элементы с возможностью восстановления", а затем возврат к предыдущей конфигурации почтового ящика. Вот процесс: 
  
[Шаг 1: сбор сведений о почтовом ящике](#step-1-collect-information-about-the-mailbox)

[Шаг 2: подготовка почтового ящика](#step-2-prepare-the-mailbox)

[Шаг 3: удаление всех удержаний из почтового ящика](#step-3-remove-all-holds-from-the-mailbox)

[Шаг 4: удаление задержки хранения из почтового ящика](#step-4-remove-the-delay-hold-from-the-mailbox)

[Шаг 5: удаление элементов из папки "элементы с возможностью восстановления"](#step-5-delete-items-in-the-recoverable-items-folder)

[Шаг 6: возврат к предыдущему состоянию почтового ящика](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Процедуры, описанные в этой статье, будут приводить к окончательному удалению данных из почтового ящика Exchange Online. Это означает, что сообщения, которые вы удаляете из папки "элементы с возможностью восстановления", невозможно восстановить, и они не будут доступны для судебного обнаружения или других целей обеспечения соответствия требованиям. Если вы хотите удалить сообщения из почтового ящика, размещенного на удержании в рамках хранения для судебного разбирательства, хранения на месте, удержания электронных данных или политики хранения, созданной в центре безопасности и соответствия требованиям, проверяйте управление записями или юридическими отделами, прежде чем удалять удержание. У вашей организации может быть политика, определяющая, имеет ли почтовые ящики на удержании или при проведении на них приоритет. 
  
## <a name="before-you-delete-items"></a>Перед удалением элементов

- Создавать и выполнять поиск контента могут только члены группы ролей "Диспетчер eDiscovery" и пользователи с ролью "Управление поиском соответствия". Удалять сообщения могут только члены группы ролей "Управление организацией" и пользователи с ролью "Управление поиском и очисткой". Сведения о добавлении пользователей в группу ролей см. в статье [Назначение разрешений обнаружения электронных данных в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- Процедуры, описанные в этой статье, не поддерживаются для неактивных почтовых ящиков. Это связано с тем, что после удаления неактивного почтового ящика невозможно повторно применить политику хранения (или политику хранения). При удалении удержания из неактивного почтового ящика он заменяется обычным обратимо удаленным почтовым ящиком и будет окончательно удален из Организации после его обработки помощником для управляемых папок.

- Эту процедуру невозможно выполнить для почтового ящика, назначенного политике хранения, заблокированной с блокировкой сохранения. Это связано с тем, что блокировка сохранения предотвращает удаление или исключение почтового ящика из политики хранения и отключение помощника для управляемых папок в почтовом ящике. Дополнительные сведения о блокировке политик хранения приведены в статье [Использование блокировки сохранения для соблюдения нормативных требований](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).

- Если почтовый ящик не полагается на удержание (или не включено восстановление отдельных элементов), можно удалить элементы из папки "элементы с возможностью восстановления". Дополнительные сведения о том, как это сделать, можно найти [в статье Поиск и удаление сообщений электронной почты в Организации](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Шаг 1: сбор сведений о почтовом ящике

Сначала необходимо собрать выбранные свойства из целевого почтового ящика, которые будут влиять на эту процедуру. Обязательно запишите эти параметры или сохраните их в текстовом файле, так как вы измените некоторые из этих свойств, а затем вернитесь к исходным значениям на шаге 6, после того как вы удалите элементы из папки "элементы с возможностью восстановления". Ниже приведен список свойств почтовых ящиков, которые необходимо собрать.
  
- *Синглеитемрековеренаблед* и *RetainDeletedItemsFor*. При необходимости вы отключите одно восстановление и увеличьте срок хранения удаленных элементов на шаге 3. 

- *LitigationHoldEnabled* и *InPlaceHolds*. Необходимо определить все удержания, размещенные в почтовом ящике, чтобы их можно было временно удалить на шаге 3. В разделе [Дополнительные сведения](#more-information) приведены советы по определению типа удержания, который может быть включен в почтовый ящик. 

Кроме того, необходимо получить параметры клиентского доступа почтовых ящиков, чтобы их можно было временно отключить, чтобы владелец (или другие пользователи) не мог получить доступ к этому почтовому ящику во время выполнения этой процедуры. Наконец, вы можете получить текущий размер и количество элементов в папке "элементы с возможностью восстановления". После удаления элементов из папки "элементы с возможностью восстановления", описанной в шаге 5, вы будете использовать эти сведения, чтобы убедиться, что элементы были удалены.
  
1. [Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Обязательно используйте имя пользователя и пароль для учетной записи администратора, которой назначены соответствующие роли управления в Exchange Online. 
    
2. Выполните следующую команду, чтобы получить сведения об использовании восстановления отдельных элементов и периода хранения удаленных элементов.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Если включено восстановление отдельных элементов, необходимо отключить его на шаге 2. Если срок хранения удаленных элементов не задан в течение 30 дней (максимальное значение в Exchange Online), его можно увеличить на шаге 2. 
    
3. Выполните следующую команду, чтобы получить параметры доступа к почтовому ящику для почтового ящика. 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Все эти способы доступа будут отключены на шаге 2.
    
4. Выполните следующую команду, чтобы получить сведения о удержаниях и политиках хранения, применяемых к почтовому ящику.
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Если в свойстве *InPlaceHolds* слишком много значений, а не все они отображаются, можно выполнить `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` команду, чтобы отобразить каждое значение в отдельной строке. 
  
5. Выполните следующую команду, чтобы получить сведения о политиках хранения на уровне всей Организации. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   Если в Организации есть политики хранения на уровне Организации, необходимо исключить почтовый ящик из этих политик на шаге 3.

   > [!TIP]
    > Если в свойстве *InPlaceHolds* слишком много значений, а не все они отображаются, можно выполнить `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` команду, чтобы отобразить каждое значение в отдельной строке. 
  
6. Выполните следующую команду, чтобы получить текущий размер и общее количество элементов в папках и вложенных папках в папке "элементы с возможностью восстановления" в основном почтовом ящике пользователя. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Если архивный почтовый ящик пользователя включен, выполните следующую команду, чтобы получить размер и общее количество элементов в папках и подпапках в папке "элементы с возможностью восстановления" в своем архивном почтовом ящике. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   При удалении элементов на шаге 5 можно удалить или не удалять элементы из папки "элементы с возможностью восстановления" в основном архивном почтовом ящике пользователя. Если для почтового ящика включено автоматическое расширение архивации, элементы в вспомогательном архивном почтовом ящике не удаляются.
  
## <a name="step-2-prepare-the-mailbox"></a>Шаг 2: подготовка почтового ящика

После сбора и сохранения сведений о почтовом ящике следующим шагом является подготовка почтового ящика путем выполнения следующих задач. 
  
- **Отключить клиентский доступ к почтовому ящику** , чтобы владелец почтового ящика не получил доступ к своему почтовому ящику и вносить в него изменения данных почтового ящика. 
    
- **Увеличьте срок хранения удаленных элементов** до 30 дней (максимальное значение в Exchange Online), чтобы элементы не удалялись из папки "элементы с возможностью восстановления", прежде чем их можно будет удалить на шаге 5. 
    
- **Отключите восстановление отдельных элементов** , чтобы элементы не сохранялись (срок хранения удаленных элементов) после удаления их из папки "элементы с возможностью восстановления" на шаге 5. 
    
- **Отключите помощник по работе с управляемыми папками** , чтобы он не обпомнил почтовый ящик и сохранял элементы, которые вы удалили на шаге 5. 
    
Выполните следующие действия в Exchange Online PowerShell.
  
1. Выполните следующую команду, чтобы отключить все клиентские права на доступ к почтовому ящику. Синтаксис команды предполагает, что все методы клиентского доступа были включены для почтового ящика.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Отключение всех методов клиентского доступа к почтовому ящику может занять до 60 минут. Обратите внимание, что отключение этих методов доступа не отключит владельца почтового ящика, в котором они вошли в систему. Если владелец не вошел в систему, он не сможет получить доступ к своему почтовому ящику после отключения этих методов доступа. 
  
2. Выполните следующую команду, чтобы увеличить срок хранения удаленных элементов максимум 30 дней. Предполагается, что текущее значение меньше 30 дней. 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Выполните следующую команду, чтобы отключить восстановление отдельных элементов.
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Отключение восстановления отдельных элементов может занять до 60 минут. Не удаляйте элементы в папке "элементы с возможностью восстановления" до истечения этого периода. 
  
4. Выполните следующую команду, чтобы предотвратить обработку почтового ящика помощником для управляемых папок. Как было сказано ранее, помощник для управляемых папок можно отключить только в том случае, если к почтовому ящику не применяется политика хранения с блокировкой сохранения. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Шаг 3: удаление всех удержаний из почтового ящика

Последний шаг перед удалением элементов из папки "элементы с возможностью восстановления" состоит в том, чтобы удалить все удержания (определенные на шаге 1), размещенные в почтовом ящике. Все удержания необходимо удалить, чтобы элементы не сохранялись после удаления их из папки "элементы с возможностью восстановления". В следующих разделах содержатся сведения об удалении различных типов удержаний для почтового ящика. В разделе [Дополнительные сведения](#more-information) приведены советы по определению типа удержания, который может быть включен в почтовый ящик. Для получения дополнительных сведений Узнайте, [как определить тип удержания, размещенного в почтовом ящике Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Как было сказано ранее, прежде чем удалять удержание из почтового ящика, проверяйте управление записями или юридическими отделами. 
  
 ### <a name="litigation-hold"></a>Хранение для судебного разбирательства
  
Выполните следующую команду в Exchange Online PowerShell, чтобы удалить удержание для судебного разбирательства из почтового ящика.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Аналогично отключению методов клиентского доступа и восстановления отдельных элементов может потребоваться до 60 минут, чтобы удалить удержание для судебного разбирательства. Не удаляйте элементы из папки "элементы с возможностью восстановления" до истечения этого периода. 
  
 ### <a name="in-place-hold"></a>Хранение на месте
  
Выполните следующую команду в Exchange Online PowerShell, чтобы определить удержание на месте, которое размещено в почтовом ящике. Используйте GUID для хранения на месте, определенного в действии 1. 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Определив удержание на месте, вы можете удалить почтовый ящик из удержания с помощью центра администрирования Exchange или Exchange Online PowerShell. Дополнительные сведения см. [в статье Создание или удаление удержания на месте](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>Политики хранения, применяемые к определенным почтовым ящикам
  
Выполните следующую команду в [PowerShell центра безопасности & соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=627084) , чтобы определить политику хранения, применяемую к почтовому ящику. Используйте GUID (не включая `mbx` `skp` префикс) для политики хранения, определенной на шаге 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Определив политику хранения, перейдите на страницу хранения данных управления **сведениями** \> **Retention** в центре безопасности & соответствия требованиям, измените политику хранения, определенную на предыдущем шаге, и удалите почтовый ящик из списка получателей, включенных в политику хранения. 
  
 ### <a name="organization-wide-retention-policies"></a>Политики хранения на уровне Организации
  
Политики хранения на уровне Организации и на уровне Exchange применяются ко всем почтовым ящикам в Организации. Они применяются на уровне Организации (не на уровне почтового ящика) и возвращаются при выполнении командлета **Get-OrganizationConfig** на этапе 1. Выполните следующую команду в [PowerShell центра безопасности & соответствия требованиям](https://go.microsoft.com/fwlink/?linkid=627084) , чтобы определить политики хранения на уровне Организации. Используйте идентификатор GUID (не включая `mbx` префикс) для политик хранения на уровне Организации, определенных на этапе 1. 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Определив политики хранения на уровне Организации, перейдите на страницу хранения данных управления **сведениями** \> **Retention** в центре безопасности & соответствия требованиям, измените каждую политику хранения на уровне Организации, определенную на предыдущем шаге, и добавьте почтовый ящик в список исключенных получателей. Это приведет к удалению почтового ящика пользователя из политики хранения. 

### <a name="retention-labels"></a>Метки хранения

Когда пользователь применяет метку, настроенную для сохранения контента или сохранения и удаления контента в любой папке или элементе почтового ящика, свойство Mailbox *комплианцетагхолдапплиед* имеет значение **true**. В этом случае почтовый ящик считается заблокированным, как если бы он был включен в удержание для судебного разбирательства или назначено политике хранения.

Чтобы просмотреть значение свойства *комплианцетагхолдапплиед* , выполните следующую команду в Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

После определения того, что почтовый ящик находится на удержании, так как метка хранения применяется к папке или элементу, можно использовать средство поиска контента в центре безопасности и соответствия требованиям для поиска помеченных элементов с помощью условия поиска ComplianceTag. Дополнительные сведения можно найти в разделе условия поиска в [запросах ключевых слов и условиях поиска для поиска контента](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Дополнительные сведения о метках см. в статье [Общие сведения о метках](labels.md).

 ### <a name="ediscovery-holds"></a>удержания электронных данных
  
Выполните следующие команды в консоли [безопасности & соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) , чтобы определить удержание, связанное с вариантом обнаружения электронных данных (называемым *удержанием электронных*данных), который применяется к почтовому ящику. Используйте GUID (не включая `UniH` префикс) для удержания обнаружения электронных данных, определенного в действии 1. Вторая команда отображает имя случая обнаружения электронных данных, с которым связана удержание. Третья команда отображает имя удержания. 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Определив имя варианта обнаружения электронных данных и удержания, перейдите на **eDiscovery** \> страницу **Обнаружение** электронных данных в центре соответствия требованиям, откройте обращение и удалите почтовый ящик из удержания. Для получения дополнительных сведений об определении удержаний eDiscovery обратитесь к разделу "обнаружение электронных данных", в котором [описывается, как определить тип удержания, размещенного в почтовом ящике Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Шаг 4: удаление задержки хранения из почтового ящика

После удаления любого типа удержания из почтового ящика для свойства *делайхолдапплиед* или *делайрелеасехолдапплиед* почтового ящика задается значение **true**. Это происходит в следующий раз, когда помощник для управляемых папок обрабатывает почтовый ящик и обнаруживает, что удержание было удалено. Это называется *Задержка хранения* и означает, что фактическое удаление удержания задерживается в течение 30 дней, чтобы предотвратить окончательное удаление данных из почтового ящика. (Цель задержки хранения заключается в предоставлении администраторам возможности поиска и восстановления элементов почтовых ящиков, которые удаляются после удаления удержания.)  Если задержка отложена, почтовый ящик по-прежнему считается на хранение неограниченной длительности, как если бы почтовый ящик находился на удержании судебного разбирательства. По истечении 30 дней задержка задержки и Microsoft 365 автоматически попытаются удалить отложенную задержку (задав для свойства *делайхолдапплиед* или *делайрелеасехолдапплиед* **значение false**), чтобы удалить удержание. Для получения дополнительных сведений об отложенной задержке ознакомьтесь с разделом «Управление почтовыми ящиками при задержке», [чтобы определить тип удержания, размещенного в почтовом ящике Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Прежде чем удалять элементы на шаге 5, необходимо удалить их из почтового ящика. Сначала определите, применяется ли задержка хранения к почтовому ящику, выполнив следующую команду в Exchange Online PowerShell:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Если для свойства *делайхолдапплиед* или *делайрелеасехолдапплиед* задано значение **false**, для почтового ящика не было включено удержание задержки. Вы можете перейти к шагу 5 и удалять элементы в папке "элементы с возможностью восстановления".

Если для свойства *делайхолдапплиед* или *делайрелеасехолдапплиед* задано значение **true**, выполните одну из следующих команд, чтобы удалить отложенную блокировку:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

или

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Для использования параметра *ремоведелайхолдапплиед* или *ремоведелайрелеасехолдапплиед* необходимо назначить роль "юридический удержание" в Exchange Online.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Шаг 5: удаление элементов из папки "элементы с возможностью восстановления"

Теперь вы готовы к фактическому удалению элементов в папке "элементы с возможностью восстановления" с помощью командлетов [New – ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) и [New ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) в центре безопасности & соответствия требованиям. 

Для этого обратитесь к разделу [Поиск и удаление сообщений электронной почты](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

### <a name="verify-that-items-were-deleted"></a>Проверка того, что элементы были удалены

Чтобы убедиться, что вы успешно удалили элементы из папки "элементы с возможностью восстановления" почтового ящика, используйте командлет **Get-MailboxFolderStatistics** в Exchange Online PowerShell, чтобы проверить размер и количество элементов в папке "элементы с возможностью восстановления". Вы можете сравнить статистику с теми, которые были собраны на шаге 1. 
  
Выполните следующую команду, чтобы получить текущий размер и общее количество элементов в папках и вложенных папках в папке "элементы с возможностью восстановления" в основном почтовом ящике пользователя. 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Выполните следующую команду, чтобы получить размер и общее количество элементов в папках и вложенных папках в папке "элементы с возможностью восстановления" в архивном почтовом ящике пользователя. 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Шаг 6: возврат к предыдущему состоянию почтового ящика

Последним шагом будет возврат к предыдущей конфигурации почтового ящика. Это означает, что вы переопределяете свойства, измененные в шаге 2, и повторно примените удержания, которые вы удалили на шаге 3. К ним относятся:
  
- Возврат к предыдущему значению срока хранения удаленного элемента. Кроме того, можно просто оставить это значение 30 дней, максимальное значение в Exchange Online.
    
- Повторное включение восстановления отдельных элементов.
    
- Повторное включение клиентских методов доступа, чтобы владелец мог получать доступ к своему почтовому ящику.
    
- Повторное применение удаленных политик хранения и хранения.
    
- Повторное включение помощника для управляемых папок для обработки почтового ящика.
    
> [!IMPORTANT]
> Рекомендуется подождать 24 часа после повторного применения политики хранения или хранения (и проверить, что она находится на месте) перед повторным включением обработки почтового ящика помощником для управляемых папок. 
  
Выполните следующие действия (в указанной последовательности) в Exchange Online PowerShell.
  
1. Выполните следующую команду, чтобы вернуться к исходному значению срока хранения удаленного элемента. Предполагается, что предыдущее значение меньше 30 дней; Например, 14 дней. 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Выполните следующую команду, чтобы снова включить восстановление отдельных элементов.
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Выполните следующую команду, чтобы снова включить все методы клиентского доступа к почтовому ящику.
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Повторно примените удержания, которые вы удалили на шаге 3. В зависимости от типа удержания используйте одну из следующих процедур.
    
    **Судебное удержание**
    
    Выполните следующую команду, чтобы снова включить удержание для судебного разбирательства для почтового ящика.
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    Используйте центр администрирования Exchange (или Exchange Online PowerShell), чтобы добавить почтовый ящик обратно в режим удержания на месте. 
    
    **Политики хранения, применяемые к определенным почтовым ящикам**
    
    Используйте центр безопасности & соответствия требованиям, чтобы добавить почтовый ящик обратно в политику хранения. Перейдите на страницу "хранение управления **сведениями** \> **Retention** " в центре безопасности & соответствия требованиям, измените политику хранения и добавьте почтовый ящик обратно в список получателей, к которым применяется политика хранения. 
    
    **Политики хранения на уровне Организации**
    
    Если вы удалили политику хранения на уровне Организации или на уровне Exchange, исключив ее из политики, воспользуйтесь центром безопасности & соответствия требованиям, чтобы удалить почтовый ящик из списка исключенных пользователей. Перейдите на страницу "хранение управления **сведениями** \> **Retention** " в центре безопасности & соответствия требованиям, измените политику хранения на уровне Организации и удалите почтовый ящик из списка исключенных получателей. При этом политика хранения будет повторно применена к почтовому ящику пользователя. 
    
    **футляр для обнаружения электронных данных**
    
    Используйте центр соответствия требованиям & безопасности, чтобы добавить почтовый ящик обратное удержание, связанное с вариантом обнаружения электронных данных. Перейдите на страницу **eDiscovery** \> **Обнаружение** электронных данных, откройте обращение и снова добавьте почтовый ящик в удержание. 
    
5. Выполните следующую команду, чтобы разрешить помощнику для управляемых папок повторно обработать почтовый ящик. Как было сказано ранее, рекомендуем подождать 24 часа после повторного применения политики хранения или хранения (и проверить, что она находится на месте) до повторного включения помощника для управляемых папок. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Чтобы убедиться, что почтовый ящик возвращен в предыдущую конфигурацию, можно выполнить следующие команды, а затем сравнить параметры с теми, которые были собраны на шаге 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Дополнительные сведения

Ниже приведена таблица, в которой описывается, как определить различные типы удержаний на основе значений в свойстве *InPlaceHolds* при запуске командлетов **Get-Mailbox** или **Get-OrganizationConfig** . Более подробную информацию можно узнать в статье [как определить тип удержания, размещенного в почтовом ящике Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Как описывалось ранее, вам необходимо удалить все политики хранения и хранения из почтового ящика, прежде чем вы сможете успешно удалить элементы из папки "элементы с возможностью восстановления". 
  
|**Тип удержания**|**Пример значения**|**Определение удержания**|
|:-----|:-----|:-----|
|Хранение для судебного разбирательства  <br/> | `True` <br/> |Свойство  *LitigationHoldEnabled*  имеет значение  `True`.  <br/> |
|Хранение на месте  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |Свойство *InPlaceHolds* содержит GUID хранения на месте, который размещается в почтовом ящике. Вы можете указать, что это удержание на месте, так как идентификатор GUID не начинается с префикса.  <br/> Вы можете использовать `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` команду в Exchange Online PowerShell, чтобы получить сведения об удержании на месте для почтового ящика.  <br/> |
| Политики хранения в центре безопасности & соответствия требованиям, применяемые к определенным почтовым ящикам  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> или  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |При запуске командлета **Get – Mailbox** свойство *InPlaceHolds* также содержит идентификаторы GUID политик хранения, применяемых к почтовому ящику. Вы можете определить политики хранения, так как идентификатор GUID начинается с `mbx` префикса. Если GUID политики хранения начинается с `skp` префикса, то это означает, что политика хранения применяется к беседам Skype для бизнеса.  <br/> Чтобы обозначить политику хранения, применяемую к почтовому ящику, выполните следующую команду в командной консоли & безопасности (PowerShell): <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Не забудьте удалить префикс  `mbx` или  `skp` при выполнении этой команды.  <br/> |
|Политики хранения на уровне Организации в центре безопасности & соответствия требованиям  <br/> |Нет значения  <br/> или  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(указывает, что почтовый ящик исключен из политики на уровне Организации)  <br/> |Даже если при запуске командлета **Get-Mailbox** свойство *InPlaceHolds* не задано, по-прежнему могут быть применены одна или несколько политик хранения на уровне Организации к почтовому ящику.  <br/> Чтобы убедиться в этом, можно выполнить `Get-OrganizationConfig | FL InPlaceHolds` команду в Exchange Online PowerShell, чтобы получить список идентификаторов GUID для политик хранения на уровне Организации. GUID для политик хранения на уровне Организации, применяемых к почтовым ящикам Exchange, начинается с `mbx` префикса, например `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Чтобы обозначить политику хранения на уровне Организации, которая применяется к почтовому ящику, выполните следующую команду в консоли безопасности & центра соответствия требованиям: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Если почтовый ящик исключен из политики хранения на уровне Организации, идентификатор GUID для политики хранения отображается в свойстве *InPlaceHolds* почтового ящика пользователя при запуске командлета **Get-Mailbox** . Он определяется по префиксу `-mbx` , например`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|удержание дел обнаружения электронных данных в центре безопасности & соответствия требованиям  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |Свойство *InPlaceHolds* также содержит GUID всех удержаний, связанных с вариантом обнаружения электронных данных в центре безопасности & соответствия требованиям, который может быть размещен в почтовом ящике. То, что это удержание по делу обнаружения электронных данных, можно понять по префиксу GUID  `UniH`.  <br/> Вы можете использовать `Get-CaseHoldPolicy` командлет в PowerShell центра безопасности & соответствия требованиям, чтобы получить сведения о том случае обнаружения электронных данных, с которым связано удержание на почтовом ящике. Например, вы можете выполнить команду, `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` чтобы отобразить имя удержания в почтовом ящике. Be sure to remove the  `UniH` при выполнении этой команды.  <br/><br/> Для идентификации случая обнаружения электронных данных, с которым связано удержание, выполните следующие команды:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


