---
title: Разработка изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Разработайте изолированные сайты групп SharePoint Online, в том числе определение уровней разрешений, назначение разрешений пользователям с помощью групп доступа и вложенные группы Azure AD.
ms.openlocfilehash: 821e15a05bc80e3795f9e18d4457416baf7145b7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209515"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Разработка изолированного сайта группы SharePoint Online

 **Сводка.** Пошаговое руководство по разработке изолированных сайтов групп SharePoint Online.
  
В этой статье описаны основные проектные решения, которые необходимо принять перед созданием изолированного сайта группы SharePoint Online.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Этап 1. Определение групп SharePoint и уровней разрешений

Каждый сайт группы SharePoint Online по умолчанию создается со следующими группами SharePoint:
  
- \<имя сайта> элементы
    
- \<имя сайта> посетителей
    
- \<Владельцы> имен сайтов
    
Эти группы отделены от групп Microsoft 365 и Azure Active Directory (AD) и являются основой для назначения разрешений для ресурсов сайта.
  
Набор разрешений, определяющий возможности члена группы SharePoint на сайте, — это уровень разрешений. По умолчанию для сайта группы SharePoint Online доступно три уровня разрешений: "Изменение", "Чтение" и "Полный доступ". В приведенной ниже таблице показаны группы SharePoint и назначенные им по умолчанию уровни разрешений.
  
|**Группа SharePoint**|**Уровень разрешений**|
|:-----|:-----|
|\<имя сайта> элементы  <br/> |Edit  <br/> |
|\<имя сайта> посетителей  <br/> |Чтение  <br/> |
|\<Владельцы> имен сайтов  <br/> |Полный доступ  <br/> |
   
 **Рекомендация.** Вы можете создавать дополнительные группы SharePoint и уровни разрешений. Но мы рекомендуем использовать заданные по умолчанию группы SharePoint и уровни разрешений для изолированного сайта SharePoint Online.
  
Ниже указаны группы SharePoint по умолчанию и уровни разрешений.
  
