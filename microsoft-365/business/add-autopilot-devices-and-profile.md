---
title: Добавление устройств и профиля AutoPilot с помощью пошагового мастера
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Узнайте, как использовать автопилот Windows для настройки новых устройств с Windows 10 для бизнеса, чтобы они были готовы к использованию сотрудниками.
ms.openlocfilehash: efcb5442b34d2d42275cedc30e71ac98c7ea1266
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401101"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Добавление устройств и профиля AutoPilot с помощью пошагового мастера

Вы можете использовать автопилот Windows для настройки **новых** устройств с Windows 10 для бизнеса, чтобы они были готовы к использованию при предоставлении их сотрудникам.
  
## <a name="device-requirements"></a>Требования к устройству

Устройства должны отвечать следующим требованиям:
  
- Windows 10 версии 1703 или более поздней версии
    
- Новые устройства, которые не прошли предварительный интерфейс Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Создание устройств и профилей с помощью мастера настройки

[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Если вы еще не создали группы устройств или профили, лучший способ начать работу с помощью пошагового руководства. Вы также можете [добавлять устройства](create-and-edit-autopilot-devices.md) и [назначать им профили](create-and-edit-autopilot-profiles.md) , не используя руководство. 
  
1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. В левой области навигации выберите **устройства** \> **автопилот**.

    ![В центре администрирования выберите устройства, а затем — автопилот.](../media/AutoPilot.png)
  
2. На странице " **Автопилотный проект** " щелкните или нажмите **начать руководство**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. На странице **upload. csv file in List of Devices (отправить. csv** ) перейдите к расположению, в котором у вас есть подготовленный. CSV-файл, а затем **откройте** \> **следующий**. Файл должен иметь три заголовка:
    
    - Столбец A: Device Serial Number (Серийный номер устройства)
    
    - Столбец B: Windows Product ID (Идентификатор продукта Windows)
    
    - Столбец C: Hardware Hash (Хэш оборудования)
    
    Эту информацию можно получить у поставщика оборудования или с помощью [сценария PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) , чтобы создать CSV-файл. 
    
    Дополнительные сведения см. в статье [CSV-файл со списком устройств](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Вы также можете скачать образец файла на странице **Отправка CSV-файла со списком устройств**. 
    
4. На странице **Назначение профиля** можно выбрать существующий профиль или создать новый. Если у вас еще нет, вам будет предложено создать его. 
    
    Профиль  это совокупность настроек, которые можно применить к одному устройству или группе устройств.
    
    Функции по умолчанию являются обязательными и устанавливаются автоматически. К ним относятся следующие параметры:
    
    - Пропускать регистрацию Кортаны, OneDrive и ИВТ.
    
    - Создание интерфейса входа с использованием фирменной символики компании.
    
    - Подключите устройства к учетным записям Azure Active Directory и автоматически зарегистрируйте их для управления с помощью Microsoft 365 Business Premium.
    
    Для получения дополнительных сведений см раздел [сведения о параметрах профиля для автопилота](autopilot-profile-settings.md). 
    
5. Также доступны параметры **Пропустить параметры конфиденциальности** и **Не разрешать пользователю становиться локальным администратором**. По умолчанию они **отключены**. 
    
    Нажмите кнопку **Далее**.
    
6. **Это означает,** что профиль, созданный вами (или выбранным), будет применен к группе устройств, созданной при отправке списка устройств. Параметры будут применяться при следующем входе пользователей устройства. Нажмите кнопку **Закрыть**.
    
