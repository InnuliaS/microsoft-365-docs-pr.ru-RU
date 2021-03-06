---
title: Настройка переадресации электронной почты
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Настройка переадресации электронной почты на одну или несколько учетных записей электронной почты с помощью Office365.
ms.openlocfilehash: f6c177ba37cf2b8ce3966732adbe8428d9b6179e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780257"
---
# <a name="configure-email-forwarding"></a>Настройка переадресации электронной почты

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Администратор организации может иметь требования к настройке переадресации электронной почты для почтового ящика пользователя. Переадресация позволяет пересылать сообщения, отправленные в почтовый ящик пользователя, в другой почтовый ящик в организации или за ее пределами.

  
## <a name="configure-email-forwarding"></a>Настройка переадресации электронной почты

 Перед настройкой переадресации электронной почты Обратите внимание на следующее: 

- После настройки переадресации электронной почты будут фовардед только **новые** сообщения, отправленные в почтовый ящик *из* почтового ящика. 
    
- Для переадресации электронной почты необходимо, чтобы у учетной записи " *от* " была лицензия. Если вы настраиваете переадресацию электронной почты, так как пользователь оставил вашу организацию, другой вариант заключается в [преобразовании его почтового ящика в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md). Это позволит нескольким людям получить к ним доступ. Однако общий почтовый ящик не может превышать 50 ГБ. 
    
Для выполнения этих действий необходимо быть администратором Exchange или глобальным администратором в Microsoft 365. Для получения дополнительных сведений ознакомьтесь с разделом ["роли администратора"](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
    
2. Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств. 
 
3. На вкладке **почта** выберите **Управление переадресацией электронной почты**. 
  
4. На странице переадресация электронной почты выберите **Переслать все сообщения, отправленные в этот почтовый ящик**, введите адрес переадресации и выберите, следует ли хранить копию пересылаемых сообщений. Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия. Нажмите кнопку **Сохранить изменения**.
    
    **Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам. Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.
    
5. Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.  В противном случае переадресация электронной почты прекратится. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>. 
    
2. Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств. 

3. Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.

4. На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений. Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия. Нажмите кнопку **Сохранить**.
    
    **Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам. Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.
    
5. Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.  В противном случае переадресация электронной почты прекратится.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>. 
    
2. Выберите имя пользователя, для которого необходимо переслать сообщение, чтобы открыть страницу свойств. 

3. Разверните узел **Параметры почты**, а затем в разделе **переадресация электронной почты** нажмите кнопку **изменить**.

4. На странице переадресация электронной почты установите переключатель в значение **вкл**., введите адрес перенаправления и выберите, нужно ли хранить копию пересылаемых сообщений. Если вы не видите этот параметр, убедитесь, что учетной записи пользователя назначена лицензия. Нажмите кнопку **Сохранить**.
    
    **Чтобы переслать на несколько адресов электронной почты**, можно попросить пользователя настроить правило в Outlook для пересылки по адресам. Чтобы узнать больше, ознакомьтесь [со статьей использование правил для автоматической пересылки сообщений](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     В центре администрирования [Создайте группу рассылки](../setup/create-distribution-lists.md), [добавьте в нее адреса](add-user-or-contact-to-distribution-list.md), а затем настройте перенаправление на адрес списка рассылки, выполнив инструкции, приведенные в этой статье.
    
5. Не удаляйте учетную запись пользователя, который пересылается или удаляет лицензию.  В противном случае переадресация электронной почты прекратится. 

::: moniker-end 
