---
title: Развертывание изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: В этом пошаговом руководстве по развертыванию можно создать и настроить изолированный сайт группы SharePoint Online в Microsoft Office 365.
ms.openlocfilehash: 05fdbcfff792805708bfe0b8027e955d54a1ec6f
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755228"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Развертывание изолированного сайта группы SharePoint Online

 **Сводка.** С помощью этих пошаговых инструкций можно развернуть новый изолированный сайт группы SharePoint Online.
  
This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Этап 1: создание и заполнение групп доступа к сайту группы

На этом этапе вы создаете три группы доступа на основе Azure AD для трех групп SharePoint по умолчанию и заполняете их соответствующими учетными записями пользователей.
  
> [!NOTE]
> The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Шаг 1. Составление списка администраторов сайта SharePoint Online

Определите набор учетных записей пользователей для администраторов изолированного сайта группы SharePoint Online.
  
Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать Windows PowerShell, создайте список имен участников-пользователей (UPN) (пример имени участника-пользователя: belindan@contoso.com).
  
### <a name="step-2-list-the-members-for-the-site"></a>Шаг 2. Составление списка участников сайта

Определите набор учетных записей пользователей для участников изолированного сайта группы, т. е. для тех, кто будет совместно работать с ресурсами, хранящимися на сайте.
  
Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, создайте список их UPN. Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Шаг 3. Составление списка посетителей сайта

Определите набор учетных записей пользователей для посетителей изолированного сайта группы, т. е. для тех, кто может просматривать ресурсы, хранящиеся на сайте, но не может изменять их или напрямую совместно работать с их содержимым.
  
Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, создайте список их UPN. Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.
  
Читателями сайта могут быть руководители, юрисконсульты или межведомственные заинтересованные лица.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Шаг 4. Создание трех групп доступа для сайта в Azure AD

Вам нужно создать в Azure AD следующие группы доступа:
  
- Администраторы сайта (список из шага 1)
    
- Участники сайта (список из шага 2)
    
- Читатели сайта (список из шага 3)
    
