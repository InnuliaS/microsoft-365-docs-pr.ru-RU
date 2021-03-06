---
title: Управление доступом к почтовому приложению в центре администрирования Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: Сведения о том, как выбирать мобильные приложения, которые пользователи могут использовать для доступа к электронной почте, календарю и контактам.
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400056"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Управление доступом к почтовому приложению в центре администрирования Microsoft 365

Используйте параметры доступа к мобильному письму, чтобы выбрать мобильные приложения, которые сотрудники Организации могут использовать для доступа к своей рабочей или учебной учетной записи для доступа к электронной почте, календарю и контактам.
  
> [!IMPORTANT]
> У вашей организации будет доступ к этому параметру, если вы не используете Microsoft Intune или не настроили параметры управления мобильными устройствами в центре администрирования Exchange. 
  
## <a name="manage-email-app-options"></a>Управление параметрами приложения электронной почты

> [!IMPORTANT]
>  Если вы не используете эту функцию, взаимодействие с пользователями не изменится. Они смогут использовать любое мобильное приложение электронной почты для доступа к своей рабочей или учебной учетной записи для электронной почты, календаря и контактов с мобильного устройства. 
    
1. В центре администрирования перейдите в раздел **Параметры ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Услуги&amp;</a> надстроек. 

2. На странице **параметры доступа к мобильным электронным письмам** установите флажок, а затем выберите способ использования почтовых приложений для пользователей в вашей организации:
  
Выберите параметр, чтобы задать способ доступа к рабочей или учебной учетной записи пользователей в Организации с мобильных устройств
  
- **Только Outlook** пользователи вашей организации должны будут использовать приложение Outlook для Android или Outlook для iOS на мобильном устройстве. 
    
- **Любое почтовое приложение** — все пользователи в вашей организации будут получать запросы на использование Outlook, но могут использовать любое почтовое приложение. 
    
- **Любое почтовые приложения** — новые пользователи и устройства в организации будут предлагаться один раз для использования Outlook, но они могут использовать любое почтовое приложение. 
    
Дополнительные сведения можно узнать в статьях, [получающих доступ к электронной почте с мобильного устройства](access-email-from-a-mobile-device.md).
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>В организации активирован новый пользователь или устройство

Как только пользователь организации добавляет свои рабочие и учебные электронные сообщения в стороннее приложение электронной почты или на новое устройство, они получают электронную почту от **корпорации Майкрософт от имени вашей организации**. Сообщения электронной почты помогут вам узнать о преимуществах использования мобильного приложения Outlook и указать ссылку на расположение для скачивания. После этого пользователи смогут выбрать, следует ли продолжать использовать приложение стороннего производителя или использовать мобильное приложение Outlook. В течение 24 часов после первого получения этого электронного сообщения устройство будет находиться в карантине, а адрес электронной почты, календарь и контактные данные не будут обновлены. Если вы решили использовать мобильное приложение Outlook, приложение стороннего производителя останется на карантине, и данные будут синхронизированы только с мобильным приложением Outlook. Если они решили продолжить работу с приложением стороннего производителя, синхронизация данных начнется мгновенно. Если в течение первых 24 часов не будет выполнено никаких действий, сообщение электронной почты будет удалено из папки "Входящие", а данные будут автоматически запускаться с сервера.
  
## <a name="previously-configured-users-in-your-organization"></a>Ранее настроенные пользователи в Организации

Если вы решили использовать Outlook для всех пользователей в Организации, а также описанный выше опыт для новых пользователей, пользователи, которые ранее подключили свою рабочую или учебную учетную запись электронной почты к стороннему приложению, получат электронное письмо от **корпорации Майкрософт от имени вашей организации** в течение 48 часов. Сообщения электронной почты помогут вам узнать о преимуществах использования мобильного приложения Outlook и указать ссылку на расположение для скачивания. После этого пользователи смогут выбрать, следует ли продолжать использовать приложение стороннего производителя или использовать мобильное приложение Outlook. В течение 24 часов после первого получения этого электронного сообщения устройство будет находиться в карантине, а адрес электронной почты, календарь и контактные данные не будут обновлены. Если вы решили использовать мобильное приложение Outlook, приложение стороннего производителя останется на карантине, и данные будут синхронизированы только с мобильным приложением Outlook. Если они решили продолжить работу с приложением стороннего производителя, синхронизация данных начнется мгновенно. Если в течение первых 24 часов не будет выполнено никаких действий, сообщение электронной почты будет удалено из папки "Входящие", а данные будут автоматически запускаться с сервера. 
  

