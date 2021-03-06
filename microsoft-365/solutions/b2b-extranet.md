---
title: Создание экстрасети B2B с управляемыми гостями
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Узнайте, как создать сайт или группу экстрасети B2B с управляемыми гостевыми пользователями из партнерской организации.
ms.openlocfilehash: f01a558d55f497952494676f0148a1e3e4f06b35
ms.sourcegitcommit: b18949de721c6eef3521d5f8286d9b926ad4aabe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342517"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Создание экстрасети B2B с управляемыми гостями

С помощью [управления обслуживанием Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) вы можете создать экстрасеть B2B для совместной работы с партнерской организацией, в которой используется Azure Active Directory. Это позволяет пользователям самостоятельно регистрироваться на сайте или группе экстрасети и получать доступ с помощью рабочего процесса утверждения.

С помощью этого метода совместного использования ресурсов для совместной работы Партнерская организация может способствовать обслуживанию и утверждению гостевых пользователей, уменьшая нагрузку на ИТ-отдел и предоставляя им все, кто знаком с соглашением о совместной работе для управления доступом пользователей.

В этой статье описано, как создать пакет ресурсов (в данном случае, на сайте или в группе), который можно предоставить партнерской организации через модель регистрации самостоятельного доступа. 

Прежде чем приступать к работе, создайте сайт или рабочую группу, к которой вы хотите предоставить доступ партнерской организации, и включите ее для общего доступа гостей. Для получения дополнительных сведений ознакомьтесь со статьей [Совместная работа с гостями на сайте](collaborate-in-site.md) или [Совместная работа с гостями в группе](collaborate-as-team.md) . Кроме того, рекомендуется ознакомиться со сведениями о том, [как создать безопасную среду общего доступа](create-secure-guest-sharing-environment.md) , чтобы получить сведения о функциях обеспечения безопасности и соответствия требованиям, которые можно использовать для поддержки политик управления при совместной работе с гостями.

## <a name="video-demonstration"></a>Видеодемонстрация

В этом видеоролике показаны процедуры, описанные в этой статье.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Подключение партнерской организации

Чтобы пригласить гостей из партнерской организации, необходимо добавить домен партнера в качестве подключенной Организации в Azure Active Directory.

