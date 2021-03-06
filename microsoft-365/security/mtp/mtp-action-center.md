---
title: Переход в центр уведомлений для просмотра и утверждения автоматического исследования и задач по исправлению
description: Используйте центр уведомлений для просмотра сведений об автоматическом исследовании и утверждения ожидающих действий
keywords: Центр уведомлений, защита от угроз, исследование, оповещение, ожидание, автоматически, обнаружение
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: c3406ebf5962d6f0ac08c1ee280bab725cf1c3bd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626962"
---
# <a name="the-action-center"></a>Центр уведомлений

**Область применения:**
- Защита от угроз (Майкрософт)

Используйте центр уведомлений для просмотра результатов текущего и прошлых исследований в почтовых ящиках и устройствах вашей организации. В зависимости от типа угрозы и результата вредоносности [действия по исправлению](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) происходят автоматически или при утверждении группой операций безопасности Организации. Все действия по исправлению (как ожидающие утверждения, так и утвержденные) объединяются в центре уведомлений. 

![Центр уведомлений](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Интерфейс "единой области представления"

В центре уведомлений доступен интерфейс "единой области представления" для задач, таких как:
- утверждение ожидающих действий по исправлению;
- просмотр журнала аудита утвержденных действий по исправлению; и
- проверка выполненных действий по исправлению.

Ваша группа операций по безопасности может работать эффективнее благодаря наличию в центре уведомлений комплексного представления защиты от угроз (Майкрософт) в работе.

## <a name="go-to-the-action-center"></a>Переход в центр уведомлений

1. Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите. 

2. В панели навигации щелкните **Центр уведомлений**. 

3. В центре уведомлений вы увидите две вкладки: **ожидающие** и **журналу**.

    - На вкладке **Ожидание** перечислены исследования, требующие проверки и утверждения участником группы операций по безопасности для продолжения процесса. Обязательно просмотрите ожидающие элементы, представленные здесь, и выполните соответствующие действия.

    - На вкладке **Журнал** перечислены прошлые исследования и действия по исправлению, выполненные автоматически. Вы можете просматривать данные за последний день, неделю, месяц или шесть месяцев.

4. Чтобы отобразить только нужные столбцы, выберите команду **Настроить столбцы**.<br/>![Центр уведомлений в службе защиты от угроз (Майкрософт)](../../media/mtp-action-center.png)

5. Выберите элемент в списке, чтобы просмотреть дополнительные сведения об исследовании. Откроется представление со сведениями об исследовании.<br/>![Сведения об исследовании](../../media/mtp-air-investdetails.png)

    - Если исследование относится к содержимому электронной почты (например, объект является почтовым ящиком), сведения об исследовании открываются в центре безопасности &[https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)соответствия требованиям (). 

    - Если исследование затрагивает устройство, сведения об исследовании откроются в Центре безопасности ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Если вы считаете, что что-то пошло не так или неправильно, с помощью автоматизированного расследования и функции ответа в Microsoft Threat Protection, сообщите нам о! Сведения о [том, как сообщить о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования (AIR) в защите от угроз Майкрософт](mtp-autoir-report-false-positives-negatives.md).

## <a name="required-permissions-for-action-center-tasks"></a>Обязательные разрешения для задач центра уведомлений

Чтобы утвердить или отклонить ожидающие действия в центре уведомлений, вам должны быть назначены разрешения, указанные в следующей таблице.

|Действие по исправлению |Обязательные роли и разрешения |
|--|----|
|Исправление в Microsoft Defender ATP (устройства) |Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- или ---<br/>Роль Активные действия по исправлению, назначенная в Microsoft Defender ATP <br/> <br/> Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами. <br/>- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Создание ролей и управление ими для контроля доступа на основе ролей (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Исправление в Office 365 ATP (почта и содержимое Office)  |Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- и --- <br/>Роль поиска и очистки, которой назначен центр безопасности & соответствия[https://protection.office.com](https://protection.office.com)требованиям (). <br/><br/>**Важно!** если у вас есть роль администратора безопасности, назначенная только в центре безопасности & соответствия требованиям, вы не сможете получить доступ к центру уведомлений или функциям защиты от угроз Майкрософт. У вас должна быть роль администратора безопасности, назначенная в Azure Active Directory или Центре администрирования Microsoft 365. <br/><br/>Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами. <br/>- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Разрешения в центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Пользователи, которым назначена роль Глобальный администратор в Azure Active Directory, могут утвердить или отклонить любые ожидающие действия в центре уведомлений. Однако рекомендуется ограничить в организации число пользователей, которым назначена роль глобального администратора. Рекомендуем использовать роли Администратор безопасности, Активные действия по исправлению, и Поиск и очистка, указанные выше, в качестве разрешений центра уведомлений.

## <a name="next-steps"></a>Дальнейшие действия 

- [Подробнее об инцидентах в службе защиты от угроз (Майкрософт)](incidents-overview.md)

- [Просмотр результатов автоматического исследования](mtp-autoir-results.md)

- [Сведения о выслеживании в службе защиты от угроз (Майкрософт)](advanced-hunting-overview.md)

