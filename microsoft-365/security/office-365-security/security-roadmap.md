---
title: План безопасности Microsoft 365 — основные приоритеты
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Основные рекомендации от группы циберсекурити корпорации Майкрософт для реализации возможностей обеспечения безопасности, защищающих среду Microsoft 365. '
ms.openlocfilehash: 968d2c5a2e8954df97fb884da6fab967b7cc806b
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726467"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>План безопасности — основные приоритеты для первых 30 дней, 90 дней и более поздних

В этой статье описываются основные рекомендации от группы циберсекурити корпорации Майкрософт по реализации возможностей обеспечения безопасности, защищающих среду Microsoft 365. Эта статья размещается в сеансе Microsoft Ignite, поэтому [Безопасность microsoft 365 подобна циберсекурити Pro: высшие приоритеты для первых 30 дней, 90 дней и более поздних](https://www.youtube.com/watch?v=luignzNyR-o). Этот сеанс был разработан и представлен маркировкой Симос и Мэтт Кемелхар, корпоративных Циберсекурити архитекторов.

В этой статье

- [Результаты плана](security-roadmap.md#Roadmap)

- [30 дней — мощная быстрая служба WINS](security-roadmap.md#Thirdaydays)

- [90 дней — расширенные возможности защиты](security-roadmap.md#Ninetydays)

- [Сверх](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Результаты плана
<a name="Roadmap"> </a>

Эти рекомендации по работе с планами помещаются на три фазы в логическом порядке со следующими целями.

|||
|:-----|:-----|
| |Результаты
|30 дней|Быстрая настройка:  <br/> * Основные средства защиты администратора  <br/> * Ведение журналов и аналитика  <br/> * Основные средства защиты идентификации  <br/> Конфигурация клиента  <br/>  Подготовка заинтересованных лиц|
|90 дней|Расширенные возможности защиты:  <br/> * Учетные записи администраторов  <br/>  * &amp; Учетные записи пользователей данных  <br/>  Отображение соответствия требованиям, угрозам и потребностям пользователей  <br/>  Адаптация и реализация политик и средств защиты по умолчанию|
|Сверх|Настройка и уточнение ключевых политик и элементов управления  <br/> Расширение возможностей защиты локальной зависимости  <br/> Интеграция с бизнес-процессами и процессами безопасности (юридическая, угроза для участников и т. д.)|



## <a name="30-days--powerful-quick-wins"></a>30 дней — мощная быстрая служба WINS
<a name="Thirdaydays"> </a>

Эти задачи выполняются быстро и почти не влияют на пользователей.

|||
|:-----|:-----|
|Область|Задачи|
|Управление безопасностью|* Проверьте контрольный рейтинг и запишите текущую оценку ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Включите ведение журнала аудита для Office 365. Обратитесь [к разделу Поиск в журнале аудита](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Настройка Microsoft 365 для повышения безопасности](tenant-wide-setup-for-increased-security.md) .  <br/>  * Регулярно изучите панели мониторинга и отчеты в центре безопасности Майкрософт 365 и в Cloud App Security.|
|Защита от угроз|[Подключите microsoft 365 к Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) , чтобы начать мониторинг с использованием политик обнаружения угроз по умолчанию для аномальных поведений. Создание базового плана для обнаружения аномалий занимает семь дней.  <br><br/>  Реализация защиты для учетных записей администраторов:  <br/> * Используйте выделенные учетные записи администраторов для действий администратора.  <br/>  * Принудительная многофакторная проверка подлинности (MFA) для учетных записей администраторов.  <br/>  * Используйте [строго безопасное устройство Windows 10](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) для действий администратора.|
|Управление идентификацией и доступом|* [Включите защиту удостоверений Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Для сред федеративного удостоверения необходимо обеспечить безопасность учетной записи (длина пароля, возраст, сложность и т. д.).|
|Защита информации| Ознакомьтесь с примерами рекомендаций по защите информации. Защита информации требует координации в Организации. Приступите к работе с помощью этих ресурсов:  <br/> * [Office 365 Information Protection для GDPR](https://aka.ms/o365gdpr) <br/> * [Настройка Teams с тремя уровнями защиты](../../solutions/configure-teams-three-tiers-protection.md) (включая общий доступ, классификацию, предотвращение потери данных и Azure Information Protection)|

## <a name="90-days--enhanced-protections"></a>90 дней — расширенные возможности защиты
<a name="Ninetydays"> </a>

Планирование и реализация этих задач занимают немного больше времени, но это значительно повысит безопасность ваших данных.

|||
|:-----|:-----|
|Область|Task|
|Управление безопасностью|* Проверьте безопасность оценки для рекомендуемых действий в среде ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Продолжайте регулярно просматривать панели мониторинга и отчеты в центре безопасности Майкрософт 365, в средствах Cloud App Security и SIEM. <br/> * Ищите и реализуйте обновления программного обеспечения. <br/> * Выполните имитацию атаки для спеар-фишинга, пароля и атаки методом грубой силы с помощью [симулятора атак](attack-simulator.md) (входит в состав [Office 365 Threat Intelligence](office-365-ti.md)).  <br/> * Найдите риск для общего доступа, просмотрев встроенные отчеты в Cloud App Security (на вкладке "исследование"). <br/> * Проверьте состояние [соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) для нормативных требований, которые применяются к вашей организации (например, GDPR, NIST 800-171).|
|Защита от угроз| Реализация расширенной защиты для учетных записей администраторов: <br/> * Настройка [привилегированных рабочих станций доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (павс) для действий администратора. <br/> * Настройка [Azure AD с правами на управление удостоверениями](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * Настройка средств безопасности и управления событиями (SIEM) для сбора данных ведения журнала из Office 365, Cloud App Security и других служб, в том числе служб федерации Active Directory. В журнале аудита хранятся данные только в 90 дней. Захват этих данных в инструменте SIEM позволяет хранить данные в течение более длительного времени.|
|Управление идентификацией и доступом|* Включение и применение MFA для всех пользователей. <br/> * Реализуйте набор [условного доступа и связанных политик](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Защита информации| Адаптируйте и реализуйте политики защиты информации. К этим ресурсам относятся примеры: <br/> * [Office 365 Information Protection для GDPR](https://aka.ms/o365gdpr) <br/> * [Настройка Teams с тремя уровнями защиты](../../solutions/configure-teams-three-tiers-protection.md) <br/> <br> Использование политик защиты от потери данных и средств мониторинга в Microsoft 365 для данных, хранящихся в Microsoft 365 (а не в Cloud App Security). <br><br>Используйте Cloud App Security с Microsoft 365 для расширенных функций оповещения (Кроме защиты от потери данных).|

## <a name="beyond"></a>Сверх
<a name="Beyond"> </a>

Это важные меры безопасности, которые создаются в предыдущей работе.

|||
|:-----|:-----|
|Область|Task|
|Управление безопасностью|* Продолжайте планировать дальнейшие действия с помощью параметра Secure Score ( [https://securescore.office.com](https://securescore.office.com) ). <br/> * Продолжайте регулярно просматривать панели мониторинга и отчеты в центре безопасности Майкрософт 365, в средствах Cloud App Security и SIEM. <br/> * Продолжайте поиск и внедрение обновлений программного обеспечения. <br/> * Интегрируйте обнаружение электронных данных с вашими юридическими и безугрозными процессами.|
|Защита от угроз|* Реализация [безопасного привилегированного доступа](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) для компонентов удостоверения в локальной среде (AD, AD FS). <br/> * Используйте Cloud App Security для отслеживания угроз для предварительной оценки. <br/> * Откройте теневое использование SaaS с помощью Cloud App Security.|
|Управление идентификацией и доступом|* Уточнение политик и рабочих процессов. <br/> * Используйте защиту удостоверений Azure AD, чтобы определить угрозы для предварительной оценки.|
|Защита информации| Уточнение политик защиты информации: <br/> * Microsoft 365 и Office 365 метки конфиденциальности и защита от потери данных (DLP) или Azure Information Protection. <br/> * Политики и оповещения Cloud App Security.|

Кроме того, [в этой статье приведены инструкции по устранению быстрых кибератаки, таких как Петя и ваннакрипт](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
