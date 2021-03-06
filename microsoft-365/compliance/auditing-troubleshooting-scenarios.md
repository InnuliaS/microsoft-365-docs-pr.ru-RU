---
title: Поиск в журнале аудита для устранения распространенных сценариев
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
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать средство поиска в журнале аудита Office 365 для устранения распространенных проблем с поддержкой учетных записей электронной почты.
ms.openlocfilehash: e370a0220fcc42854d3cc570e175ab96845f7d4b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351132"
---
# <a name="search-the-audit-log-to-investigate-common-support-issues"></a>Поиск в журнале аудита для изучения распространенных проблем с поддержкой

В этой статье описано, как использовать средство поиска журнала аудита для изучения распространенных проблем с поддержкой. Это включает в себя использование журнала аудита для:

- Поиск IP-адреса компьютера, используемого для доступа к скомпрометированной учетной записи
- Определение пользователей, которые настраивают переадресацию электронной почты для почтового ящика
- Определение того, удалил ли пользователь элементы электронной почты в своем почтовом ящике
- Определение того, было ли пользователь создал правило для папки "Входящие"
- Выясните причину успешного входа пользователя за прев Организации

## <a name="using-the-audit-log-search-tool"></a>Использование средства поиска журнала аудита

Все сценарии устранения неполадок, описанные в этой статье, основаны на использовании средства поиска журнала аудита в центре безопасности & соответствия требованиям. В этом разделе перечислены разрешения, необходимые для поиска в журнале аудита, а также описаны действия, необходимые для доступа и запуска операций поиска в журнале аудита. В каждом разделе описывается настройка поискового запроса в журнале аудита и то, что следует искать в подробных сведениях в записях аудита, которые отвечают условиям поиска.

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>Разрешения, необходимые для использования средства поиска журнала аудита

Для поиска в журнале аудита необходимо назначить роль "журналы аудита только для просмотра" или "журналы аудита" в Exchange Online. Эти роли по умолчанию назначены группам ролей "Управление соответствием" и "Управление организацией" на странице **Разрешения** в Центре администрирования Exchange. Глобальные администраторы в Office 365 и Microsoft 365 автоматически добавляются в группу ролей Управление организацией в Exchange Online. Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

### <a name="running-audit-log-searches"></a>Выполнение операций поиска в журнале аудита

В этом разделе описываются основные принципы создания и запуска операций поиска в журнале аудита. Используйте эти инструкции в качестве отправной точки для каждого сценария устранения неполадок, описанных в этой статье. Для получения более подробных пошаговых инструкций обратитесь к разделу [Поиск в журнале аудита](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).

1. Перейдите на страницу [https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog) и войдите с помощью рабочей или учебной учетной записи.
    
    Откроется страница **Поиск в журнале аудита**. 
    
    ![Настройте условия, а затем нажмите кнопку Поиск, чтобы выполнить поиск.](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. Можно настроить следующие условия поиска. В каждом сценарии устранения неполадок, описанном в этой статье, рекомендуется присвоить им рекомендации по настройке этих полей.
    
    а) **Действия:** Выберите раскрывающийся список, чтобы отобразить действия, которые можно найти. После выполнения поиска отображаются только записи аудита для выбранных действий. При выборе пункта **Показать результаты для всех действий** отображаются результаты для всех действий, соответствующих другим условиям поиска. Кроме того, в некоторых сценариях устранения неполадок необходимо оставить это поле пустым.
    
    б) **Дата начала** и **Дата окончания:** выберите диапазон дат и времени для отображения событий, произошедших в течение этого периода. По умолчанию выбраны последние семь дней. Даты и время представлены в формате UTC. Максимальный диапазон дат, который можно указать, составляет 90 дней.

    в. **Пользователи:** Щелкните в этом поле, а затем выберите одного или нескольких пользователей, для которых нужно отобразить результаты поиска. В списке результатов отображаются записи аудита для выбранного действия, выполняемого пользователями, выбранными в этом поле. Чтобы получить результаты для всех пользователей (и учетных записей служб) в организации, оставьте это поле пустым.
    
    г. **Файл, папка или сайт:** Введите имя файла или папки, чтобы найти действия, связанные с файлом папки, содержащей заданное ключевое слово. Также можно указать URL-адрес файла или папки. Если вы используете URL-адрес, убедитесь, что введите полный URL-путь или только часть URL-адреса, не включайте специальные символы и пробелы. Чтобы получить результаты для всех файлов и папок в организации, оставьте это поле пустым. Это поле остается пустым во всех сценариях устранения неполадок, описанных в этой статье.
    
