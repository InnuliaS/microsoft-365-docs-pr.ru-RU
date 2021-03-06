---
title: Создание и изменение устройств AutoPilot
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Сведения о том, как отправлять устройства с помощью автопилота в Microsoft 365 бизнес премиум. Вы можете назначить профиль устройству или группе устройств.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401001"
---
# <a name="create-and-edit-autopilot-devices"></a>Создание и изменение устройств AutoPilot

## <a name="upload-a-list-of-devices"></a>Отправка списка устройств

Вы можете использовать [Пошаговое руководство](add-autopilot-devices-and-profile.md) по отправке устройств, но вы также можете загрузить устройства на вкладке " **устройства** ". 
  
Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней версии
    
- Новые устройства, которые не прошли предварительный интерфейс Windows

1. В центре администрирования Microsoft 365 выберите **устройства** \> **автопилот**.
  
2. На странице " **Автопилотный проект** " перейдите на вкладку **устройства** , чтобы \> **Добавить устройства**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. На панели **Add Devices (Добавление устройств** ) перейдите к [CSV-файлу списка устройств](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) , подготовленный для \> **сохранения** \> **Close**.
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) , чтобы создать CSV-файл. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Назначение профиля устройству или группе устройств

1. На странице **Подготовка Windows** перейдите на вкладку **устройства** и установите флажок рядом с одним или несколькими устройствами. 
    
2. На панели **Устройство** выберите профиль в раскрывающемся списке **Назначенный профиль**. 
    
    Если у вас еще нет профилей, см. инструкции в статье [Создание и изменение профилей AutoPilot](create-and-edit-autopilot-profiles.md). 
    
