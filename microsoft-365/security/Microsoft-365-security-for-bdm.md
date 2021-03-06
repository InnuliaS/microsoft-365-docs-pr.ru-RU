---
title: Microsoft 365 Security для лиц, принимающих решения в Организации (вариантах развертывания)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: наиболее распространенные сценарии угроз и атак, которые в настоящее время сталкиваются организациями для своих сред Microsoft 365, и рекомендуемые действия по устранению этих рисков.
ms.openlocfilehash: 894486951deac7e9c157409af8da5e813b53343b
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739231"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security для лиц, принимающих решения в Организации (вариантах развертывания)

В этой статье описываются некоторые из наиболее распространенных сценариев угроз и атак, которые в настоящее время встречаются в организациях для своих сред Microsoft 365, а также Рекомендуемые действия по устранению этих рисков. Несмотря на то что Microsoft 365 поставляется с широким набором предварительно настроенных функций безопасности, он также требует от пользователя ответственности за обеспечение безопасности собственных удостоверений, данных и устройств, используемых для доступа к облачным службам. Это руководство было создано с помощью Козетаной системы безопасности (архитектор Microsoft Cloud Cloud архитектора) и Сиагараж Сундараражан (старший консультант Майкрософт).

Эта статья упорядочена по приоритету работы, начиная с защиты учетных записей, используемых для администрирования самых важных служб и ресурсов, таких как клиент, электронная почта и SharePoint. Он предоставляет методичному способ для обеспечения безопасности и работает вместе со следующей таблицей, чтобы можно было отслеживать ход выполнения в рамках своей организации с помощью заинтересованных лиц и teams: [Microsoft 365 Security for вариантах развертывания электронной таблицы](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![Изображение эскиза Microsoft 365 BDM, электронная таблица рекомендаций по безопасности](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Корпорация Майкрософт предоставляет вам средство безопасного оценки в рамках клиента для автоматического анализа уровня безопасности на основе регулярных действий, назначения оценки и предоставления рекомендаций по улучшению безопасности. Прежде чем приступать к действиям, рекомендуемым в этой статье, запишите текущие оценки и рекомендации. Рекомендуемые действия, описанные в этой статье, увеличивают рейтинг. Цель не допустить максимальной оценки, но знать о возможностях защиты среды не так, чтобы они не влияли на производительность ваших пользователей. Просмотр [оценки безопасности Майкрософт](mtp/microsoft-secure-score.md).

Еще одну вещь, прежде чем начать работу. . . обязательно [включите журнал аудита](../compliance/search-the-audit-log-in-security-and-compliance.md). Эти данные понадобятся позже, в случае необходимости изучения инцидента или нарушения. 

## <a name="protect-privileged-accounts"></a>Защита привилегированных учетных записей

На первом этапе мы рекомендуем гарантировать, что критические учетные записи в среде получают дополнительный уровень защиты, так как эти учетные записи имеют доступ и разрешения на управление и изменение критически важных служб и ресурсов, которые могут негативно повлиять на всю организацию, если она скомпрометирована. Защита привилегированных учетных записей является одним из наиболее эффективных способов защиты от злоумышленника, пытающегося повысить уровень разрешений скомпрометированной учетной записи до администратора. 

|Рекомендация  |E3 |E5  |
|---------|---------|---------|
|Применение многофакторной проверки подлинности (MFA) для всех учетных записей администраторов.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)| 
|Реализуйте управление привилегированными удостоверениями Azure Active Directory (Azure AD), чтобы применить привилегированный доступ к ресурсам Azure AD и Azure. Вы также можете узнать, у кого есть доступ, и проверить привилегированный доступ.|         | ![Зеленая галочка](../media/green-check-mark.png)|
|Реализуйте управление привилегированным доступом для управления детализированным доступом к задачам привилегированного администрирования в Office 365. |         | ![Зеленая галочка](../media/green-check-mark.png)|
|Настройка и использование привилегированных рабочих станций доступа (PAW) для управления службами. Не используйте одни рабочие станции для просмотра Интернета и проверки электронной почты, не связанной с учетной записью администратора.|  ![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png) | 

Эти возможности показаны на следующей схеме.
![Рекомендуемые возможности для защиты привилегированных учетных записей](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Дополнительные рекомендации:
- Убедитесь, что учетные записи, синхронизированные из локальной службы, не назначены ролям администратора для облачных служб. Это помогает предотвратить использование локальных учетных записей злоумышленниками для получения административного доступа к облачным службам. 
- Убедитесь, что учетным записям служб не назначены роли администратора. Эти учетные записи часто не отслеживаются и не устанавливаются с использованием паролей, срок действия которых не ограничен. Для начала убедитесь, что учетные записи служб AADConnect и ADFS не являются глобальными администраторами по умолчанию.
- Удаление лицензий из учетных записей администраторов. Если нет определенного варианта использования для назначения лицензий определенным учетным записям администраторов, удалите лицензии из этих учетных записей. 

## <a name="reduce-the-surface-of-attack"></a>Сокращение поверхности атаки

Следующая область фокуса уменьшает область атаки. Это может быть выполнено с минимальными усилиями и влиянием на пользователей и службы. Благодаря снижению контактной зоны атаке злоумышленники имеют меньше способов запустить атаку в Организации.

Ниже приводятся примеры:
- Отключите протоколы POP3, IMAP и SMTP. Большинство современных организаций больше не используют устаревшие протоколы. Вы можете безопасно отключить эти и разрешить исключения только по мере необходимости. 
- Сократите и сохраните число глобальных администраторов в клиенте до минимального минимального необходимого значения. Это позволяет немедленно уменьшить контактную зону для всех облачных приложений. 
- Выснятие с учета серверов и приложений, которые больше не используются в вашей среде. 
- Реализуйте процесс отключения и удаления учетных записей, которые больше не используются. 

## <a name="protect-against-known-threats"></a>Защита от известных угроз

Известные угрозы включают вредоносные программы, скомпрометированные учетные записи и фишинг. Некоторые средства защиты от этих угроз можно быстро реализовать без прямого воздействия на пользователей, в то время как другие требуют больше планирования и обучения пользователей. 

|Рекомендация  |E3  |E5  |
|---------|---------|---------|
|**Настройка многофакторной проверки подлинности и использование рекомендуемых политик условного доступа, в том числе политик риска входа**. Корпорация Майкрософт рекомендует и проверила набор политик, которые совместно работают для защиты всех облачных приложений, в том числе Office 365 и Microsoft 365 Services. Просмотр [конфигураций доступа для удостоверений и устройств](../enterprise/microsoft-365-policies-configurations.md). | |![Зеленая галочка](../media/green-check-mark.png)|
|**Требовать многофакторную проверку подлинности для всех пользователей**. Если у вас нет лицензирования, необходимого для реализации рекомендуемых политик условного доступа, по меньшей мере требуется многофакторная проверка подлинности для всех пользователей.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|**Повышение уровня защиты от вредоносных программ в почте**. Ваша среда Office 365 или Microsoft 365 включает защиту от вредоносных программ, но вы можете повысить эту защиту, блокируя вложения с типами файлов, которые часто используются для вредоносных программ.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|**Защитите электронную почту от целевых фишинговых атак**. Если вы настроили один или несколько пользовательских доменов для вашей среды Office 365 или Microsoft 365, вы можете настроить эту антифишинговую защиту. Функция защиты от фишинга ATP, которая входит в состав Office 365 Advanced Threat Protection, поможет защитить организацию от атак фишинга и других фишинговых атак на основе олицетворения злоумышленников. Если вы еще не настроили личный домен, это не требуется.| |![Зеленая галочка](../media/green-check-mark.png)|
|**Защита от атак программой "почта" в сообщении электронной почты**. Отменяет доступ к данным с помощью шифрования файлов или блокировки экранов компьютера. Затем он предпринимает попытку ексторт денег от жертв, запросив "Рансом", как правило, в виде криптокурренЦиес, например биткоин, в Exchange для возвращения доступа к данным. Можно защититься от атаки с помощью атаки путем создания одного или нескольких правил обработки почты, чтобы заблокировать расширения файлов, которые обычно используются для атаки программой «почта», или предупредить пользователей, которые получают эти вложения, в электронном письме.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|**Блокировать подключения из стран, с которыми вы не работают**. Создайте политику условного доступа Azure AD, чтобы заблокировать все подключения, поступающие из этих стран, с помощью эффективного создания географического брандмауэра для клиента.| |![Зеленая галочка](../media/green-check-mark.png)|

Эти возможности показаны на следующей схеме.
![Рекомендуемые возможности для защиты от известных угроз](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Защита от неизвестных угроз

Добавив дополнительные меры защиты к привилегированным учетным записям и защищая их от известных атак, вы перемещаете внимание на защиту от неизвестных угроз. Чем определено и расширено адверсариес использовать инновационные и новые неизвестные методы для атак организаций. Благодаря обширной телеметрии данных корпорации Майкрософт, собранных на основе миллиардов устройств, приложений и служб, мы можем выполнить расширенную защиту от угроз для Windows, Office 365 и Azure, чтобы предотвратить атаки с нулевым сроком действия, используя среды Санд и проверив действия перед предоставлением доступа к контенту. 


|Рекомендация  |E3  |E5  |
|---------|---------|---------|
|**Настройка Office 365 Advanced Threat protection (ATP)**:<br>* Безопасные вложения ATP<br>* Безопасные ссылки ATP<br>* ATP для SharePoint, OneDrive и Microsoft Teams<br>* Защита от фишинга ATP|         |![Зеленая галочка](../media/green-check-mark.png) |
|**Настройка функций Advanced Threat Protection в защитнике Майкрософт**:<br>* Антивирусная программа "Защитник Windows" <br>* Защита от эксплойтов <br> * Снижение уязвимой зоны <br> * Изоляция на основе оборудования <br>* Контролируемый доступ к папкам     |         |![Зеленая галочка](../media/green-check-mark.png) |
|**Используйте Microsoft Cloud App Security** для обнаружения приложений SaaS и начните использовать анализ поведения и обнаружение аномалий. |         |![Зеленая галочка](../media/green-check-mark.png) |

Эти возможности показаны на следующей схеме.
![Рекомендуемые возможности для защиты от неизвестных угроз](../media/m365-security-bdm-illustrations-unknown-threats.png)

Дополнительные рекомендации:
- Обеспечение безопасности канала связи в виде электронных сообщений с помощью протокола TLS.
- Откройте Федерацию Teams только для партнеров, с которыми вы обмениваетесь данными.
- Не добавляйте домены отправителей, отдельные отправители или исходные IP-адреса в список разрешений, так как это позволяет обходить проверки нежелательной почты и вредоносных программ, а общедоступные клиенты добавляют собственные обслуживаемые домены или другие домены, в которых сообщения о неполадках могут поступать в список разрешенных. Не добавляйте домены в список фильтров нежелательной почты и подключений, так как они могут обходить все проверки нежелательной почты. 
- Включите уведомления об исходящих сообщениях о нежелательной почте — включите уведомления об исходящих сообщениях нежелательной почты в список рассылки, чтобы сообщить о том, что любой из внутренних пользователей отправляет нежелательную почту извне. Это может быть индикатором того, что учетная запись была скомпрометирована.
- Отключить удаленную оболочку PowerShell для всех пользователей — удаленная оболочка PowerShell в основном используется администраторами для доступа к службам для административных целей или доступа к программным API. Мы рекомендуем отключить этот параметр для пользователей, не являющихся администраторами, чтобы избежать реконнаиссанце, если у них нет бизнес-требований для доступа к нему. 
- Заблокируйте доступ к порталу управления Microsoft Azure для всех, не являющихся администраторами. Это можно сделать, создав правило условного доступа, чтобы заблокировать всех пользователей, за исключением администраторов. 


## <a name="assume-breach"></a>Считать нарушение

Несмотря на то, что корпорация Майкрософт принимает все возможные меры по предотвращению угроз и атак, мы рекомендуем всегда работать в соответствии с размышлениям "нарушение безопасности". Даже если злоумышленнику удается получить доступ к среде, необходимо убедиться, что они не могут ексфилтрате данные или идентификационные данные из среды. По этой причине мы рекомендуем включать защиту от потерь конфиденциальных данных, таких как номера социального страхования, номера кредитных карт, дополнительные персональные данные и другие конфиденциальные сведения об уровне Организации. 

Для установки "нарушение безопасности" требуется реализация стратегии сети с нулевым доверием, то есть пользователи не являются полностью доверенными только потому, что они являются внутренними по отношению к сети. Вместо этого в рамках авторизации действий, которые могут выполнять пользователи, задаются наборы условий, а при выполнении таких условий применяются определенные элементы управления. Условия могут включать состояние работоспособности устройства, доступное приложение, выполняемые операции и риск для пользователей. Например, действие регистрации устройства всегда должно запускать проверку подлинности MFA, чтобы не допустить добавления устройств рауже в среду. 

Стратегия сети с нулевым доверием также требует, чтобы вы знали, где хранятся ваши данные, и применяет соответствующие элементы управления для классификации, защиты и хранения. Чтобы эффективно защитить наиболее важные и конфиденциальные ресурсы, необходимо сначала определить, где они находятся, и принять участие в инвентаризации, что может быть непростой задачей. После этого работайте с Организацией, чтобы определить стратегию управления. Определение схемы классификации для Организации и Настройка политик, меток и условий требует тщательного планирования и подготовки. Важно понимать, что это не процесс, управляемый ИТ-процессом. Обязательно работайте с юридическими и юридическими командами, чтобы разработать соответствующую классификацию и схему маркировки для данных вашей организации.

Microsoft 365 Information Protection поможет вам определить, какая информация у вас есть, где она хранится, и какую информацию требует дополнительная защита. Информационная защита — непрерывный процесс, а возможности Microsoft 365 предоставляют представление о том, как пользователи используют и отправляют конфиденциальную информацию, в которой в настоящее время хранятся данные, и где они передаются. Вы также можете узнать, как пользователи обрабатывают данные, поднадзорные, чтобы убедиться, что применяются соответствующие метки и системы защиты.


|Рекомендация |E3|E5 |
|---------|---------|---------|
|**Проверьте и оптимизируйте условный доступ и связанные с ними политики, чтобы они соответствовали целям для сети с нулевым доверием**. Защита от известных угроз включает реализацию набора [рекомендуемых политик](../enterprise/microsoft-365-policies-configurations.md). Изучите реализацию этих политик, чтобы убедиться, что ваши приложения и данные защищены от хакеров, получивших доступ к вашей сети. Обратите внимание, что рекомендуемая политика защиты приложений Intune для Windows 10 включает Windows Information Protection (WIP). НЗП обеспечивает защиту от случайных потерь данных Организации с помощью приложений и служб, таких как электронная почта, социальные сети и общедоступное облако. |         |![Зеленая галочка](../media/green-check-mark.png)|
|**Отключить внешнюю переадресацию электронной почты**. Хакеры, которые получают доступ к почтовому ящику пользователя, могут украсть свою почту, настроив почтовый ящик на автоматическую пересылку электронной почты. Это может произойти даже без информирования пользователя. Вы можете предотвратить возникновение этой ситуации, настроив правило для процесса обработки почты.|![Зеленая галочка](../media/green-check-mark.png) |![Зеленая галочка](../media/green-check-mark.png)|
|**Отключить общий доступ к анонимному внешнему календарю**. По умолчанию разрешен общий доступ к внешним анонимным календарям. [Запретите общий доступ к календарю](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) , чтобы снизить вероятность потери конфиденциальной информации.|![Зеленая галочка](../media/green-check-mark.png) |![Зеленая галочка](../media/green-check-mark.png)|
|**Настройка политик защиты от потери данных для конфиденциальных данных**. Создайте политику защиты от потери данных в &amp; центре соответствия требованиям безопасности для обнаружения и защиты конфиденциальных данных, таких как номера кредитных карт, номера социального страхования и номера банковских счетов. Microsoft 365 включает множество предопределенных типов конфиденциальных данных, которые можно использовать в политиках защиты от потери данных. Вы также можете создавать собственные типы конфиденциальной информации для конфиденциальных данных, которые являются настраиваемыми для вашей среды. |![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|**Реализуйте политики классификации данных и защиты информации**. Реализуйте метки конфиденциальности и используйте их для классификации и применения защиты к конфиденциальным данным. Вы также можете использовать эти метки в политиках защиты от потери данных. Если вы используете метки Azure Information Protection, рекомендуем не создавать новые метки в других центрах администрирования.|         |![Зеленая галочка](../media/green-check-mark.png)|
|**Защита данных в сторонних приложениях и службах с помощью Cloud App Security**. Настройте политики Cloud App Security для защиты конфиденциальной информации среди сторонних облачных приложений, таких как Salesforce, Box или Dropbox. Вы можете использовать типы конфиденциальной информации и метки конфиденциальности, созданные в политиках Cloud App Security, и применять их к своим приложениям SaaS. <br><br>Microsoft Cloud App Security позволяет применять широкий спектр автоматизированных процессов. Политики можно настроить для обеспечения непрерывных проверок соответствия требованиям, юридических задач обнаружения электронных данных, DLP для конфиденциального контента, доступного общедоступного и т. д. Cloud App Security может отслеживать любой тип файлов на основе более 20 фильтров метаданных (например, уровень доступа, тип файла). |         |![Зеленая галочка](../media/green-check-mark.png)|
|**Используйте [пакет ATP для защитника Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) , чтобы определить, хранят ли пользователи конфиденциальные данные на своих устройствах Windows**. |         |![Зеленая галочка](../media/green-check-mark.png)|
|**Использование [сканера административной](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) установки для определения и классификации данных на серверах и общих файловых ресурсах**. Используйте средство создания отчетов точка административной установки для просмотра результатов и выполнения соответствующих действий.|         |![Зеленая галочка](../media/green-check-mark.png)|

Эти возможности показаны на следующей схеме.
![Рекомендуемые возможности для защиты от нарушений](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Непрерывный мониторинг и аудит

Последний, но не самый минимум постоянный мониторинг и Аудит среды Microsoft 365 вместе с окнами и устройствами очень важно, чтобы убедиться в том, что вы можете быстро обнаруживать и устранять любые вторжения. Такие средства, как "Оценка безопасности", "Центр безопасности" и "интеллектуальный анализ интеллектуального анализа Microsoft интеллектуального анализа" содержат неважную информацию о клиенте и связывают значительные объемы данных о безопасности и безопасности, чтобы обеспечить непревзойденную защиту и обнаружение угроз.


|Рекомендация |E3 |E5 |
|---------|---------|---------|
|Убедитесь, что **журнал аудита** включен.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|**Обзор по безопасному показателю еженедельно** — показатель безопасности является центральным расположением для доступа к состоянию безопасности компании и выполнения действий в соответствии с рекомендациями по обеспечению безопасной оценки. Эту проверку рекомендуется выполнять еженедельно.|![Зеленая галочка](../media/green-check-mark.png)|![Зеленая галочка](../media/green-check-mark.png)|
|Использование средств **Office 365 ATP** :<br>* Исследование угроз и возможности реагирования<br> * Автоматическое исследование и ответ |         |![Зеленая галочка](../media/green-check-mark.png)|
|Использование **пакета ATP для защитника Майкрософт**:<br> *    [Обнаружение и ответ конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Оценка безопасности автоматического исследования и исправления <br>*    [Расширенный поиск](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![Зеленая галочка](../media/green-check-mark.png)|
|Используйте **Microsoft Cloud App Security** для обнаружения нетипичного поведения в облачных приложениях, чтобы определить, скомпрометированные пользователи или мошеннические приложения, проанализировать использование высокой степени риска и исправить его автоматически, чтобы ограничить риск для Организации.|         |![Зеленая галочка](../media/green-check-mark.png)|
|Используйте **Microsoft Azure Sentinel** или текущее средство SIEM для отслеживания угроз в среде. |         |![Зеленая галочка](../media/green-check-mark.png)|
|**Разверните [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** для мониторинга и защиты от угроз, предназначенных для локальной среды Active Directory.   |         |![Зеленая галочка](../media/green-check-mark.png) |
|Используйте **Центр безопасности Azure** для отслеживания угроз между гибридными и облачными рабочими нагрузками. Центр безопасности Azure включает в себя бесплатный уровень возможностей и стандартный уровень возможностей, которые оплачиваются на основе рабочих часов или транзакций.|         |         |

Эти возможности показаны на следующей схеме.
![Рекомендуемые возможности для непрерывного мониторинга и аудита](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Основные Рекомендуемые действия по мониторингу:
- **Ознакомьтесь с оценочным рейтингом корпорации Майкрософт** (по ценным показателем) — это центральное расположение для доступа к состоянию безопасности клиента и выполнения действий на основе основных рекомендаций. Эту проверку рекомендуется выполнять еженедельно. Показатель безопасности включает рекомендации по использованию Azure AD, Intune, Cloud App Security и Advanced Threat Protection в защитнике Майкрософт, а также Office 365. 
- **Еженедельное рассмотрение нерискованных учетных записей** — используйте центр администрирования Azure AD для еженедельного просмотра рискованных входов. Рекомендуемый набор правил идентификации и доступа к устройствам содержит политику, обеспечивающую изменение паролей для рискованных входов.  
- **Еженедельно изучите самые популярные вредоносные и фишинговые пользователи** — используйте проводник угроз Office Advanced Threat Protection, чтобы просмотреть основные пользователи, которым назначены вредоносные программы и фишинга, и узнать, почему эти пользователи подвержены воздействию этой проблемы.
