---
title: Защита доступа пользователей и устройств
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Узнайте, как защитить доступ пользователей и устройств к данным и службам Microsoft 365 и защитить от потери данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90fd902f0ccd8589fa413a2b06b9d5ccf74ab1fd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036032"
---
# <a name="protect-user-and-device-access"></a>Защита доступа пользователей и устройств

Защита доступа к данным и службам Microsoft 365 важна для защиты от кибератаки и защиты от потери данных. Одни и те же защиты можно применять к другим приложениям SaaS в среде и даже к локальным приложениям, публикуемым с помощью прокси-сервера приложения Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Шаг 1: проверка рекомендаций

Рекомендуемые возможности для защиты удостоверений и устройств, имеющих доступ к Office 365 и отличных от SaaS-служб и локальных приложений, которые опубликованы с помощью прокси приложения Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Другие языки](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Шаг 2: защита учетных записей администраторов и доступа
Административные учетные записи, которые используются для администрирования вашей среды Microsoft 365, включают повышенные привилегии. Это ценные цели для хакеров и цибераттаккерс. 

Начните с использования учетных записей администраторов только для администрирования. Администраторы должны иметь отдельную учетную запись пользователя для обычного, не административного использования и использовать учетную запись администратора только при необходимости выполнения задачи, связанной с должностной функцией.

Защитите учетные записи администратора с помощью многофакторной проверки подлинности и условного доступа. Дополнительные сведения можно найти в статье [Защита учетных записей администраторов](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts). 

Затем настройте управление привилегированным доступом в Office 365. Управление привилегированным доступом позволяет осуществлять детализированный контроль над задачами привилегированного администрирования в Office 365. Это помогает защитить организацию от нарушений, которые могут использовать существующие привилегированные учетные записи администраторов с ограниченным доступом к конфиденциальным данным или к критическим параметрам конфигурации.

- [Общие сведения об управлении привилегированным доступом](privileged-access-management-overview.md)
- [Настройка управления привилегированным доступом](privileged-access-management-configuration.md)

Еще одной рекомендацией является использование рабочих станций, специально настроенных для административной работы. Это выделенные устройства, которые используются только для задач администрирования. Обратитесь [к разделу защита привилегированного доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).

Наконец, вы можете уменьшить влияние непреднамеренного отсутствия административного доступа, создав две или более учетных записей для аварийного доступа в клиенте. Обратитесь к разделу [Управление учетными записями аварийного доступа в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Шаг 3: Настройка рекомендуемых политик доступа к удостоверениям и устройствам
Многофакторная проверка подлинности (MFA) и политики условного доступа являются мощными средствами для устранения скомпрометированных учетных записей и несанкционированного доступа. Мы рекомендуем реализовать набор политик, которые были проверены вместе. Дополнительные сведения, в том числе этапы развертывания, приведены в разделе [Конфигурация доступа к удостоверениям и устройствам](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).

 Эти политики реализуют следующие возможности:
- Мулт Factoring Authentication (проверка подлинности)
- Условный доступ
- Защита приложений в Intune (защита приложений и данных для устройств)
- Соответствие устройств Intune требованиям
- Защита идентификации Azure AD

Для реализации соответствия требованиям к устройствам Intune необходимо зарегистрировать устройство. Управление устройствами позволяет убедиться, что они являются работоспособными и совместимыми, прежде чем разрешить им доступ к ресурсам в вашей среде. [В разделе Регистрация устройств для управления в Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Шаг 4: Настройка политик доступа к устройствам SharePoint

Корпорация Майкрософт рекомендует защищать контент на сайтах SharePoint с помощью конфиденциального и строго регулируемого контента с помощью управления доступом к устройствам. Для получения дополнительных сведений см. [рекомендации по политике по обеспечению безопасности сайтов и файлов SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).



    

