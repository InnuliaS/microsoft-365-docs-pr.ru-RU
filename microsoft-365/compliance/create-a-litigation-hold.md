---
title: Создание удержания для судебного разбирательства
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Сведения о том, как поместить почтовый ящик на хранение для судебного разбирательства, сохранив все содержимое почтовых ящиков во время расследования.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9c62dfcd9e4cf1e3cc75e029b250c7abe80de6df
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818048"
---
# <a name="create-a-litigation-hold"></a>Создание удержания для судебного разбирательства

Вы можете поместить почтовый ящик на хранение для судебного разбирательства, чтобы сохранить все содержимое почтового ящика, включая удаленные элементы и исходные версии измененных элементов. При помещении почтового ящика пользователя на хранение для судебного разбирательства также сохраняется содержимое архивного почтового ящика пользователя (если он включен). При создании удержания можно указать продолжительность удержания (также называемую *удержанием на основе времени*), чтобы удаленные и измененные элементы сохранялись в течение указанного периода, а затем окончательно удалены из почтового ящика. Или вы можете просто хранить контент в неопределенном состоянии (называемом *бесконечное удержание*) или пока не будет удалено удержание для судебного разбирательства. Если указать период хранения, он вычисляется с момента получения сообщения или создания элемента почтового ящика. 
  
Ниже показано, что происходит при создании удержания для судебного разбирательства.
  
- Элементы, которые пользователь навсегда удаляет, сохраняются в папке "элементы с возможностью восстановления" в почтовом ящике пользователя в течение периода удержания.
    
- Элементы, которые удаляются из папки "элементы с возможностью восстановления", сохраняются в течение срока хранения.
    
- Квота хранилища для папки "элементы с возможностью восстановления" увеличивается с 30 ГБ до 110 ГБ.
    
- Элементы в основном пользователе и архивные почтовые ящики сохраняются
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Назначение лицензии на Exchange Online (план 2)

- Чтобы поместить почтовый ящик Exchange Online на удержание для судебного разбирательства, ему необходимо назначить лицензию на Exchange Online (план 2). Если почтовому ящику назначена лицензия на Exchange Online (план 1), необходимо назначить ему отдельную лицензию на архивацию на базе Exchange Online, чтобы разместить ее на удержании.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Перевод почтового ящика в режим хранения для судебного разбирательства

Ниже описано, как поместить почтовый ящик на удержание для судебного разбирательства с помощью центра администрирования Exchange.

1. Войдите в систему [https://outlook.office.com/ecp](https://outlook.office.com/ecp) , используя свою учетную запись глобального администратора.

2. В левой области навигации щелкните **получатели > почтовые ящики** .

3. Выберите почтовый ящик, который необходимо поместить на удержание для судебного разбирательства, а затем нажмите кнопку **изменить**.

4. На странице свойств почтового ящика щелкните **Функции почтового ящика**.
    
5. В разделе **Хранение для судебного разбирательства: отключено** нажмите кнопку **Включить**, чтобы применить к почтовому ящику хранение для судебного разбирательства.
    
6. На странице " **удержание для судебного разбирательства** " введите следующие дополнительные сведения: 
    
    - **Срок хранения для судебного разбирательства (дни)** — это поле используется для создания удержания на основе времени и указания того, как долго почтовые ящики будут удерживаться при включении почтового ящика на хранение для судебного разбирательства. Этот срок рассчитывается с даты получения или создания элемента почтового ящика. По истечении срока хранения для определенного элемента этот элемент больше не будет сохраняться. Если оставить это поле пустым, элементы будут сохраняться неопределенное время или пока не будет удалено удержание. Длительность указывается в днях.
    
    - **Примечание** . это поле используется для информирования пользователя о своем почтовом ящике на удержание для судебного разбирательства. Примечание появится на странице сведения об учетной записи в почтовом ящике пользователя, если они используют Outlook 2010 или более поздней версии. Для доступа к этой странице пользователи могут щелкнуть **файл** в Outlook.
    
    - **URL-адрес** это поле используется для направления пользователя на веб-сайт для получения дополнительных сведений о удержании судебного разбирательства. Этот URL-адрес отображается на странице "сведения об учетной записи" в почтовом ящике пользователя, если они используют Outlook 2010 или более поздней версии. Для доступа к этой странице пользователи могут щелкнуть **файл** в Outlook...

7. Нажмите кнопку **сохранить** на странице " **удержание для судебного разбирательства** ", а затем нажмите кнопку **сохранить** на странице свойств почтового ящика.

### <a name="create-a-litigation-hold-using-powershell"></a>Создание хранения для судебного разбирательства с помощью PowerShell

Вы также можете создать удержание для судебного разбирательства, выполнив следующую команду в [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

В предыдущей команде сохраняются неограниченные элементы, так как срок хранения не указан. Чтобы создать удержание на основе времени, используйте следующую команду:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Дополнительные сведения см. в статье [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Как работает хранение для судебного разбирательства?

Если почтовый ящик не на хранении, после удаления с помощью клавиш Shift+Delete или удаления из папки "Удаленные" элемент перемещается в подпапку удаления в папке "Элементы с возможностью восстановления". По истечении срока хранения, заданного политикой удаления (тег хранения, для которого настроено действие хранения), элементы также перемещаются в подпапку удаления. Когда пользователь удаляет элемент в папке "Элементы с возможностью восстановления" или истекает срок хранения удаленного элемента, он перемещается в подпапку очистки и помечается для окончательного удаления. Он будет удален из Exchange при следующей обработке почтового ящика помощником для управляемых папок.

When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.

На следующем рисунке показаны подпапки в папке "Элементы с возможностью восстановления" и рабочий процесс хранения.

![Жизненный цикл хранения для судебного разбирательства](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Если удержание, связанное с вариантом обнаружения электронных данных, размещается для почтового ящика, удаленные элементы перемещаются из подпапки "удаления" в подпапку DiscoveryHolds и сохраняются до тех пор, пока почтовый ящик не будет выпущен из удержания обнаружения электронных данных.
  
