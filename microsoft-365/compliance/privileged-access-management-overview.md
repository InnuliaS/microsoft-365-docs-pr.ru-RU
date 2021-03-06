---
title: Управление привилегированным доступом
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: В этой статье представлен обзор управления привилегированным доступом в Microsoft 365, в том числе ответы на часто задаваемые вопросы (FAQ).
ms.openlocfilehash: eb5fe5320c061d40f0882f93b66afa3cad4fa0fa
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036042"
---
# <a name="privileged-access-management"></a>Управление привилегированным доступом

Управление привилегированным доступом позволяет осуществлять детализированный контроль над задачами привилегированного администрирования в Office 365. Это поможет защитить организацию от нарушений, которые используют существующие привилегированные учетные записи администратора с ограниченным доступом к конфиденциальным данным или к критически важным параметрам конфигурации. Управление привилегированным доступом требует от пользователей запрашивать доступ по требованию к выполнению привилегированных и привилегированных задач с помощью рабочего процесса утверждения с высоким уровнем с областью действия и с ограниченным временем действия. Эта конфигурация дает пользователям достаточно прав для выполнения задачи, не выполняя риск потери конфиденциальных данных или критически важных параметров конфигурации. Включение управления привилегированным доступом в Microsoft 365 позволяет организации работать с нулевыми привилегиями и обеспечивать уровень защиты от появления уязвимостей административного доступа.

Чтобы получить краткий обзор интегрированного защищенного хранилища и рабочего процесса управления доступом для клиентов, просмотрите [видео о защищенном доступе и привилегированном доступе](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Уровни защиты

Управление привилегированным доступом дополняет другие функции защиты данных и доступа в архитектуре безопасности Microsoft 365. Включение привилегированного управления доступом в рамках интегрированного и многоуровневого подхода к безопасности обеспечивает модель безопасности, которая максимизирует защиту конфиденциальной информации и параметров конфигурации Microsoft 365. Как показано на схеме, управление привилегированным доступом выполняется на основе защиты, предоставляемой с помощью встроенного шифрования данных Microsoft 365 и модели безопасности управления доступом на основе ролей для служб Microsoft 365. При использовании с [правами привилегированного управления удостоверениями Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)эти две функции обеспечивают управление доступом с помощью доступа по требованию в различных областях.

![Многоуровневая защита в Microsoft 365](../media/pam-layered-protection.png)

Управление привилегированным доступом определяется и задается на уровне **задачи** , а управление удостоверениями Azure AD обеспечивает защиту на уровне **ролей** с возможностью выполнения нескольких задач. Служба управления удостоверениями Azure AD в основном позволяет управлять ролями AD и группами ролей, в то время как управление привилегированным доступом в Microsoft 365 применяется только на уровне задачи.

- **Включение управления привилегированным доступом в то время, когда уже используется Azure AD с правами на управление удостоверениями:** Добавление привилегированного управления доступом обеспечивает еще один детализированный уровень защиты и возможности аудита для привилегированного доступа к данным Microsoft 365.

- **Включение привилегированного управления удостоверениями Azure AD при использовании привилегированного управления доступом в Office 365:**  Добавление привилегированного управления удостоверениями Azure AD в Управление привилегированным доступом позволяет расширить доступ к данным вне Microsoft 365, которые в основном определяются ролями пользователей или удостоверениями.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Архитектура управления привилегированным доступом и последовательность процессов

Каждый из следующих процессов обрабатывает архитектуру привилегированного доступа и взаимодействие с подложкой Microsoft 365, аудитом и пространством выполнения управления Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Шаг 1: Настройка политики привилегированного доступа

При настройке политики привилегированного доступа с помощью [центра администрирования Microsoft 365](https://admin.microsoft.com) или Exchange Management PowerShell вы определяете политику и процессы привилегированного доступа и атрибуты политики на подложке Microsoft 365. Действия регистрируются в центре безопасности &amp; и соответствия требованиям. Теперь политика включена и готова к обработке входящих запросов на утверждения.

![Шаг 1: Создание политики](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Шаг 2: запрос на доступ

В [центре администрирования Microsoft 365](https://admin.microsoft.com) или Exchange Management PowerShell пользователи могут запрашивать доступ к повышенным или привилегированным задачам. Функция привилегированного доступа отправляет запрос на подложку Microsoft 365 для обработки в настроенной политике доступа к данным и записывает действия в журналы &amp; центра соответствия требованиям безопасности.

![Шаг 2: запрос на доступ](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Шаг 3: утверждение доступа

Будет создан запрос на утверждение, а уведомление о незавершенном запросе будет отправлено утверждающим. В случае утверждения привилегированный запрос на доступ обрабатывается как утверждение и готов к выполнению задачи. Если этот параметр отклонен, задача блокируется, а запрашивающему не предоставляется доступ. Запрашивающий уведомляет об утверждении или отказе от запроса через сообщение электронной почты.

![Шаг 3: утверждение доступа](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Шаг 4: обработка доступа

Для утвержденного запроса задача обрабатывается пространством выполнения управления Exchange. Утверждение проверяется на соответствие политике привилегированного доступа и обрабатывается с помощью подложки Microsoft 365. Все действия для задачи записываются в центре безопасности &amp; и соответствия требованиям.

![Шаг 4: обработка доступа](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Какие номера SKU могут использовать привилегированный доступ в Office 365?

Управление привилегированным доступом доступно для пользователей с широким набором подписок и надстроек Microsoft 365 и Office 365. Дополнительные сведения можно найти в статье Начало [работы с правами на управление правами на доступ к данным](privileged-access-management-configuration.md) .

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Когда будет поддерживаться привилегированный доступ к рабочим нагрузкам Office 365 за пределами Exchange?

Управление привилегированным доступом скоро будет доступно в других рабочих нагрузках Office 365. Для получения дополнительных сведений посетите [план Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) .

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Для организации требуется более 30 политик привилегированного доступа? это максимальное значение будет увеличено.

Да, если вы придаете текущему ограничению 30 привилегированных политик доступа для каждой организации, в ней находится схема компонентов.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Нужен ли глобальный администратор для управления привилегированным доступом в Office 365?

Нет, роль управления ролями Exchange должна быть назначена учетным записям, которые управляют привилегированным доступом в Office 365. Если вы не хотите настраивать роль управления ролями в качестве автономного разрешения, роль глобального администратора включает эту роль по умолчанию и может управлять привилегированным доступом. Пользователи, включенные в группу утверждающих, не обязательно должны быть глобальными администраторами или иметь роль управления ролями, назначенную для просмотра и утверждения запросов с помощью PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Как управление привилегированным доступом связано с защищенным хранилищем пользователей?

[Служба защищенного хранилища](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) обеспечивает уровень управления доступом для организаций, когда Microsoft обращается к данным. Управление привилегированным доступом позволяет управлять детальным доступом в Организации для всех привилегированных задач Microsoft 365.

## <a name="ready-to-get-started"></a>Готовы приступить к работе?

Начните [настраивать организацию для управления привилегированным доступом](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Подробнее

[Интерактивное руководство: мониторинг и управление задачами администрирования с помощью привилегированного управления доступом](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
