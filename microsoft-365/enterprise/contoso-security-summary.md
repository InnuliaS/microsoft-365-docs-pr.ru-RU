---
title: Сводка по безопасности Microsoft 365 корпоративный для корпорации Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Сведения о том, как Contoso использует функции безопасности в Microsoft 365 корпоративный.
ms.openlocfilehash: c0f3497eb49a0490fccf6c0ec5174d932a21005e
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268402"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Сводка по безопасности Microsoft 365 корпоративный для корпорации Contoso

Чтобы ИТ-отдел безопасности утвердил развертывание Microsoft 365 корпоративный, была проведена тщательная проверка безопасности. Ниже приведены требования Contoso к безопасности для облака.

- Нужно применять самые надежные методы проверки подлинности при предоставлении доступа сотрудникам к облачным ресурсам.
- Нужно обеспечить безопасный способ подключения и доступа к приложениям для компьютеров и мобильных устройств.
- Нужно защитить компьютеры и электронную почту от вредоносных программ.
- Разрешения для облачных цифровых ресурсов должны определять субъектов и объектов доступа, допустимые действия и предоставляться по принципу доступа с минимальными привилегиями.
- Конфиденциальные и жестко регулируемые цифровые ресурсы нужно пометить, зашифровать и хранить в безопасных расположениях.
- Жестко регулируемые цифровые ресурсы следует защитить с использованием дополнительного шифрования и разрешений.
- У сотрудников отдела ИТ-безопасности должна быть возможность контролировать текущее обеспечение безопасности с помощью центральных информационных панелей и получать уведомления о событиях безопасности для быстрого реагирования и недопущения негативных последствий.

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Подготовка Contoso к обеспечению безопасности в Microsoft 365

Подготовка инфраструктуры безопасности Contoso для развертывания Microsoft 365 корпоративный включает в себя перечисленные ниже этапы.

1. Ограниченные учетные записи администраторов для облака

   Корпорация Contoso провела тщательный анализ существующих учетных записей администратора доменных служб Active Directory (AD DS) и создала ряд специальных облачных учетных записей администраторов и групп.

2. Классификация данных с разделением их на три уровня

   Корпорация Contoso провела тщательную проверку и определила три уровня данных, чтобы выбрать функции Microsoft 365 корпоративный, обеспечивающие защиту самых ценных данных.

3. Определение политик доступа, хранения и защиты информации для различных уровней данных

   Учитывая уровни данных, корпорация Contoso определила подробные требования, которые будут применяться для будущих рабочих ИТ-нагрузок, перемещаемых в облако.

В соответствии с рекомендациями по безопасности и требованиями к развертыванию Microsoft 365 корпоративный, администраторы безопасности Contoso и ИТ-отдел развернули многие функции и возможности безопасности, как описано в последующих разделах.

## <a name="identity--access-management"></a>Управление удостоверениями и доступом 

- Специальные учетные записи глобального администратора с использованием MFA и PIM

  Вместо того чтобы назначить роль глобального администратора обычным учетным записям пользователей, в Contoso создали три специальные учетные записи глобального администратора с надежными паролями и защитили их с помощью многофакторной проверки подлинности (MFA) Azure и Azure Active Directory (Azure AD) Privileged Identity Management (PIM). PIM доступно только с Microsoft 365 E5.

  Вход в учетную запись глобального администратора выполняется только для определенных задач администрирования, пароли известны только специально назначенному персоналу и могут использоваться только в течение времени, указанного в Azure AD PIM. 

  Администраторы безопасности в Contoso назначили роли администраторов с меньшими полномочиями учетным записям, которые соответствуют должностным обязанностям ИТ-специалиста.

  Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- Многофакторная проверка подлинности для всех учетных записей пользователей

  Многофакторная проверка подлинности обеспечивает дополнительный уровень защиты для процесса входа, так как пользователи обязаны принять звонок, получить SMS или уведомление в приложении на смартфоне после правильного ввода пароля. Благодаря MFA учетные записи пользователей Azure AD будут защищены от несанкционированного входа даже при компрометации пароля учетной записи.

   - Чтобы защитить подписки на Microsoft 365 от компрометации, Contoso требует прохождения многофакторной проверки подлинности для всех учетных записей глобального администратора.
   - Для защиты от фишинговых атак, в ходе которых злоумышленник компрометирует учетные данные надежного пользователя в организации и отправляет вредоносные письма, в Contoso реализовали MFA для всех учетных записей пользователей, в том числе начальников отделов и высшего руководства. 

