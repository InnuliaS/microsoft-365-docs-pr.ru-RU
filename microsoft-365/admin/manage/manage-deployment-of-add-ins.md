---
title: Развертывание надстроек в центре администрирования
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Узнайте, как развертывать надстройки для пользователей и групп в Организации с помощью централизованного развертывания в центре администрирования.
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102864"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Развертывание надстроек в центре администрирования

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Надстройки Office помогают настраивать документы и оптимизировать способ доступа к данным в Интернете (см. раздел [Начало работы с надстройкой Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Как администратор вы можете развертывать надстройки Office для пользователей в Организации с помощью функции централизованного развертывания в центре администрирования Microsoft 365. Централизованное развертывание — это рекомендуемый и наиболее полнофункциональный способ развертывания надстроек для пользователей и групп в Организации с широкими функциональными возможностями. 

Дополнительные сведения о том, как определить, поддерживает ли Организация централизованное развертывание, можно узнать в статье определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).

Дополнительные сведения об управлении надстройками после развертывания см в разделе Управление надстройками [в центре администрирования](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  В Word, Excel и PowerPoint с помощью [каталога приложений SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) можно развертывать надстройки для пользователей в локальной среде без подключения к Microsoft 365 и/или поддержки надстроек SharePoint. Для Outlook используйте панель управления Exchange для развертывания в локальной среде без подключения к Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Рекомендуемый подход к развертыванию надстроек Office

Чтобы развернуть надстройки с помощью поэтапного подхода, рекомендуется выполнить следующие действия:
  
1. Развертывание надстройки для небольшой группы заинтересованных лиц и участников ИТ-отдела. Если развертывание прошло успешно, перейдите к шагу 2.
    
2. Развертывание надстройки для большего числа пользователей в Организации. Опять же, оцените результаты и при успешном завершении переходите к полному развертыванию.
    
3. Выполните полное развертывание для всех пользователей.
    
В зависимости от размера целевой аудитории вы можете добавить или удалить этапы развертывания.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Развертывание надстройки Office с помощью центра администрирования

Прежде чем приступать к работе, ознакомьтесь со статьей определение того, [работает ли централизованное развертывание надстроек для вашей организации](centralized-deployment-of-add-ins.md).
  
1. В центре администрирования откройте страницу "параметры надстроек **Settings** \> **"** .
    
2. Выберите **развернуть надстройку** в верхней части страницы, а затем нажмите кнопку **Далее**.
    
3. Выберите параметр и следуйте инструкциям.
  
4. Если вы выбрали вариант добавления надстройки из магазина Office, сделайте выбор в надстройке. </br>

    Вы можете просматривать доступные надстройки по категориям: **предложено для вас**, **рейтинга**или **имени**. Из магазина Office доступны только бесплатные надстройки. В настоящее время возможность добавления платных надстроек не поддерживается. После выбора надстройки примите условия и условия, чтобы продолжить. <br/> 

    > [!NOTE] 
    > С помощью параметра магазин Office пользователи автоматически обновляются и улучшаются.

5. На следующей странице выберите " **все**", " **конкретные пользователи/группы**" или " **только я** ", чтобы указать, в кого развернута надстройка. Используйте поле поиска для поиска определенных пользователей или групп. <br/>

    > [!NOTE] 
    > Сведения о других состояниях, применяемых к надстройке, можно узнать в статье [состояния надстроек](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Нажмите **Развернуть**.
  
7. При развертывании надстройки отображается зеленый импульс. Следуйте инструкциям на странице, чтобы протестировать надстройку.

    > [!NOTE]
    > Пользователям может потребоваться перезапустить Office, чтобы просмотреть значок надстройки на ленте приложения. Для отображения на лентах приложений надстройки Outlook могут занимать до 24 часов.
    
8. По завершении нажмите кнопку **Далее**. Если вы развернули только себя, вы можете выбрать команду **изменить, кто имеет доступ к надстройке** , чтобы развернуть ее для большего числа пользователей.

    Если вы развернули надстройку для других участников Организации, следуйте указаниям, чтобы объявить о развертывании надстройки. <br/>
  
    Рекомендуется проинформировать пользователей и группы о том, что развернутая Надстройка доступна. Рассмотрите возможность отправки электронной почты, в которой описывается, когда и как использовать надстройку. Включение или ссылка на справочные материалы или часто задаваемые вопросы, которые могут помочь пользователям при возникновении проблем с надстройкой.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Рекомендации при назначении надстройки пользователям и группам

Администраторы могут назначить надстройку всем или отдельным пользователям и группам. Каждый вариант имеет ряд особенностей.
  
- **Все пользователи** Этот параметр назначает надстройку каждому пользователю в Организации. Используйте этот вариант осторожно и только для тех надстроек, которые действительно применяются во всей организации. 
    
- **Users (пользователи** ) Если вы назначаете надстройку отдельному пользователю и затем развертываете надстройку для нового пользователя, необходимо сначала добавить нового пользователя.
    
- **Groups (группы** ) При назначении надстройке группе пользователям, добавленным в группу, автоматически назначается эта надстройка. Когда пользователь удаляется из группы, он теряет доступ к надстройке. В любом случае в администраторе не требуются дополнительные действия. 

- **Только я** Если вы назначаете надстройку только для себя, надстройка будет назначена только вашей учетной записи, что лучше всего подходит для тестирования надстройки.
    
Правильный вариант вашей организации зависит от конфигурации. Тем не менее, рекомендуется делать назначения с помощью групп. Администратор может упростить управление надстройками с помощью групп и управления членством в этих группах, а не назначать отдельных пользователей каждый раз. В некоторых случаях может потребоваться ограничить доступ к небольшому набору пользователей, выполнив назначения определенным пользователям вручную.
  
## <a name="more-about-office-add-ins-security"></a>Дополнительные сведения о безопасности надстроек Office

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Выводить данные.
    
- Читать документ пользователя для предоставления контекстных услуг.
    
- Считывать данные из документа пользователя и записывать их в него для предоставления значений.
    
Дополнительные сведения о типах и возможностях надстроек Office см. в статье [Общие сведения о платформе надстроек Office](https://go.microsoft.com/fwlink/p/?linkid=846362) (на английском языке). Особое внимание обратите на раздел "Структура надстройки Office".
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Надстройки обновляются следующим образом:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > Администратору не нужно удалять бизнес-надстройку для обновления.   В разделе надстройки администратор может просто щелкнуть надстройку LOB и нажать **кнопку Обновить** в правом нижнем углу. Обновление будет работать только в том случае, если версия новой надстройки больше, чем у существующей надстройки.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>Дополнительные сведения

Создание и создание надстроек [Office](https://go.microsoft.com/fwlink/p/?linkid=846362)

[Управление надстройками в центре администрирования](manage-addins-in-the-admin-center.md)

[Вспомогательные и приобретение надстроек из магазина](minors-and-acquiring-addins-from-the-store.md)
  
[Использование командлетов PowerShell для централизованного развертывания для управления надстройками](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Устранение неполадок: пользователь не видит надстройки](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
