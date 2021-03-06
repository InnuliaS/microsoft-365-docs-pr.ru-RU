---
title: Удаление неактивного почтового ящика
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Если вы больше не хотите сохранять содержимое неактивного почтового ящика Microsoft 365, вы можете окончательно удалить неактивный почтовый ящик.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817898"
---
# <a name="delete-an-inactive-mailbox"></a>Удаление неактивного почтового ящика

Неактивный почтовый ящик используется для хранения электронной почты бывшего сотрудника после увольнения. Если больше нет необходимости хранить контент неактивного почтового ящика, можно окончательно удалить его, выключив режим хранения. Кроме того, возможно, что к неактивному почтовому ящику применяются несколько инцидентов удержания. Например, неактивный почтовый ящик может находиться в режиме хранения для судебного разбирательства или хранения на месте. Кроме того, политика хранения (созданная в центре безопасности и соответствия требованиям в Office 365 или Microsoft 365) может быть применена к неактивному почтовому ящику. Необходимо удалить все удержания и политики хранения из неактивного почтового ящика, чтобы удалить его. После удаления политик хранения и хранения неактивный почтовый ящик помечается для удаления и безвозвратно удаляется после его обработки.
  
> [!IMPORTANT]
> Так как мы будем хранить содержимое почтового ящика разными способами, мы сообщаем выбытие на месте в центре администрирования Exchange. Это означает, что для создания неактивного почтового ящика следует использовать удержания и политики хранения для судебного разбирательства. Начиная с 1 июля, 2020 вы не сможете создавать новые удержания на месте в Exchange Online. Но вы по-прежнему можете изменить срок хранения на месте, включенный для неактивного почтового ящика. Однако, начиная с 1 октября 2020, вы не сможете изменить срок хранения. Удаление неактивного почтового ящика позволит удалить удержание на месте. Существующие Неактивные почтовые ящики, которые включены в удержание на месте, будут сохранены до тех пор, пока не будет удалено удержание. Для получения дополнительных сведений о прекращении удержания на месте, ознакомьтесь со статьей [выбытие средств прежних версий электронных данных](legacy-ediscovery-retirement.md).
  
Описание того, что происходит после удаления инцидента удержания для неактивного почтового ящика, см. в статье [Дополнительные сведения](#more-information).
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Перед удалением неактивного почтового ящика

- Чтобы удалить удержание для судебного разбирательства из неактивного почтового ящика, необходимо использовать Exchange Online PowerShell. Вы не можете сделать этого в Центре администрирования Exchange (EAC). Пошаговые инструкции приведены [в статье подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Чтобы удалить удержание на месте из неактивного почтового ящика, можно использовать Exchange Online PowerShell или центр администрирования Exchange. 
    
- Вы можете скопировать содержимое неактивного почтового ящика в другой почтовый ящик, прежде чем удалить инцидент удержания и сам почтовый ящик. Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](restore-an-inactive-mailbox.md).
    
- Если удалить политику хранения или хранения из неактивного почтового ящика и срок хранения обратимо удаленного почтового ящика для почтового ящика, почтовый ящик будет окончательно удален. После удаления его невозможно будет восстановить. Прежде чем удалять инцидент удержания, убедитесь, что вам больше не требуется содержимое почтового ящика. Если вы захотите повторно активировать неактивный почтовый ящик, его можно восстановить. Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](recover-an-inactive-mailbox.md).
    