- Повышение безопасности доступа для устройств и приложений с помощью политик условного доступа

  В Contoso применяются [политики условного доступа](microsoft-365-policies-configurations.md) для удостоверений, устройств, Exchange Online и SharePoint. Политики условного доступа для удостоверений предусматривают обязательную смену паролей для пользователей с высокой степенью риска и блокирование использования клиентами приложений, которые не поддерживают современную проверку подлинности. Политики для устройств предусматривают определение утвержденных приложений и обязательное использование компьютеров и мобильных устройств, соответствующих требованиям. Политики условного доступа для Exchange Online предусматривают блокировку клиентов ActiveSync и настройку шифрования сообщений Office 365. Политики условного доступа для SharePoint предусматривают дополнительную защиту для конфиденциальных и жестко регулируемых сайтов.

- Windows Hello для бизнеса

  Корпорация Contoso развернула и требует использовать [Windows Hello для бизнеса](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) для постепенного отказа от паролей и перехода на надежную двухфакторную проверку подлинности на компьютерах и мобильных устройствах под управлением Windows 10 Корпоративная.

- Credential Guard в Защитнике Windows

  Для защиты от целевых атак и вредоносных программ, запускаемых в операционной системе с правами администратора, специалисты Contoso активировали [Credential Guard в Защитнике Windows](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) с помощью групповых политик AD DS.

## <a name="threat-protection"></a>Защита от угроз

- Защита от вредоносных программ с помощью антивирусной программы "Защитник Windows"

  С помощью [антивирусной программы "Защитник Windows"](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) Contoso обеспечивает защиту от вредоносных программ и управляет такой защитой на компьютерах и устройствах под управлением Windows 10 Корпоративная.

- Защита потока электронной почты и ведение журнала аудита почтового ящика с помощью Office 365 Advanced Threat Protection 

  С помощью Exchange Online Protection и [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) Contoso обеспечивает защиту от неизвестных вредоносных программ, вирусов и вредоносных URL-адресов, передаваемых по электронной почте. 

  Корпорация Contoso также обеспечила ведение журнала аудита почтового ящика, чтобы определять, кто входил в почтовые ящики пользователей, отправлял сообщения и совершал другие действия, выполняемые владельцем почтового ящика, уполномоченным пользователем или администратором.

- Мониторинг и предотвращение атак с помощью инструмента анализа угроз и реагирования на них в Office 365

  Contoso использует средство для [исследования угроз и реагирования на них в Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) для защиты своих пользователей, облегчая обнаружение и отражение атак, а также предотвращение будущих атак.

- Защита от сложных угроз с помощью Advanced Threat Analytics

  С помощью [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) Contoso обеспечивает защиту от сложных целевых атак. ATA автоматически анализирует, изучает и определяет обычное и необычное поведение сущности (пользователя, устройства и ресурсов). 

## <a name="information-protection"></a>Защита информации

- Защита конфиденциальных и жестко регулируемых цифровых ресурсов с помощью меток Azure Information Protection

  Корпорация Contoso определила три уровня защиты данных и развернула [метки конфиденциальности Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels), применяемые пользователями к цифровым ресурсам. Для коммерческих тайн и другой интеллектуальной собственности Contoso использует вспомогательные метки конфиденциальности для жестко регулируемых данных. Такая политика шифрует содержимое и ограничивает доступ к определенным учетным записям пользователей и группам.

- Предотвращение утечки данных интрасети с помощью защиты от потери данных

  Корпорация Contoso настроила политики [защиты от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) для Exchange Online, SharePoint и OneDrive для бизнеса, чтобы пользователи не могли случайно или намеренно передавать конфиденциальные данные.

- Предотвращение утечек данных на устройстве с помощью Windows Information Protection

  С помощью [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) Contoso обеспечивает защиту от утечки данных через веб-приложения и службы, а также защищает корпоративные приложения и данные на корпоративных и личных устройствах, приносимых сотрудниками на работу.

- Мониторинг облака с помощью Microsoft Cloud App Security

  С помощью [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) корпорация Contoso создает схему своей облачной среды, отслеживает ее использование, определяет инциденты и события безопасности. Microsoft Cloud App Security предлагается только в плане Microsoft 365 E5.

- Управление устройствами с использованием Microsoft Intune

  Корпорация Contoso использует [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) для регистрации, контроля и настройки доступа для мобильных устройств и приложений, которые на них выполняются. Кроме того, в соответствии с политиками условного доступа для устройств необходимо использовать утвержденные приложения, а также компьютеры и мобильные устройства, соответствующие требованиям.

## <a name="security-management"></a>Управление безопасностью

- Центральная панель мониторинга безопасности для ИТ-отдела с центром безопасности Azure

  Корпорация Contoso использует единое представление безопасности и защиты от угроз, доступное в [центре безопасности Azure](https://azure.microsoft.com/services/security-center/), для управления политиками безопасности в отношении рабочих нагрузок и для реагирования на кибератаки.

- Центральная панель мониторинга безопасности, доступная пользователям на консоли "Безопасность Windows"

  Корпорация Contoso выполнила развертывание приложения [Безопасность Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) на компьютерах и других устройствах под управлением Windows 10 Корпоративная, благодаря чему пользователи сразу же видят состояние безопасности и могут предпринять соответствующие действия.