5. Выберите **Поиск** , чтобы выполнить поиск, используя условия поиска. 
    
    Результаты поиска загружаются, а через некоторое время они отображаются в разделе **результаты** на странице " **Поиск журнала аудита** ". В каждом из разделов этой статьи представлены рекомендации по поиску в контексте определенного сценария устранения неполадок.

    Дополнительные сведения о просмотре, фильтрации и экспорте результатов поиска в журнале аудита приведены в следующих статьях:

    - [Просмотр результатов поиска](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [Фильтрация результатов поиска](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [Экспорт результатов поиска](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>Поиск IP-адреса компьютера, используемого для доступа к скомпрометированной учетной записи

IP-адрес, соответствующий действиям, выполняемым любым пользователем, включается в большинство записей аудита. Сведения об используемом клиенте также включены в запись аудита.

Вот как настроить поисковый запрос журнала аудита для этого сценария:

**Действия:** В случае необходимости выберите конкретное действие для поиска. Для устранения неполадок, связанных с скомпрометированными учетными записями, рассмотрите возможность выбора **пользователя, вошедшего в действие почтовых** ящиков в разделе **действия** При этом возвращаются записи аудита, отображающие IP-адрес, который использовался при входе в почтовый ящик. В противном случае оставьте это поле пустым, чтобы получить записи аудита для всех действий. 

> [!TIP]
> Если оставить это поле пустым, будут возвращены действия **усерлогжедин** , являющиеся действием Azure Active Directory, которое указывает, что кто-то выполнил вход в учетную запись пользователя. Используйте фильтрацию в результатах поиска, чтобы отобразить записи аудита **усерлогжедин** .

**Дата начала** и **Дата окончания:** выберите диапазон дат, который применяется к расследованию.

**Пользователи:** Если вы изучаете скомпрометированную учетную запись, выберите пользователя, для которого была скомпрометирована учетная запись. Это возвращает записи аудита для действий, выполняемых этой учетной записью пользователя.

**Файл, папка или сайт:** Оставьте это поле пустым.

После выполнения поиска IP-адрес каждого действия отображается в столбце **IP-адрес** в результатах поиска. Выберите запись в результатах поиска, чтобы получить более подробные сведения о всплывающей странице.

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>Определение пользователей, которые настраивают переадресацию электронной почты для почтового ящика

При настройке переадресации электронной почты для почтового ящика сообщения электронной почты, отправленные в почтовый ящик, пересылаются в другой почтовый ящик. Сообщения могут пересылаться пользователям в организации или за ее пределами. При настройке переадресации электронной почты для почтового ящика используется базовый командлет Exchange Online — **Set-Mailbox**.

Вот как настроить поисковый запрос журнала аудита для этого сценария:

**Действия:** Оставьте это поле пустым, чтобы поиск возвращал записи аудита для всех действий. Это необходимо для возврата записей аудита, относящихся к командлету **Set-Mailbox** .

**Дата начала** и **Дата окончания:** выберите диапазон дат, который применяется к расследованию.

**Пользователи:** Если вы не изучаете проблему переадресации электронной почты для определенного пользователя, оставьте это поле пустым. Это помогает определить, настроена ли переадресация электронной почты для любого пользователя.

**Файл, папка или сайт:** Оставьте это поле пустым.

После выполнения поиска выберите пункт **результаты фильтра** на странице результатов поиска. В поле Заголовок столбца **активности** введите **Set — Mailbox** , чтобы отображались только записи аудита, связанные с командлетом **Set — Mailbox** .

![Фильтрация результатов поиска в журнале аудита](../media/emailforwarding1.png)

На этом шаге необходимо просмотреть сведения о каждой записи аудита, чтобы определить, связано ли действие с переадресацией электронной почты. Выберите запись аудита для отображения всплывающей страницы **сведений** , а затем выберите **Дополнительные сведения**. Приведенный ниже снимок экрана и описания выделяют сведения, которые указывают, что для почтового ящика задана переадресация электронной почты.

![Подробные сведения из записи аудита](../media/emailforwarding2.png)

а) В поле **ObjectID** отображается псевдоним почтового ящика, для которого было задано пересылка электронной почты. Этот почтовый ящик также отображается в столбце **элемент** на странице результатов поиска.

б) В поле **Параметры** значение *ForwardingSmtpAddress* указывает, что для почтового ящика задана переадресация электронной почты. В этом примере почта перенаправляется на адрес электронной почты mike@contoso.com, который находится за прев Организации alpinehouse.onmicrosoft.com.

в. Значение *true* для параметра *DeliverToMailboxAndForward* указывает на то, что копия сообщения доставляется в sarad@alpinehouse.onmicrosoft.com *и* переадресована на адрес электронной почты, указанный параметром *ForwardingSmtpAddress* , в данном примере — Mike@contoso.com. Если для параметра *DeliverToMailboxAndForward* задано значение *false*, электронная почта пересылается только по адресу, указанному в параметре *ForwardingSmtpAddress* . Он не доставляется в почтовый ящик, указанный в поле **ObjectID** .

г. Поле **UserID** указывает пользователя, который настроил переадресацию электронной почты в почтовом ящике, указанном в поле **ObjectID** . Этот пользователь также отображается в столбце **пользователь** на странице результатов поиска. В этом случае возникает впечатление, что владелец почтового ящика настраивает переадресацию электронной почты на своем почтовом ящике.

Если вы определили, что перенаправление электронной почты не следует устанавливать для почтового ящика, вы можете удалить его, выполнив следующую команду в Exchange Online PowerShell:

```powershell
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

Дополнительные сведения о параметрах, связанных с переадресацией электронной почты, приведены в статье [Set/Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) .

## <a name="determine-if-a-user-deleted-email-items"></a>Определение того, удалил ли пользователь элементы электронной почты

Начиная с 2019 января Корпорация Майкрософт расписывает ведение журнала аудита почтовых ящиков по умолчанию для всех организаций Office 365 и Майкрософт. Это означает, что определенные действия, выполняемые владельцами почтовых ящиков, регистрируются автоматически, и соответствующие записи аудита почтовых ящиков будут доступны при поиске их в журнале аудита почтовых ящиков. Если аудит почтовых ящиков включен по умолчанию, необходимо вручную включить его для каждого почтового ящика пользователя в Организации. 

Действия почтового ящика, регистрируемые по умолчанию, включают действия почтового ящика SoftDelete и HardDelete, выполняемые владельцами почтового Это означает, что вы можете использовать следующие действия для поиска событий, относящихся к удаленным элементам электронной почты, в журнале аудита. Дополнительные сведения об аудите почтовых ящиков по умолчанию содержатся в разделе [Управление аудитом почтовых ящиков](enable-mailbox-auditing.md).

Вот как настроить поисковый запрос журнала аудита для этого сценария:

**Действия:** В разделе **действия почтового ящика Exchange**выберите одно или оба из следующих действий:

- **Удаленные сообщения из папки "Удаленные":** Это действие соответствует действию аудита почтового ящика **SoftDelete** . Это действие также заносится в журнал, когда пользователь окончательно удаляет элемент, выбирая его и нажимая клавиши **SHIFT + DELETE**. После окончательного удаления элемента пользователь сможет восстановить его до истечения срока хранения удаленных элементов.

- **Очищенные сообщения из почтового ящика:** Это действие соответствует действию аудита почтового ящика **HardDelete** . Он записывается в журнал, когда пользователь удаляет элемент из папки "элементы с возможностью восстановления". Администраторы могут использовать средство "поиск контента" в центре безопасности и соответствия требованиям для поиска и восстановления очищенных элементов до истечения срока хранения удаленных элементов, если почтовый ящик пользователя находится на удержании.

**Дата начала** и **Дата окончания:** выберите диапазон дат, который применяется к расследованию.

**Пользователи:** Если в этом поле выбран пользователь, средство поиска журнала аудита возвращает записи аудита для элементов электронной почты, которые были удалены пользователем (SoftDeleted или Хардделетед) указанным пользователем. Иногда пользователь, который удаляет электронную почту, может не являться владельцем почтового ящика.

**Файл, папка или сайт:** Оставьте это поле пустым.

После выполнения поиска можно отфильтровать результаты поиска, чтобы отобразить записи аудита для обратимо удаленных элементов или для окончательно удаленных элементов. Выберите запись аудита для отображения всплывающей страницы **сведений** , а затем выберите **Дополнительные сведения**. Дополнительные сведения об удаленном элементе, такие как строка темы и расположение элемента при его удалении, отображаются в поле **аффектедитемс** . На следующих снимках экрана показан пример поля **аффектедитемс** из обратимо удаленного элемента и окончательно удаленного элемента.

**Пример поля Аффектедитемс для обратимо удаленного элемента**

![Запись аудита для обратимо удаленного элемента](../media/softdeleteditem.png)

**Пример поля Аффектедитемс для окончательного удаления элемента**

![Запись аудита для окончательно удаленного элемента электронной почты](../media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>Восстановление удаленных элементов электронной почты

Пользователи могут восстанавливать обратимо удаленные элементы, если срок хранения удаленных элементов еще не истек. В Exchange Online срок хранения удаленных элементов по умолчанию составляет 14 дней, но администраторы могут увеличить значение этого параметра до 30 дней. Направьте пользователей на [Восстановление удаленных элементов или электронной почты в Outlook в веб-](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) статье, чтобы получить инструкции по восстановлению удаленных элементов.

Как описывалось ранее, администраторы могут восстанавливать необратимо удаленные элементы, если срок хранения удаленных элементов не истек, или если почтовый ящик находится на удержании, в этом случае элементы сохраняются до истечения срока хранения. При выполнении поиска контента обратимо удаленные и обратимо удаленные элементы в папке "элементы с возможностью восстановления" возвращаются в результатах поиска, если они совпадают с поисковым запросом. Дополнительные сведения о выполнении поиска контента см в разделе [Поиск содержимого в Office 365](content-search.md).

> [!TIP]
> Чтобы найти удаленные элементы электронной почты, выполните поиск всей строки темы или ее части, отображаемой в поле **аффектедитемс** записи аудита.

## <a name="determine-if-a-user-created-an-inbox-rule"></a>Определение того, было ли пользователь создал правило для папки "Входящие"

Когда пользователи создают правило папки "Входящие" для почтового ящика Exchange Online, соответствующая запись аудита сохраняется в журнале аудита. Дополнительные сведения о правилах для папки "Входящие" можно найти в следующих статьях:

- [Использование правил для папки "Входящие" в Outlook в Интернете](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [Управление сообщениями электронной почты в Outlook с помощью правил](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

Вот как настроить поисковый запрос журнала аудита для этого сценария:

**Действия:** В разделе **действия почтового ящика Exchange**выберите Создать, **InboxRule создать/изменить/включить/отключить правило для папки "Входящие"**.

**Дата начала** и **Дата окончания:** выберите диапазон дат, который применяется к расследованию.

**Пользователи:** Если вы не изучаете определенного пользователя, оставьте это поле пустым. Это помогает определить новые правила для папки "Входящие", настроенные любым пользователем.

**Файл, папка или сайт:** Оставьте это поле пустым.

После выполнения поиска все записи аудита для этого действия отображаются в результатах поиска. Выберите запись аудита для отображения всплывающей страницы **сведений** , а затем выберите **Дополнительные сведения**. Сведения о параметрах правила папки "Входящие" отображаются в поле **Параметры** . На следующем снимке экрана и описаниях выделены сведения о правилах для папки "Входящие".

![Запись аудита для нового правила папки "Входящие"](../media/NewInboxRuleRecord.png)

а) В поле **ObjectID** отображается полное имя правила для папки "Входящие". Это имя включает псевдоним почтового ящика пользователя (например, Сарад) и имя правила для папки "Входящие" (например, "перемещение сообщений от администратора").

б) В поле **Параметры** отображается условие правила для папки "Входящие". В этом примере условие задается с помощью параметра *from* . Значение, заданное для параметра *from* , указывает, что правило для папки "Входящие" действует в сообщениях, отправленных Admin@alpinehouse.onmicrosoft.com. Полный список параметров, которые можно использовать для определения условий правил для папки "Входящие", представлен в статье [New – InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) .

в. Параметр *MoveToFolder* указывает действие для правила папки "Входящие". В этом примере сообщения, полученные от admin@alpinehouse.onmicrosoft.com, перемещаются в папку с именем *админсеарч*. Кроме того, в статье [New – InboxRule](https://docs.microsoft.com/powershell/module/exchange/new-inboxrule) представлен полный список параметров, которые можно использовать для определения действия правила папки "Входящие".

г. Поле **UserID** указывает пользователя, создавшего правило для папки "Входящие", которое указано в поле **ObjectID** . Этот пользователь также отображается в столбце **пользователь** на странице результатов поиска.

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>Выясните причину успешного входа пользователя за прев Организации

При просмотре записей аудита в журнале аудита могут отображаться записи, указывающие, что внешний пользователь прошел проверку подлинности Azure Active Directory и успешно выполнил вход в организацию. Например, администратор в contoso.onmicrosoft.com может увидеть запись аудита, в которой показано, что пользователь из другой организации (например, fabrikam.onmicrosoft.com) успешно вошел в contoso.onmicrosoft.com. Аналогично, вы можете увидеть записи аудита, указывающие пользователей с помощью учетной записи Майкрософт (MSA), например, Outlook.com или Live.com, успешно выполнили вход в организацию. В этих случаях аудитное действие является пользователем, **вошедшим в систему**. 

Такое поведение является особенностью данного продукта. Azure Active Directory (Azure AD), Служба каталогов, позволяет выполнить *сквозную проверку подлинности* при попытке внешнего пользователя получить доступ к сайту SharePoint или расположению OneDrive в вашей организации. Когда внешний пользователь попытается сделать это, ему будет предложено ввести учетные данные. Azure AD использует учетные данные для проверки подлинности пользователя, что означает, что только Azure AD проверяет, есть ли у пользователя то, что они говорят. В результате проверки подлинности пользователя с помощью Azure AD отображается значение, указывающее, что успешный вход в запись аудита. Успешный вход не означает, что пользователь мог получить доступ к ресурсам или выполнять другие действия в Организации. Он только указывает, что пользователь прошел проверку подлинности с помощью Azure AD. Чтобы получить доступ к ресурсам SharePoint или OneDrive для транзитного пользователя, пользователю в вашей организации потребуется предоставить общий доступ к ресурсу для внешнего пользователя, отправив ему приглашение для совместного доступа или ссылку для анонимного доступа. 

> [!NOTE]
> Azure AD разрешает сквозную проверку подлинности только для *приложений First-производителей*, таких как SharePoint Online и OneDrive для бизнеса. Оно не разрешено для других сторонних приложений.

Ниже приведен пример и описание соответствующих свойств в записи аудита для события, **зарегистрированного пользователем** , которое является результатом сквозной проверки подлинности. Выберите запись аудита для отображения всплывающей страницы **сведений** , а затем выберите **Дополнительные сведения**.

![Пример записи аудита для успешной сквозной проверки подлинности](../media/PassThroughAuth1.png)

   а) Это поле указывает на то, что пользователь, пытающийся получить доступ к ресурсу в вашей организации, не был найден в Azure AD вашей организации.

   б) В этом поле отображается имя участника-пользователя для внешнего пользователя, который пытался получить доступ к ресурсу в Организации. Этот идентификатор пользователя также определяется в свойствах **User** и **UserID** в записи аудита.

   в. Свойство **applicationId** определяет приложение, которое инициировало запрос на вход. Значение является 00000003-0000-0ff1-ce00-000000000000, отображаемое в свойстве ApplicationId этой записи аудита, указывает SharePoint Online. Приложение OneDrive для бизнеса также имеет такой же ApplicationId.

   г. Это означает, что проверка подлинности прошла успешно. Другими словами, пользователь успешно прошел проверку подлинности с помощью Azure AD. 

   д. Значение **RecordType** , равное **15** , указывает на то, что проверяемое действие (усерлогжедин) является событием входа в службу маркеров безопасности (STS) в Azure AD.

Дополнительные сведения о других свойствах, отображаемых в записи аудита Усерлогжедин, можно найти в статье сведения о схеме, связанную с Azure AD, в [схеме API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema).

Ниже приведены два примера сценариев, которые приводили к успешному **выполнению входа пользователя в систему** из-за сквозной проверки подлинности. 

  - Пользователь с учетной записью Майкрософт (например, SaraD@outlook.com) попытался получить доступ к документу в учетной записи OneDrive для бизнеса в fourthcoffee.onmicrosoft.com, и отсутствует соответствующая учетная запись пользователя-гостя для SaraD@outlook.com в fourthcoffee.onmicrosoft.com.

  - Пользователь с рабочей или учебной учетной записью в Организации (например, pilarp@fabrikam.onmicrosoft.com) попытался получить доступ к сайту SharePoint в contoso.onmicrosoft.com, и у пользователя нет соответствующей учетной записи гостя для pilarp@fabrikam.com в contoso.onmicrosoft.com.


### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>Советы по исследованию успешных учетных записей при сквозной проверке подлинности

- Поиск в журнале аудита действий, выполняемых внешним пользователем, указанным в записи аудита **пользователя, выполнившего вход в систему** . Введите имя участника-пользователя для внешнего пользователя в поле **Пользователи** и используйте диапазон дат, если это применимо к вашему сценарию. Например, вы можете создать поиск с помощью следующих условий поиска:

   ![Поиск всех действий, выполняемых внешним пользователем](../media/PassThroughAuth2.png)

    Помимо **пользователя, выполнившего вход в систему** , могут быть возвращены другие записи аудита, такие как пользователь в общих ресурсах Организации с внешним пользователем и как внешний пользователь обращался, изменен или скачал документ, к которому предоставлен доступ.

- Поиск действий общего доступа к SharePoint, указывающих на то, что общий доступ к файлу предоставлен внешнему пользователю, указанному **пользователем, вошедшим в** запись аудита. Для получения дополнительной информации см. раздел [Использование аудита совместного использования в журнале аудита](use-sharing-auditing.md).

- Экспортируйте результаты поиска журнала аудита, содержащие записи, относящиеся к расследованию, чтобы можно было использовать Excel для поиска других действий, связанных с внешним пользователем. Дополнительные сведения можно найти в статье [Экспорт, Настройка и просмотр записей журнала аудита](export-view-audit-log-records.md).