- Дополнительные сведения о неактивных почтовых ящиках приведены [в статье Неактивные почтовые ящики в Office 365](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Этап 1. Определение инцидентов удержания для неактивного почтового ящика

Как отмечалось ранее, хранение для судебного разбирательства, хранение на месте или политика хранения могут быть размещены на неактивном почтовом ящике. Первый шаг состоит в определении инцидентов удержания неактивного почтового ящика.
  
Выполните следующую команду, чтобы отобразить сведения об удержании для всех неактивных почтовых ящиков в организации.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Если для неактивного почтового ящика применено множество инцидентов хранения на месте, будут показаны не все идентификаторы GUID хранения. Для отображения всех идентификаторов GUID хранения на месте можно выполнить следующую команду:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Действие 2. Удаление инцидента удержания неактивного почтового ящика

After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox. 
  
### <a name="remove-a-litigation-hold"></a>Отключение хранения для судебного разбирательства

As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="remove-in-place-holds"></a>Отключение хранения на месте

 Отключить хранение на месте для неактивного почтового ящика можно двумя способами: 
  
- **Удаление объекта хранения на месте** Если неактивный почтовый ящик, который необходимо окончательно удалить, является единственным исходным почтовым ящиком для хранения на месте, можно просто удалить объект хранения на месте. 
    
    > [!NOTE]
    > You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message. 
  
- **Удалить неактивный почтовый ящик как исходный почтовый ящик хранения на месте**. Если вы хотите сохранить другие исходные почтовые ящики для хранения на месте, можно удалить неактивный почтовый ящик из списка исходных почтовых ящиков и сохранить объект хранения на месте. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Использование Центра администрирования Exchange для отключения хранения на месте

1. If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Выберите удержание на месте, которое нужно удалить, а затем нажмите кнопку **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. В окне предупреждения щелкните **Да**, чтобы удалить инцидент хранения на месте. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Удаление хранения на месте с помощью Exchange Online PowerShell

1. Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Отключите хранение на месте.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Затем удалите инцидент хранения на месте.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Использование Центра администрирования Exchange для отключения хранения на месте неактивного почтового ящика

1. If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Выберите удержание на месте для неактивного почтового ящика, а затем щелкните **изменить** ![ значок редактирования ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. В списке исходных почтовых ящиков щелкните имя неактивного почтового ящика, который требуется удалить, а затем нажмите кнопку **Удалить**![Значок "Удалить"](../media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Click **Save** to save the change. A message is displayed saying the operation was successfully completed. 
    
7. Повторите шаги с 1 по 6, чтобы удалить другие инциденты хранения на месте для неактивного почтового ящика.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Удаление неактивного почтового ящика из хранения на месте с помощью Exchange Online PowerShell

Если инцидент хранения на месте содержит большое количество исходных почтовых ящиков, возможно, что неактивный почтовый ящик не будет показан на странице **Источники** в Центре администрирования Exchange. При редактировании инцидента хранения на месте на странице **Источники** отображаются до 3000 почтовых ящиков. Если неактивный почтовый ящик не указан на странице **источники** , можно удалить его из удержания на месте с помощью Exchange Online PowerShell. 
  
1. Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Убедитесь, что неактивный почтовый ящик указан как исходный почтовый ящик для хранения на месте. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Примечание:** Свойство *Sources* хранения на месте определяет исходные почтовые ящики по их свойствам *legacyExchangeDN* . Поскольку это свойство уникально идентифицирует неактивные почтовые ящики, использование свойства *Sources* хранения на месте предотвращает удаление неверного почтового ящика. Это также позволяет избежать проблем, если у двух почтовых ящиков одинаковый псевдоним или SMTP-адрес. 
   
3. Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Например, следующая команда удаляет неактивный почтовый ящик для пользователя Pilar Pinilla.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков в переменной.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. Измените инцидент хранения на месте, используя обновленный список исходных почтовых ящиков, в который не входит неактивный почтовый ящик.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Убедитесь, что неактивный почтовый ящик удален из списка исходных почтовых ящиков для хранения на месте.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Дополнительные сведения

- **An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered. 
    
- **Что происходит после удаления удержания на неактивном почтовом ящике?** Почтовый ящик рассматривается как другие обратимо удаленные почтовые ящики и помечается для окончательного удаления после истечения 30-дневного периода хранения с обратимым удаленным почтовым ящиком. Этот период хранения начинается с даты первого совершения почтовых ящиков в неактивном состоянии. Эта дата известна как дата обратимого удаления, которая соответствует дате удаления соответствующей учетной записи пользователя или при удалении почтового ящика Exchange Online с помощью командлета **Remove-Mailbox** . Дата обратимого удаления не является датой, на которую вы удаляете удержание. 
    
- **Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed. 
    
- **Как период хранения обратимо удаленного почтового ящика влияет на неактивные почтовые ящики?** Если дата удаления неактивного почтового ящика превышает 30 дней до даты, когда была удалена удержание, почтовый ящик помечается для постоянного удаления. Но если дата обратимого удаления неактивного почтового ящика попадает в последние 30 дней и вы удалите инцидент удержания, почтовый ящик можно восстановить до истечения срока хранения обратимо удаленного почтового ящика. Дополнительные сведения см. [в статье Удаление или восстановление почтовых ящиков пользователей в Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). После истечения срока хранения обратимо удаленных почтовых ящиков вы можете восстановить неактивный почтовый ящик. Дополнительные сведения см. [в статье восстановление неактивного почтового ящика в Office 365](recover-an-inactive-mailbox.md).
    
- **Как отобразить сведения о неактивном почтовом ящике после снятия с удержания?** После удаления удержания и возврата неактивного почтового ящика обратно в обратимо удаленный почтовый ящик он не будет возвращен с помощью параметра *инактивемаилбоксонли* командлета **Get-Mailbox** . Однако вы можете отобразить сведения о почтовом ящике с помощью команды **Get-Mailbox -SoftDeletedMailbox**. Например: 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  В приведенном выше примере свойство *WhenSoftDeleted* определяет дату обратимого удаления, которая в данном примере составляет 30 октября 2014 г. Если этот Обратимо удаленный почтовый ящик ранее был неактивным почтовым ящиком, для которого было удалено удержание, оно будет безвозвратно удалено в течение 30 дней после значения свойства *WhenSoftDeleted* . В этом случае почтовый ящик окончательно удаляется после 30 ноября 2014 г.

