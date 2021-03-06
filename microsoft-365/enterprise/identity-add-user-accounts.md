---
title: Шаг 4. Добавление учетных записей пользователей
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Добавляйте учетные записи пользователей и группы непосредственно в облаке или с помощью синхронизации с локальным каталогом.
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005838"
---
# <a name="step-4-add-your-user-accounts"></a>Шаг 4. Добавление учетных записей пользователей

![Этап 2. Удостоверения](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>Создание учетных записей пользователей, если используется только облачная идентификация

Если используется только облачная идентификация, создавайте пользователей и группы в Azure Active Directory (Azure AD). Вы можете использовать:

- Центр администрирования Microsoft 365
- Портал Azure
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>Синхронизация удостоверений для гибридного удостоверения

*Это обязательный этап для гибридных развертываний; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

В этом разделе синхронизируются локальные доменные службы Active Directory (AD DS) с клиентом Azure AD, используемым в Office 365, Microsoft Intune и других облачных службах, входящих в состав Microsoft 365 корпоративный.

Azure AD Connect — это поддерживаемое корпорацией Майкрософт средство, с помощью которого вы сможете синхронизировать только те удостоверения, которые вам действительно нужны, из сред AD DS с одним или несколькими лесами в свой клиент Azure AD. На рисунке ниже показан базовый процесс для синхронизации Azure AD Connect.

![Сведения о том, как Azure AD Connect синхронизирует локальный каталог с Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. Средство Azure AD Connect, запущенное на сервере, опрашивает службы AD DS на наличие изменений в учетных записях, группах и контактах.
2. Azure AD Connect отправляет эти изменения в клиент Azure AD вашей подписки на Microsoft 365.

The first decision in your hybrid identity solution is your authentication requirement. The following options are options:

- With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication: 
    - **Синхронизация хэша паролей (PHS)**. [Рекомендованный и обязательный метод для некоторых премиум-функций.] Это самый простой способ включения проверки подлинности для объектов локального каталога в Azure AD. Azure AD Connect извлекает хэшированный пароль из AD DS, выполняет дополнительную обработку пароля для хэширования пароля и синхронизирует его с Azure AD. Дополнительные сведения см. в статье о [реализации синхронизации хэша паролей с помощью службы синхронизации Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
    - **Сквозная проверка подлинности** — это простое решение для проверки подлинности паролей для служб на основе Azure AD. При сквозной проверке подлинности используется агент, работающий на одном или нескольких локальных серверах и проверяющий операции проверки подлинности пользователей непосредственно с помощью локальных служб AD DS. Дополнительные сведения см. в статье [Вход пользователей с помощью сквозной проверки подлинности Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).

Просмотрите это видео с обзором моделей удостоверений и проверки подлинности для Microsoft 365 корпоративный.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

После того как вы определили гибридное решение для работы с удостоверениями, скачайте и запустите [средство устранения ошибок синхронизации каталогов IdFix](https://www.microsoft.com/download/details.aspx?id=36832), чтобы проанализировать AD DS на наличие проблем.

После устранения всех проблем, найденных средством IdFix, прочитайте статью [Реализация синхронизации хэшей паролей](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) с рекомендациями по установке средства Azure AD Connect и настройке синхронизации каталогов между локальными службами AD DS и клиентом Azure AD для вашей подписки на Microsoft 365. После начала синхронизации вы будете обслуживать свои учетные записи пользователей и группы с помощью своего локального поставщика удостоверений, например AD DS.

Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников. 

- Данные о рекомендуемых требованиях для гибридных сред см. в колонке **Active Directory с синхронизацией хэша пароля** [предварительных требований](identity-access-prerequisites.md#prerequisites). 

- Данные о рекомендуемых требованиях для исключительно облачных сред см. в колонке **Только в облаке** [предварительных требований](identity-access-prerequisites.md#prerequisites).

После появления локальных пользователей и групп в Azure AD вы можете приступить к назначению лицензий и использованию рабочих нагрузок, например OneDrive для бизнеса и Exchange Online.

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: синхронизация хэшей паролей](password-hash-sync-m365-ent-test-environment.md)<br> [Руководство по лаборатории тестирования: сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-sync), при выполнении которых можно считать данный раздел завершенным.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Отслеживание работоспособности функции синхронизации

*Это необязательная процедура, применимая к версиям Microsoft 365 E3 и E5*

В этом разделе вы установите агент Azure AD Connect Health на все свои локальные контроллеры доменов AD DS, чтобы отслеживать инфраструктуру идентификации и службы синхронизации, предоставляемые Azure AD Connect. Сведения, полученные в результате отслеживания, доступны на портале Azure AD Connect Health. Там вы можете просматривать оповещения, результаты отслеживания производительности, аналитические данные об использовании и прочие сведения.

![Компоненты Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

Ключевое решение о способе использования Azure AD Connect Health зависит от способа, которым вы используете Azure AD Connect.

- Если вы используете **управляемую проверку подлинности**, начните работу с прочтения статьи [Мониторинг синхронизации Azure AD Connect с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), чтобы понять и настроить Azure AD Connect Health.
- Если вы синхронизируете только имена учетных записей и групп, используя **федеративную проверку подлинности** с помощью служб федерации Active Directory (AD FS), для начала прочитайте статью [Мониторинг AD FS с помощью Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), чтобы понять и настроить Azure AD Connect Health.

Когда вы завершите этот раздел, у вас будут указанные ниже элементы.

- На каждом из ваших локальных серверов поставщиков удостоверений установлен агент Azure AD Connect Health.
- На портале Azure AD Connect Health отображается текущее состояние вашей локальной инфраструктуры и действий по синхронизации с клиентом Azure AD для вашей подписки на Microsoft 365.

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-sync-health).



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Упрощение процедуры обновления паролей

*Этот этап не является обязательным для гибридных развертываний. Он применяется к версиям E3 и E5 набора Microsoft 365 корпоративный.*

В этом разделе описывается, как разрешить пользователям сбрасывать свои пароли в Azure Active Directory (Azure AD), которые затем реплицируются в локальные доменные службы Active Directory (AD DS). Этот процесс называется обратной записью паролей. Благодаря обратной записи паролей пользователям не нужно обновлять свои пароли в локальных доменных службах AD DS, где хранятся учетные записи и их атрибуты. Это важно для роуминга и удаленных пользователей, у которых нет подключения к локальной сети для удаленного доступа.

Функция обратной записи пароля необходима, чтобы полностью использовать возможности функции защиты идентификации Azure AD, например чтобы требовать от пользователей изменять свои локальные пароли при высоком риске компрометации учетной записи.

Дополнительные сведения и инструкции по настройке см. в статье [Практическое руководство. Настройка компонента обратной записи паролей](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Выполните обновление до последней версии Azure AD Connect, чтобы использовать лучшие новые функции по мере их выпуска. Дополнительные сведения см. в статье [Выборочная установка Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство для лаборатории тестирования: обратная запись пароля](password-writeback-m365-ent-test-environment.md) |
|||

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-pw-writeback).

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)| [Управление с помощью групп](identity-use-group-management.md) |
