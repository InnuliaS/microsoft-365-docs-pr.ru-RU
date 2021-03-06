---
title: Этап 3. Условия, при выполнении которых можно считать инфраструктуру Windows 10 Корпоративная настроенной
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Убедитесь, что используемая вами конфигурация соответствует критериям Microsoft 365 корпоративный для Windows 10 Корпоративная.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636691"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Этап 3. Условия, при выполнении которых можно считать инфраструктуру Windows 10 Корпоративная настроенной

![Этап 3. Windows 10 Корпоративная](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Убедитесь, что инфраструктура Windows 10 Корпоративная соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Обязательно: домены Microsoft 365 добавлены и проверены

Клиент Azure AD для подписок на Office 365 и Intune настраивается с доменными именами Интернета (например, contoso.com), а не только доменным именем, включающим строку "onmicrosoft.com". 

В противном случае выбор способов проверки подлинности, которые вы можете настроить, будет ограничен. Например, для сквозной и федеративной аутентификации невозможно использовать доменное имя onmicrosoft.com.

Чтобы выполнить это требование, см. [этап 1](windows10-prepare-your-org.md).

## <a name="optional-your-users-are-added-and-licensed"></a>Необязательно: пользователи добавлены и лицензированы

Учетные записи, соответствующие вашим пользователям, добавлены либо непосредственно в клиент Azure AD для ваших подписок на Office 365 и Intune, либо путем синхронизации службы каталогов из локальных доменных служб Active Directory (AD DS).

Добавив пользователей, вы можете назначить им лицензии на Microsoft 365 корпоративный либо непосредственно как администратор пользователей или глобальный администратор, либо автоматически через членство в группах.

В этом вам поможет описание [этапа 1](windows10-prepare-your-org.md).

## <a name="optional-diagnostics-are-enabled"></a>Необязательно: диагностика включена

Вы включили параметры диагностики данных с помощью групповой политики, Microsoft Intune, редактора реестра или в командной строке.

В этом вам поможет описание [этапа 1](windows10-prepare-your-org.md).

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Обязательно для обновления на месте: создана последовательность задач диспетчера конфигураций для развертывания операционной системы

Чтобы запустить последовательность задач диспетчера конфигураций для обновления на месте на устройстве с Windows 7 или Windows 8.1, необходимо:

- задать подходящий уровень диагностических данных Windows;
- проверить готовность к обновлению Windows;
- создать последовательность задач диспетчера конфигураций, которая включает коллекцию устройств и развертывание операционной системы с использованием образа ОС Windows 10.

Когда это будет сделано, вы можете выполнить обновление на месте для тех устройств, которые готовы к обновлению Windows. Чтобы получить максимум пользы от Microsoft 365 корпоративный, обновите как можно больше устройств с Windows 7 и Windows 8.1. 

Каждое устройство с Windows 10 Корпоративная может использовать преимущества интегрированного решения Microsoft 365 корпоративный. Остальные устройства с Windows 7 или Windows 8.1 не могут использовать облачные технологии и расширенные функции безопасности, доступные в Windows 10 Корпоративная.

Чтобы выполнить это требование, см. [этап 2](windows10-deploy-inplaceupgrade.md).

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Обязательно для новых устройств: настроено решение Windows Autopilot

Чтобы использовать Windows Autopilot для развертывания и настройки Windows 10 Корпоративная на новом устройстве, необходимо:

- настроить подходящий уровень диагностических данных Windows;
- настроить необходимые условия для Windows Autopilot, в том числе:
   - регистрацию устройств и настройку запуска при первом включении компьютера;
   - фирменную символику для запуска при первом включении компьютера;
   - автоматическую регистрацию MDM в Microsoft Intune;
   - сетевое подключение к облачным службам, которые использует Windows Autopilot;
- использовать устройства с предварительной установкой Windows 10 версии 1703 или более поздней;
- выбрать программу Windows Autopilot Deployment для своей организации.

Когда конфигурация Windows Autopilot будет готова, с ее помощью вы можете настроить в Windows 10 Корпоративная запуск при первом включении (OOBE) для:

- новых устройств;
- устройств, которые уже прошли настройку первого включения в вашей организации. 

Windows Autopilot настраивает устройство и подключает его к Azure AD.

Без Windows Autopilot потребуется настраивать новые устройства (в том числе выполнять подключение к Azure AD) вручную.

Чтобы выполнить это требование, см. [этап 3](windows10-deploy-autopilot.md).

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Необязательно: служба работоспособности устройств Windows Analytics используется для наблюдения за устройствами с Windows 10 Корпоративная

Вы использовали данные мониторинга в службе работоспособности устройств, чтобы обнаруживать и устранять проблемы, влияющие на работу пользователей. Быстрое реагирование может снизить затраты на поддержку и показать пользователям ваше серьезное отношение к ОС Windows 10 Корпоративная, что поспособствует ее принятию в организации. 

Чтобы выполнить это требование, см. [этап 4](windows10-enable-windows-analytics.md).

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Обязательно: вы используете антивирусную программу "Защитник Windows" или собственное антивредоносное решение

Вы развернули антивирусная программа "Защитник Windows" или собственное антивирусное решение для защиты устройств с Windows 10 Корпоративная от вредоносных программ. Если развернута антивирусная программа "Защитник Windows", то должен быть реализован способ создания отчетов, например Microsoft Endpoint Configuration Manager или Microsoft Intune, для отслеживания событий и действий антивируса.

Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-av).

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Обязательно: используется Exploit Guard в Защитнике Windows

Вы развернули Exploit Guard в Защитнике Windows для защиты устройств с Windows 10 Корпоративная от вторжений и реализовали способ создания отчетов, например Configuration Manager или Microsoft Intune, для отслеживания событий и действий, связанных с вторжениями.

Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-eg).

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>Обязательно: вы используете расширенную защиту от угроз в Microsoft Defender (только в Microsoft 365 E5)

Вы развернули расширенную защиту от угроз (ATP) в Microsoft Defender, чтобы обнаруживать и расследовать особо опасные угрозы для сети и устройств с Windows 10 Корпоративная, а также реагировать на них. 

При необходимости вы интегрировали службу ATP в Microsoft Defender с другими средствами, чтобы расширить ее возможности.

Чтобы выполнить это требование, см. [этап 5](windows10-enable-security-features.md#windows10-sec-atp).

## <a name="results-and-next-steps"></a>Результаты и дальнейшие действия

Ваша инфраструктура Windows 10 Корпоративная готова к началу установки на новых устройствах и обновлениям на устройствах под управлением предыдущих версий Windows, и вы используете ключевые функции безопасности Windows 10 Корпоративная.

|||
|:-------|:-----|
|![Этап 4. Приложения Microsoft 365 для предприятий](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, следующий этап —[Приложения Microsoft 365 для предприятий](office365proplus-infrastructure.md). |
