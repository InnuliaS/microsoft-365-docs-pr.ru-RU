---
title: Этап 5 - Управление мобильными устройствами
description: Microsoft 365 Enterprise включает управление мобильными устройствами с помощью Microsoft Intune. Ознакомьтесь с требованиями и необходимыми условиями, настройте Intune с помощью ресурса Azure Active Directory, регистрации устройств iOS, macOS, Android и Windows, развертывания приложений, создания профиля, использования политики соответствия и включения условного доступа для управления мобильными устройствами с помощью Microsoft 365 корпоративный.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, управление мобильными устройствами, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: c90f16bfbdf41f859e13a23fbdaeb0c3480bd191
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631529"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Этап 5: Управление мобильными устройствами для Microsoft 365 корпоративный

![Этап 5. Управление мобильными устройствами](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Эта функция применима к версиям Microsoft 365 корпоративный для E3 и, а также*

Microsoft 365 Enterprise включает функции, помогающие управлять устройствами и их приложениями в Организации. С помощью Microsoft Intune вы можете управлять устройствами iOS, Android, macOS и Windows, чтобы защитить доступ к ресурсам Организации, в том числе к данным. 

На этом этапе вы регистрируете устройства в Intune, а также создаете и накладываете политики для обеспечения безопасности и защиты данных. Всю библиотеку документации Intune [можно получить в Интернете](https://docs.microsoft.com/intune). Кроме того, перед началом работы рекомендуется ознакомиться с [руководством по планированию развертывания Intune, проектированию и реализации](https://docs.microsoft.com/intune/planning-guide) .

## <a name="step-1-plan-for-your-scenario"></a>Шаг 1: планирование для сценария

Одной из основных причин для управления мобильными устройствами является защита и защита ресурсов Организации. [Распространенные способы использования Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) перечислены в реальных примерах, в том числе обеспечение безопасности электронной почты и данных Майкрософт.

Intune предоставляет возможности для управления доступом к Организации с помощью управления мобильными устройствами (MDM) или управления мобильными приложениями (MAM). MDM — когда пользователи регистрируют свои устройства в Intune. После регистрации они будут управляемыми устройствами и могут получать любые политики, правила и параметры, используемые вашей организацией. Например, можно установить конкретные приложения, создать политику паролей, установить VPN-подключение и т. д.

Пользователи с личными устройствами могут не заносить свои устройства или управляться Intune и политиками. Но по-прежнему необходимо защищать ресурсы и данные Организации. В этом сценарии можно защитить приложения с помощью MAM. Например, вы можете использовать политику MAM, требующую от пользователя ввода ПИН-кода при доступе к SharePoint на устройстве.

Кроме того, вы узнаете, как вы будете управлять личными или принадлежащими организацией устройствами. В зависимости от их использования устройства могут работать по-разному. Например, вы можете использовать различные планы для пользователей в отделе кадров или для пользователей в продажах. [Определите сценарии использования для управления мобильными устройствами](https://docs.microsoft.com/intune/planning-guide-scenarios) , которые помогут вам приступить к работе, и включает некоторые рекомендации по этим различным сценариям.

## <a name="step-2-get-your-prerequisites"></a>Шаг 2: получение необходимых компонентов

После этого получите необходимые компоненты в соответствии с вашими требованиями и сценариями, созданными на предыдущем этапе. [Реализуйте свой план, чтобы](https://docs.microsoft.com/intune/planning-guide-onboarding) отобразить все требования. Ниже приведены важные элементы, необходимые для Intune с Microsoft 365:

- **Подписка на Intune**: входит в состав Microsoft 365 и предоставляет доступ к Microsoft Intune на [портале Azure](https://portal.azure.com) .
- **Подписка на microsoft 365**: входит в состав Microsoft 365 и используется для приложений Office, включая электронную почту.
- **Azure Active Directory (Azure AD) Premium**: входит в состав Microsoft 365 и используется для создания пользователей или групп безопасности. Эти группы получают созданные политики Intune, такие как форсирование длины пароля для разблокировки устройства. Группы, создаваемые на [этапе 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) можно использовать.

В зависимости от потребностей Организации могут потребоваться дополнительные требования. Например, если вы будете управлять устройствами iOS, вам потребуется сертификат push-уведомлений Apple MDM. Если вы используете локальный сервер Exchange, вам потребуются локальные соединители Exchange. Эти дополнительные требования обрабатываются при выполнении этих действий.

## <a name="step-3-set-up-intune"></a>Шаг 3: Настройка Intune

В Intune используются многие функции в Azure AD, в том числе ваш домен, пользователей и группы. Вы также можете создавать новых пользователей и новые группы в соответствии с потребностями компании. Например, можно создать группу с именем **устройства iOS**или **все пользователи отдела кадров**.  Используйте преимущества [динамических групп](https://docs.microsoft.com/intune/groups-add) , которые позволяют создавать группы пользователей или устройств на основе простых или расширенных правил.

Этот шаг посвящен настройке Intune и готовности к управлению устройствами.

1. **[Убедитесь, что устройства поддерживаются](https://docs.microsoft.com/intune/supported-devices-browsers)**. Подтвердите, что в Intune поддерживаются устройства iOS, macOS, Android, Галакси и Windows. Если ваша организация включает устройства, которые не поддерживаются, политики не применяются к этим устройствам.

2. **[Настройте доменное имя](https://docs.microsoft.com/intune/custom-domain-name-configure)**. По умолчанию в Azure AD автоматически создается домен с именем примерно **Your-Domain.onmicrosoft.com** . **onmicrosoft.com** можно изменить в Организации. При настройке он также предоставляет пользователям знакомый домен при подключении к Intune и использовании ресурсов.

3. **[Войдите в Intune](https://docs.microsoft.com/intune/account-sign-up)**. При входе вам может быть предложено ввести сведения о вашей организации. Intune входит в состав Microsoft 365, и ее можно открыть непосредственно из [центра администрирования Microsoft 365](https://admin.microsoft.com). Вы также можете открыть Intune напрямую на [портале Azure](https://portal.azure.com).

4. **[Выберите конфигурацию управления мобильными устройствами](https://docs.microsoft.com/intune/mdm-authority-set)**. При первом использовании Intune необходимо включить управление устройствами. Intune можно использовать в качестве облачной службы, гибридной среды с Intune и диспетчером конфигурации конечных точек Майкрософт, а также с помощью управления мобильными устройствами для Office 365. Вы можете выбрать, какая программа установки лучше всего подходит для вашей организации.

5. **[Добавление пользователей](https://docs.microsoft.com/intune/users-add)** и **[Добавление групп](https://docs.microsoft.com/intune/groups-add)**. 

   Вы можете вручную добавить пользователей или использовать гибридную идентификацию и Azure AD Connect для синхронизации локальных учетных записей пользователей с Intune. Вы также можете присвоить роли администратора определенным пользователям. Пользователи необходимы, если устройства не имеют "безпользовательющих" устройств, таких как устройства с подсистемой терминала.

   Группы Azure AD используются для упрощения управления устройствами и пользователями в Intune. С помощью групп можно выполнить множество различных задач. Например, вашей организации требуется определенное приложение на устройствах Android. Вы можете создать группу устройств Android и развернуть политику с этим приложением в группу.

    В Intune можно добавить пользователей или группы, созданные на [этапе 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Назначение лицензий](https://docs.microsoft.com/intune/licenses-assign)**. Чтобы пользователи или устройства зарегистрировались в Intune, им требуется лицензия Microsoft 365 с включенной службой Intune для доступа к службе Intune. Вы назначаете лицензии Microsoft 365 с включенной по умолчанию службой Microsoft Intune в центре администрирования Microsoft 365 или PowerShell.

## <a name="step-4-enroll-devices"></a>Шаг 4: регистрация устройств

Для управления устройствами необходимо зарегистрировать устройства в Intune. Как администратор вы настроите ограничения на регистрацию и политики для пользователей и устройств. У каждой платформы устройств (iOS, Android, macOS и Windows) есть разнообразные возможности. Пользователи могут самостоятельно регистрироваться. Кроме того, вы можете автоматизировать регистрацию, чтобы пользователи просто могли войти на устройство.

Регистрация — это ключевой шаг при использовании Intune. [Devices Devices (регистрация устройств](https://docs.microsoft.com/intune/device-enrollment) ) — список действий для различных устройств.

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: регистрация устройств с iOS и Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Шаг 5: Добавление и развертывание приложений

Приложения на мобильных устройствах часто являются быстрым способом получения доступа к корпоративным ресурсам. 

При использовании приложений возникают проблемы, так как существуют различные устройства, в том числе персональные устройства и корпоративные устройства. Кроме того, вы хотите защитить ресурсы Организации и их данные, а также обеспечить эффективность работы пользователей.

Intune может управлять приложениями, в том числе добавлять приложения, назначать их разным пользователям или группам, а также просматривать другие ключевые сведения. Например, вы можете увидеть, какие приложения не удается установить, проверить версию приложения и многое другое.

Когда пользователи получают мобильное устройство, одной из первых задач является доступ к электронной почте и документам Организации. С помощью Intune вы можете [создавать и развертывать параметры электронной почты](https://docs.microsoft.com/intune/email-settings-configure) с помощью почтовых приложений, которые были предварительно установлены на устройствах. 

В статье [Add Apps](https://docs.microsoft.com/intune/apps/apps-add) перечислены действия по добавлению, развертыванию, мониторингу, настройке и защите приложений на устройствах в вашей организации.

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: политики соответствия требованиям устройств](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Шаг 6: включение соответствия и условный доступ

На предыдущих шагах вы настроили среду и включили Intune. Теперь вы готовы создать несколько политик, использующих соответствие требованиям и условный доступ.

Для управления устройствами важно обеспечить соответствие требованиям и условный доступ. Для защиты ресурсов Организации создаются [политики соответствия требованиям](https://docs.microsoft.com/intune/device-compliance-get-started) . При создании политики соответствия вы определяете стандарт или "базовый план" того, что должно иметь устройство. Например, вы можете выбрать приемлемый (неприемлемый) уровень защиты от угроз, блокировать устройства с защитой от потери, требовать длину пароля и т. д. Если эти устройства не соответствуют правилам, что означает, что они не соответствуют требованиям, вы можете заблокировать доступ к ресурсам.

Эта "Блокировка" вводит [Условный доступ](https://docs.microsoft.com/intune/conditional-access). Если устройство считается несоответствующим, вы можете заблокировать доступ к электронной почте, SharePoint и многому другому.

Intune на [портале Azure](https://portal.azure.com) позволяет создавать эти политики и применять их к пользователям и устройствам. Рекомендуется начать мелкие и использовать поэтапный подход. Например, создайте политику iOS, которая блокирует устройства с защитой от устройства. Apply (под названием "Assign" в Intune) политика для пилотной или тестовой группы. После первоначального тестирования добавьте пользователей в пилотную группу. Используя поэтапный подход, вы можете получить отзыв из широкого диапазона пользовательских типов.

Сведения о том, как начать [работу с политиками соответствия требованиям устройств](https://docs.microsoft.com/intune/device-compliance-get-started) и [о условном доступе и Intune?](https://docs.microsoft.com/intune/conditional-access) , помогут вам приступить к работе.

## <a name="step-7-apply-features-and-settings"></a>Шаг 7: применение компонентов и параметров

Эти функции и параметры часто считаются "Крутоой" частью Intune и являются мощными. После успешного применения политик соответствия требованиям с помощью условного доступа вы можете создать **профили устройств**.

Intune на [портале Azure](https://portal.azure.com) позволяет создавать различные профили на основе платформы устройства — iOS, MacOS, Android и Windows. Например, вы можете:

- Используйте Endpoint Protection на устройствах с Windows 10 для включения различных параметров BitLocker, в том числе шифрования.
- Используйте функцию "ограниченные приложения" на устройствах iOS, чтобы создать список утвержденных приложений, которые можно установить. Или создайте список запрещенных приложений.
- Используйте параметры терминала для выбора приложений, которые можно использовать на устройствах с Android, работающих в режиме киоска.
- Примените подключение Wi/Fi и его параметры, в том числе тип безопасности, на устройствах под управлением macOS.

[Применение функций и параметров на устройствах с помощью профилей устройств](https://docs.microsoft.com/intune/device-profiles) — это отличное место для чтения сведений о профилях, Узнайте, как создать профиль и т. д.

Запомните, начните мелкие и используйте поэтапный подход. Назначьте профиль пилотной или тестовой группе. Затем назначьте профиль для дополнительных пилотных групп.

## <a name="step-8-get-to-know-the-other-features"></a>Шаг 8: знакомство с другими функциями

Intune — это мощная служба, включающая множество функций. Ниже приведены некоторые другие задачи, которые можно выполнить с помощью Intune.

- Управление программным обеспечением и обновлениями на & [компьютерах](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) [с Windows и устройствами](https://docs.microsoft.com/intune/windows-update-for-business-configure) [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Включите [Advanced Threat protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) на устройствах с Windows 10 и используйте соответствие требованиям и условный доступ для защиты доступа к корпоративным ресурсам, таким как SharePoint или Exchange Online
- Использование [Лукаут](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)и других угроз обороны для мобильных устройств
- Добавление [центра сертификации партнеров](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) для выдачи и обновления сертификатов
- [Предоставление пользователям рекомендаций для конечных пользователей](https://docs.microsoft.com/intune/end-user-educate) в приложении корпоративного портала, получения приложений и т. д.
- Отслеживать [приложения](https://docs.microsoft.com/intune/apps-monitor) и [профили соответствия требованиям к устройствам и конфигурации](https://docs.microsoft.com/intune/compliance-policy-monitor), а также дополнительные телеметрии с помощью журналов аудита. Вы также можете подключиться к [хранилищу данных Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) и использовать Power BI для получения более подробных отчетов.


## <a name="identity-and-device-access-recommendations"></a>Рекомендации по доступу для удостоверений и устройств

Корпорация Майкрософт предоставляет набор рекомендаций для [удостоверений и доступа к устройству](microsoft-365-policies-configurations.md) с целью обеспечения безопасности и эффективности работы сотрудников. Для доступа к устройству используйте рекомендации и параметры, приведенные в следующих статьях, а также действия, описанные на этом этапе:

- [Необходимые компоненты](identity-access-prerequisites.md)
- [Основные политики доступа для удостоверений и устройств](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Как корпорация Майкрософт реализует Microsoft 365 корпоративный

Узнайте, как специалисты корпорации Майкрософт [управляют устройствами с помощью EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Как корпорация Contoso реализовала Microsoft 365 корпоративный

Узнайте, как Корпорация Contoso, вымышленная, но предопределяющая многонациональная организация, [развернула инфраструктуру управления мобильными устройствами](contoso-mdm.md) с Microsoft 365 Cloud Services.

![Корпорация Contoso](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Следующий шаг

[Критерии выхода инфраструктуры управления мобильными устройствами](mobility-infrastructure-exit-criteria.md)

