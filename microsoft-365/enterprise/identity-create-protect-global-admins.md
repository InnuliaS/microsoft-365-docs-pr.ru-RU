---
title: Шаг 1. Создание и защита учетных записей глобальных администраторов
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
description: Учетные записи глобальных администраторов нуждаются в особой обработке, чтобы защитить их от компрометации учетных данных.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621310"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Шаг 1. Создание и защита учетных записей глобальных администраторов

![Этап 2. Удостоверения](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Защита учетных записей глобальных администраторов

**Этот шаг обязателен и применяется к планам E3 и E5 Microsoft 365 корпоративный*

В данном разделе рассматривается предотвращение цифровых атак в вашей организации за счет как можно большего укрепления безопасности учетных записей администраторов. Чтобы достичь этого, примите следующие меры:

- Создавайте несколько выделенных учетных записей глобальных администраторов с [надежными паролями](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) и используйте эти учетные записи только при необходимости.
- Для выполнения повседневных задач администрирования назначайте конкретные роли администраторов, например администратора Exchange или администратора паролей, для других выделенных учетных записей для этих ролей или пользователей-сотрудников ИТ-подразделения, при необходимости.

Кроме того, для выделенных учетных записей глобальных администраторов необходимо выполнять указанные ниже действия.

1. Чтобы убедиться, что многофакторная проверка подлинности Azure для отдельных учетных записей пользователей или на основе условного доступа работает правильно и предсказуемо, проверяйте ее параметры на тестовых учетных записях пользователей.  Для работы многофакторной проверки подлинности необходимо использовать дополнительный способ проверки подлинности, например отправлять код проверки на смартфон.
2. Создайте и активируйте политику условного доступа для ваших учетных записей глобальных администраторов, которые требуют многофакторной проверки подлинности, и используйте наиболее надежную форму дополнительной проверки подлинности в вашей организации. Дополнительные сведения см. в статье [Многофакторная проверка подлинности Azure](identity-access-prerequisites.md#protecting-administrator-accounts).

Сведения по дополнительным средствам защиты см. в статье [Защита учетных записей глобальных администраторов](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> Учетные записи для экстренных ситуаций при возникновении сценариев аварийного доступа, таких как кибератаки, должны быть только облачными учетными записями. У вас могут также иметься учетные записи глобальных администраторов (разрешенные или постоянные) не только в облаке. Дополнительные сведения см. в статье [Управление учетными записями администраторов для аварийного доступа в Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Ниже перечислены результаты, которые вы получите после выполнения инструкций с данного этапа.

- Роль глобального администратора имеют только новые специальные учетные записи глобального администратора. Проверьте это с помощью указанной ниже команды Azure Active Directory PowerShell для Graph: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Всем остальным учетным записям пользователей, которые управляют вашей подпиской, назначены роли администраторов, соответствующие должностным обязанностям этих пользователей.

> [!Note]
> Инструкции по установке модуля Azure Active Directory PowerShell для Graph и входу в него см. в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Защита учетных записей глобальных администраторов: руководство по лаборатории тестирования](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-global-admin).


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Настройка администраторов по требованию

*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*

В этом разделе рассматривается настройка Azure AD Privileged Identity Management (PIM) для сокращения времени уязвимости учетных записей ваших администраторов к атакам злоумышленников. PIM обеспечивает своевременное присвоение роли администратора, когда это необходимо.  

Ваши учетные записи администраторов становятся разрешенными, а не постоянными администраторами. Роль администратора будет неактивной до тех пор, пока она не понадобится. После этого вы сможете выполнить процесс активации, чтобы добавить роль администратора в учетную запись администратора в течение определенного периода времени. По истечении этого времени PIM удаляет роль администратора из учетной записи администратора.

PIM доступна в службе Azure Active Directory Premium P2, которая входит в состав Microsoft 365 E5. Кроме того, вы можете приобрести отдельные лицензии Azure Active Directory Premium P2 для ваших учетных записей администраторов.

Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей администраторов, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-pim).


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Управление привилегированным доступом

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

Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pam), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 2](../media/stepnumbers/Step2.png)| [Защита паролей](identity-secure-your-passwords.md) |