Добавление подключенной Организации
1. В [Azure Active Directory](https://aad.portal.azure.com)щелкните **Управление удостоверениями**.
2. Щелкните элемент **подключенные Организации**.
4. Щелкните **Добавить подключенную организацию**.
5. Введите имя и описание организации, а затем нажмите кнопку **Далее: Каталог и домен**.
6. Нажмите кнопку **Добавить каталог + домен**.
7. Введите домен для Организации, к которой требуется подключиться, и нажмите кнопку **Добавить**.
8. Нажмите кнопку **подключить**, а затем нажмите кнопку **Далее: Спонсоры**.
9. Добавьте людей из вашей организации или организации, к которой вы подключаетесь, к которым вы хотите утвердить доступ для гостей.
10. Нажмите кнопку **Далее: Проверка + создать**.
11. Просмотрите выбранные параметры и нажмите кнопку **создать**.

    ![Снимок экрана со страницей "подключенные организации" в Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Выбор ресурсов для совместного использования

Первый шаг в выборе ресурсов для совместного использования с партнерской организацией состоит в создании каталога, в котором они должны содержаться.

Создание каталога
1. В [Azure Active Directory](https://aad.portal.azure.com)щелкните **Управление удостоверениями**.
2. Щелкните **каталоги**.
3. Нажмите кнопку **создать каталог**.
4. Введите имя и описание каталога и **Убедитесь, что** для **внешних пользователей** задано значение **Да**.
5. Нажмите кнопку **Создать**.

   ![Снимок экрана: страница каталогов в управлении удостоверениями Azure Active Directory](../media/identity-governance-catalogs.png)

После создания каталога вы добавляете сайт или группу SharePoint, к которым вы хотите предоставить доступ партнерской организации.

Добавление ресурсов в каталог
1. В разделе Управление удостоверениями Azure AD щелкните **каталоги**, а затем выберите каталог, в который требуется добавить ресурсы.
2. Щелкните **ресурсы** , а затем — **Добавить ресурсы**.
3. Выберите сайты Teams или SharePoint, которые вы хотите включить в экстрасеть, и нажмите кнопку **Добавить**.

   ![Снимок экрана: страница ресурсов каталога в управлении удостоверениями Azure Active Directory](../media/identity-governance-catalog-resource.png)

После определения ресурсов, к которым вы хотите предоставить общий доступ, следующим шагом является создание пакета Access, который определяет тип доступа, предоставленный пользователям-партнерам, и процесс утверждения для новых партнеров-пользователей, запрашивающих доступ.

Создание пакета Access
1. В разделе Управление удостоверениями Azure AD щелкните **каталоги**, а затем выберите каталог, в котором нужно создать пакет Access.
2. Щелкните **пакеты Access**, а затем — **новый пакет Access**.
3. Введите имя и описание для пакета Access, а затем нажмите кнопку **Далее: роли ресурсов**.
4. Выберите ресурсы из каталога, который вы хотите использовать для экстрасети.
5. Для каждого ресурса в столбце **роль** выберите роль пользователя, которую необходимо предоставить гостям, использующим экстрасеть.
6. Нажмите кнопку **Далее: запросы**.
7. В разделе **Пользователи, которые могут запрашивать доступ**, выберите для пользователей, не находящихся **в вашем каталоге**.
8. Убедитесь, что выбран параметр **конкретные подключенные Организации** , а затем нажмите кнопку **Добавить каталоги**.
9. Выберите добавленную ранее подключенную организацию и нажмите кнопку **выбрать**
10. В разделе **утверждение**выберите **Да** для параметра **требуется утверждение**.
11. В разделе **первый утверждающий**выберите одного из спонсоров, добавленных ранее, или выберите определенного пользователя.
12. Нажмите кнопку **добавить резервную** копию и выберите резервный утверждающий.
13. В разделе **включить**нажмите кнопку **Да**.
14. Нажмите кнопку **Далее: жизненный цикл**.
15. Выберите нужные параметры проверки истечения срока действия и проверки доступа, а затем нажмите кнопку **Далее: Проверка и создание**.
16. Проверьте параметры и нажмите кнопку **создать**.

    ![Снимок экрана с экраном пакетов доступа в управлении удостоверениями Azure Active Directory](../media/identity-governance-access-packages.png)

Если вы собираетесь с большой организацией, вам может потребоваться скрыть пакет Access. Если пакет скрыт, пользователи в партнерской организации не увидят пакет на своем портале *доступа* . Вместо этого им необходимо отправить прямую ссылку для регистрации пакета. Скрытие пакета Access может уменьшить количество неуместных запросов на доступ, а также обеспечить доступ к пакетам Access, организованным на портал партнерской организации.

Установка скрытого пакета доступа
1. В управлении удостоверениями Azure AD щелкните **пакеты Access**, а затем щелкните пакет Access.
2. На странице **Обзор** щелкните **изменить**.
3. В разделе **Свойства**выберите пункт **Да** для параметра **скрытый**и нажмите кнопку **сохранить**.

   ![Снимок экрана: экран свойств пакета редактирования](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Приглашение партнеров для пользователей

Если вы установили скрытый пакет доступа, необходимо отправить прямую ссылку на партнерскую организацию, чтобы она могла запрашивать доступ к сайту или группе.

Поиск ссылки на портал доступа
1. В управлении удостоверениями Azure AD щелкните **пакеты Access**, а затем щелкните пакет Access.
2. На странице **Обзор** щелкните ссылку **Копировать в буфер обмена, чтобы** **перейти по ссылке портал My Access**.

   ![Снимок экрана: свойства пакета Access с ссылкой на портал доступа](../media/identity-governance-access-portal-link.png)

После того как вы скопировали ссылку, вы можете поделиться ею с контактом в партнерской организации и отправить его пользователям в своей группе совместной работы.

## <a name="see-also"></a>См. также

[Создание безопасной среды гостевого общего доступа](create-secure-guest-sharing-environment.md)

