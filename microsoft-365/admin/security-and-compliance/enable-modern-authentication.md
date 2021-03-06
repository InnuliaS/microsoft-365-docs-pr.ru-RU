---
title: Включение современной проверки подлинности для Office 2013 на устройствах с Windows
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Сведения о настройке разделов реестра для включения современной проверки подлинности для устройств, на которых установлен Microsoft Office 2013.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779969"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Включение современной проверки подлинности для Office 2013 на устройствах с Windows

Чтобы включить современную проверку подлинности для устройств Windows, на которых установлен Office 2013, необходимо настроить разделы реестра.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Включение современной проверки подлинности для клиентов Office 2013

> [!NOTE]
> Современная проверка подлинности уже включена для клиентов Office 2016. Настраивать разделы реестра для Office 2016 не нужно. 
  
To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:
  
|**Раздел реестра**|**Тип**|**Значение** |
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0\common\identity\enableadal нулевое  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |
   
После настройки разделов реестра можно настроить приложения Office 2013 для использования [многофакторной проверки подлинности (MFA)](set-up-multi-factor-authentication.md) с Microsoft 365. 
  
If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.
  
## <a name="disable-modern-authentication-on-devices"></a>Отключение современный проверки подлинности на устройствах

Чтобы отключить современную проверку подлинности на устройстве, настройте на нем следующие разделы реестра:
  
|**Раздел реестра**|**Тип**|**Значение**|
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0\common\identity\enableadal нулевое |REG_DWORD|нуль|
   
## <a name="related-articles"></a>Связанные статьи
[Вход в Office 2013 со вторым способом проверки подлинности](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