1. В браузере перейдите на портал Azure [https://portal.azure.com](https://portal.azure.com) и войдите, используя учетные данные, назначенные администратором управления пользователями или ролью администратора организации.
    
2. На портале Azure выберите **Azure Active Directory > Группы**.
    
3. В колонке **Группы — Все группы** выберите пункт **+ Создать группу**.
    
4. В новой колонке **группы** :
    
    - В разделе **Тип группы** выберите **Безопасность**.

    - Введите имя группы в поле **имя**.

    - Введите описание группы в поле **Описание группы**.

    - Выберите **Назначенные** в поле **Тип членства**.
    
5. Нажмите кнопку **Создать**, а затем закройте колонку **Группа**.
    
6. Повторите шаги 3-5 для дополнительных групп.
    
> [!NOTE]
> Для создания групп с включенными функциями Office необходимо использовать портал Azure. Если изолированный сайт SharePoint Online позже настраивается как сайт с строго конфиденциальной информацией с меткой Azure Information Protection для шифрования файлов и назначения разрешений определенным группам, разрешенные группы должны быть созданы с включенными функциями Office. После создания группы Azure AD невозможно изменить параметр компонентов Office для группы Azure AD. 
  
Ниже показана итоговая конфигурация с тремя группами доступа к сайту.
  
![Три группы доступа для развертывания изолированного сайта SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Этап 5. Добавление учетных записей пользователей в группы доступа

На этом шаге выполните указанные ниже действия.
  
1. Добавьте список пользователей из шага 1 в группу доступа для администраторов сайта.
    
2. Добавьте список пользователей из шага 2 в группу доступа для участников сайта.
    
3. Добавьте список пользователей из шага 3 в группу доступа для читателей сайта.
    
Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory (AD DS), добавьте пользователей в соответствующие группы доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской Microsoft 365.
  
Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell. Если у вас есть дублирующиеся имена групп для любой группы доступа, следует использовать центр администрирования Microsoft 365.
  
Для центра администрирования Microsoft 365 войдите в систему, используя учетную запись пользователя, которой назначена роль администратора учетных записей или администратора организации, и используйте группы, чтобы добавить соответствующие учетные записи пользователей и группы в соответствующие группы доступа.
  
Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Затем используйте следующий блок команд для добавления отдельной учетной записи пользователя в группу доступа:
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
Если вы сохранили имена участников-пользователей для учетных записей пользователей какой-либо из групп доступа в текстовом файле, воспользуйтесь следующим блоком команд PowerShell, чтобы добавить их все сразу:
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Для добавления отдельной группы в группу доступа PowerShell используйте следующий блок команд:
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

Результаты должны выглядеть следующим образом:
  
- Группа Azure AD "Администраторы сайта" содержит учетные записи пользователей или группы администраторов сайта
    
- Группа Azure AD "Участники сайта" содержит учетные записи пользователей или группы участников сайта.
    
- Группа Azure AD для посетителей сайта содержит учетные записи пользователей или группы, которые могут просматривать только содержимое сайта.
    
Проверяйте список участников группы для каждой группы доступа с помощью центра администрирования Microsoft 365 или с помощью следующего блока команд PowerShell:
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Ниже показана итоговая конфигурация с тремя группами доступа к сайтам, заполненными учетными записями пользователей или группами.
  
![Три группы доступа, заполненные учетными записями пользователей.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Этап 2. Создание и настройка изолированного сайта группы

На этом этапе вы создаете изолированный сайт SharePoint Online и настраиваете разрешения в соответствии с уровнями разрешений SharePoint Online по умолчанию, чтобы можно было использовать ваши новые группы доступа на основе Azure AD. По умолчанию новые сайты групп включают группу Microsoft 365 и другие связанные ресурсы, но в этом случае мы создадим сайт группы без группы Microsoft 365. Это позволяет полностью управлять разрешениями в SharePoint.
  
Сначала создайте сайт группы SharePoint Online, следуя приведенным ниже инструкциям.
  
1. Войдите в центр администрирования Microsoft 365 с помощью учетной записи, которая также будет использоваться для администрирования сайта группы SharePoint Online (администратор SharePoint Online). Дополнительные сведения см. в статье [Вход в Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. В центре администрирования Microsoft 365 в разделе **центры администрирования**щелкните **SharePoint**.

3. В центре администрирования SharePoint разверните узел **сайты** и выберите пункт **активные сайты**.

4. Нажмите кнопку **создать**, а затем выберите **другие параметры**.

5. В списке **выберите шаблон** выберите пункт **сайт группы**.
   
6. В поле **имя сайта**введите имя сайта группы. 
    
7. В поле **основной администратор**введите учетную запись, с которой вы вошли в систему.
 
8. Нажмите кнопку **Готово**.
    
Далее настройте разрешения на новом сайте группы SharePoint Online.
  
1. На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.

2. В разделе **общий доступ к сайту**щелкните ссылку **изменение способа совместного использования участниками**.

3. Выберите **только те владельцы сайтов, которые могут предоставлять общий доступ к файлам, папкам и сайтам**.

4. Установите параметр **Разрешить запросы на доступ** к **выходу**.

5. Нажмите кнопку **Сохранить**.
    
6. В области **разрешения** щелкните **Дополнительные параметры разрешений**.
    
7. На вкладке **разрешения** в браузере выберите ** \<site name> элементы** в списке.
    
8. В разделе **Пользователи и группы** нажмите кнопку **Создать**.
    
9. В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для участников сайта, выберите ее и нажмите **Поделиться**.
    
10. Нажмите кнопку "Назад" в браузере.
    
11. Выберите в списке пункт ** \<site name> владельцы** .
    
12. В разделе **Пользователи и группы** нажмите кнопку **Создать**.
    
13. В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для администраторов сайта, выберите ее и нажмите **Поделиться**.
    
14. Нажмите кнопку "Назад" в браузере.
    
15. Щелкните элемент ** \<site name> Посетители** в списке.
    
16. В разделе **Пользователи и группы** нажмите **Создание**.
    
17. В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для читателей сайта, выберите ее и нажмите **Поделиться**.
    
18. Закройте вкладку браузера **Разрешения**.
    
Ознакомьтесь с результатами настройки разрешений.
  
- Группа SharePoint ** \<site name> Owners** содержит группу доступа "Администраторы сайта", в которой все участники имеют уровень разрешений " **полный** доступ".
    
- Группа SharePoint ** \<site name> Members** содержит группу доступа "Участники сайта", в которой все участники имеют уровень разрешений " **изменить** ".
    
- Группа SharePoint Посетители содержит группу доступа ** \<site name> посетителей** сайта, в которой все участники имеют уровень разрешений **Чтение** .
    
- Участники не могут приглашать других участников, равно как и запрашивать доступ для лиц, не являющихся участниками.
    
Ниже показана итоговая конфигурация с тремя группами SharePoint для сайта, на котором настроено использование трех групп доступа, заполненных учетными записями пользователей или группами Azure AD.
  
![Последняя конфигурация изолированного сайта SharePoint Online с группами доступа и учетными записями пользователей.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
Теперь вы и участники сайта можете совместно работать с его материалами посредством участия в одной из групп доступа.
  
## <a name="next-step"></a>Следующий этап

Если вам нужно изменить состав группы доступа к сайту или создать папку документов с особыми разрешениями, см. статью [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>См. также

[Изолированные сайты групп SharePoint Online](isolated-sharepoint-online-team-sites.md)
  
[Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md)
  
[Управление изолированным сайтом группы SharePoint Online](manage-an-isolated-sharepoint-online-team-site.md)
  



