---
title: Шаг 4. Настройка Windows Information Protection
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Изучение и развертывание Windows Information Protection в Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005726"
---
# <a name="step-4-configure-windows-information-protection"></a>Шаг 4. Настройка Windows Information Protection

*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Чем больше персональных устройств используется для работы, тем выше становится риск утечки конфиденциальных данных организаций через приложения и устройства. Например, сотрудник может случайно отправить на сайт социальной сети рисунок с маркетинговым планом будущего продукта или сохранить в общедоступном облачном хранилище файл, содержащий совершенно секретную информацию. 

Windows Information Protection (WIP) обеспечивает защиту от утечки данных такого рода на устройствах с Windows 10. Дополнительные сведения см. в статье [Защита корпоративных данных с помощью WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

В Microsoft 365 корпоративный WIP представляет собой сочетание операционной системы Windows 10 Корпоративная и службы Microsoft Intune, которая входит в вашу подписку. 

Для развертывания WIP в организации с использованием Microsoft 365 корпоративный выполните следующие действия.

1. Зарегистрируйте свои устройства Windows в Intune. Это уже должно быть сделано на [Этапе 5. Управление мобильными устройствами](mobility-infrastructure.md).

2. Создайте [политику Intune для WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).

   -    Убедитесь, что список защищенных приложений заполнен.
  
   - Выберите уровень защиты WIP.

Также можно использовать WIP с [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr). 

Дополнительную информацию см. в статье [Советы и рекомендации по WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[Настройка защиты от потери данных](infoprotect-data-loss-prevention.md)|


