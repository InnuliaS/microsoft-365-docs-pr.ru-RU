---
title: 'Шаг 7: Настройка управления привилегированным доступом'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Общие сведения и Настройка управления привилегированным доступом.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636992"
---
# <a name="step-7-configure-privileged-access-management"></a>Шаг 7: Настройка управления привилегированным доступом

*Этот шаг необязательный; он применяется только к планам E5 и Advanced Compliance Microsoft 365 корпоративный.*

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Управление привилегированным доступом включается посредством настройки политик, определяющим своевременный доступ для действий на основе задач в вашем клиенте. Вашей организации может понадобиться защита от нарушений с использованием существующих привилегированных учетных записей администратора с постоянным доступом к конфиденциальным данным или доступом к критическим параметрам конфигурации. Например, можно настроить политику управления привилегированным доступом таким образом, чтобы требовалось явное утверждение для доступа к параметрам почтового ящика организации и их изменения в клиенте.

На этом этапе вы включаете управление привилегированным доступом в вашем клиенте и настраиваете политики привилегированного доступа, которые обеспечивают дополнительную защиту для доступа на основе задач к данным и параметрам конфигурации для вашей организации. Существуют три основных этапа настройки управления привилегированным доступом в вашей организации:
- создание группы утверждающего;
- включение привилегированного доступа;
- создание политик утверждения.

Настройка управления привилегированным доступом позволит вашей организации работать без постоянного привилегированного доступа и обеспечить уровень защиты от уязвимостей, связанных с таким постоянным административным доступом. Привилегированный доступ требует утверждения выполнения любой задачи, для которой установлена соответствующая политика утверждения. Пользователи, которым необходимо выполнить задачи, регулируемые политикой утверждения, должны запросить и получить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения определенных в политике задач.

Чтобы включить управление привилегированным доступом, см. статью [Настройка управления привилегированным доступом](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Дополнительные сведения см. в статье [Управление привилегированным доступом](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Управление привилегированным доступом: руководство по лаборатории тестирования](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step7), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

[Условия, при выполнении которых можно считать защиту информации настроенной](infoprotect-exit-criteria.md)