![Группы SharePoint по умолчанию и уровни разрешений для сайта SharePoint Online.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Этап 2. Назначение разрешений пользователям с помощью групп доступа

Можно назначить разрешения пользователям, добавив свою учетную запись пользователя или группу Microsoft 365 или Azure AD, членом которой является учетная запись пользователя, в группы SharePoint. После добавления учетным записям пользователей, напрямую или косвенно через членство в группе Microsoft 365 или Azure AD, назначается уровень разрешений, связанный с группой SharePoint.
  
Предоставление разрешений на примере групп SharePoint по умолчанию:
  
- Членам группы " ** \< имя сайта> участников** SharePoint", которая может включать как учетные записи пользователей, так и группы, назначается уровень разрешений " **изменить** ".
    
- Членам группы " ** \< имя сайта>** SharePoint", которая может включать как учетные записи пользователей, так и группы, назначается уровень разрешений " **Чтение** ".
    
- Членам группы SharePoint " ** \< имя сайта> владельцы** ", которая может включать как учетные записи пользователей, так и группы, назначается уровень разрешений " **полный** доступ".
    
 **Рекомендация.** Вы можете управлять разрешениями через отдельные учетные записи пользователей, но рекомендуем использовать для этого одну группу Azure AD (т. н. группу доступа). Это позволяет управлять разрешениями через членство в группе доступа, не управляя списком учетных записей для каждой группы SharePoint.
  
Группы Azure AD для Microsoft 365 отличаются са группами Microsoft 365. Группы Azure AD отображаются в центре администрирования Microsoft 365 с **типом** " **Безопасность** " и не имеют адреса электронной почты. Группами Azure AD можно управлять с помощью указанных ниже средств.
  
- Доменные службы Active Directory
    
    Это группы, созданные в локальной инфраструктуре AD DS и синхронизированные с подпиской на Microsoft 365. В центре администрирования Microsoft 365 для этих групп задано **состояние** " **синхронизирован" с Active Directory**.
    
- Office 365
    
    Это группы, созданные с помощью центра администрирования Microsoft 365, портала Azure или Microsoft PowerShell. В центре администрирования Microsoft 365 для этих групп задано **состояние** **Cloud**.
    
 **Рекомендация:** Если вы используете локальную службу доменных служб Active Directory и выполняете синхронизацию с вашей подпиской на Microsoft 365, выполните Управление пользователями и группами с помощью AD DS.
  
Рекомендуемая структура изолированных сайтов групп SharePoint Online указана ниже.
  
|**Группа SharePoint**|**Группа доступа на основе Azure AD**|**Уровень разрешений**|
|:-----|:-----|:-----|
|\<имя сайта> элементы  <br/> |\<имя сайта> элементы  <br/> |Edit  <br/> |
|\<имя сайта> посетителей  <br/> |\<имя сайта> средства просмотра  <br/> |Чтение  <br/> |
|\<Владельцы> имен сайтов  <br/> |\<имя сайта> администраторов  <br/> |Полный доступ  <br/> |
   
 **Рекомендация:** Несмотря на то что вы можете использовать группы Microsoft 365 или Azure AD в качестве членов групп SharePoint, мы рекомендуем использовать группы Azure AD. Группы Azure AD, управляемые с помощью AD DS или Microsoft 365, предоставляют вам больше гибкости для назначения разрешений с помощью вложенных групп.
  
Ниже приведены группы SharePoint по умолчанию, настроенные для использования групп доступа на основе Azure AD.
  
![Использование групп доступа в качестве членов групп сайтов SharePoint Online по умолчанию.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
При создании трех групп доступа учитывайте следующее:
  
- В группе ** \< "имя сайта> группы доступа" Администраторы "** должно быть только несколько членов, соответствующих небольшому числу администраторов SharePoint Online, которые управляют сайтом группы.
    
- Большинство участников сайта находятся в ** \< имени сайта> элементы** или ** \< имя сайта>** группы доступа к читателям. Так как члены сайта в группе доступа к ** \< имени сайта> участников** имеют возможность удалять или изменять ресурсы на сайте, тщательно изучите их участников. При возникновении сомнений добавьте участника сайта в группу " ** \< имя сайта> доступ к зрителям** ".
    
Ниже приведен пример групп SharePoint и групп доступа для изолированного сайта с именем ProjectX.
  
![Пример использования групп доступа для сайта SharePoint Online с именем ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Этап 3: использование вложенных групп Azure AD

Если в проекте немного людей, один уровень групп доступа на основе Azure AD, добавленных в группы SharePoint сайта, подойдет для большинства сценариев. Тем не менее, если у вас большое количество людей, и эти пользователи уже являются участниками группы Azure AD, вы можете легко назначить разрешения SharePoint с помощью вложенных групп или групп, которые содержат другие группы в качестве участников.
  
Например, вы хотите создать изолированный сайт группы SharePoint Online для совместной работы руководителей отделов продаж, маркетинга, поддержки, а также инженерно-технического и юридического отделов, и у этих отделов уже есть группы руководителей. Вместо того чтобы создавать группу для новых участников сайта и добавлять в нее все учетные записи руководителей, добавьте существующие группы руководителей каждого отдела в новую группу.
  
 Если вы совместно используете подписку на Microsoft 365 между несколькими организациями, можно управлять одним уровнем членства в группе для изолированного сайта для Организации в связи с тем, что количество учетных записей пользователей является довольно сложным. В этом случае можно использовать вложенные группы Azure AD для каждой организации, которые содержат группы в своей организации для управления разрешениями.
  
Чтобы использовать вложенные группы Azure AD:
  
1. Определите или создайте группы Azure AD, которые будут содержать учетные записи пользователей, и добавьте соответствующие учетные записи пользователей в качестве членов.
    
2. Создайте общую группу доступа на основе Azure AD, которая будет содержать другие группы Azure AD, и добавьте эти группы в качестве членов.
    
3.   Чтобы предоставить общей группе доступа нужный уровень доступа, укажите группу SharePoint и соответствующий уровень разрешений.
    
> [!NOTE]
> Нельзя использовать вложенные группы Microsoft 365. 
  
Ниже приведен пример вложенных групп Azure AD для группы доступа к членам ProjectX.
  
![Пример использования вложенных групп доступа для группы доступа "участники" на сайте ProjectX.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Так как все учетные записи пользователей в группах "исследование", "Проектирование" и "руководители проектов" предназначены для участников сайта, проще добавить свои группы Azure AD в группу доступа к участникам ProjectX.
  
## <a name="next-step"></a>Следующий этап

Сведения о создании и настройке изолированного сайта в рабочей среде см. в статье [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>См. также

[Изолированные сайты групп SharePoint Online](isolated-sharepoint-online-team-sites.md)
  
[Управление изолированным сайтом группы SharePoint Online](manage-an-isolated-sharepoint-online-team-site.md)

[Развертывание изолированного сайта группы SharePoint Online](deploy-an-isolated-sharepoint-online-team-site.md)



