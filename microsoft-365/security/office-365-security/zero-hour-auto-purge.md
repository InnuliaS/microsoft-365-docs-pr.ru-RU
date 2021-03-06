---
title: Автоматическая очистка с нулевым временем (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о том, как автоматическая очистка (ZAP) ретроактивели перемещение доставленных сообщений в почтовом ящике Exchange Online в папку нежелательной почты или в карантин, которые находятся в ретроактивели, которые могут быть нежелательными или фишингами.
ms.openlocfilehash: 612ef45194fbf70ef89eee0f455b2d4d8781247f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819428"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Автоматическая очистка (ZAP) в Exchange Online с нулевым часовым значением

## <a name="basic-features-of-zap"></a>Основные функции ZAP

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online автоматическая очистка (ZAP) — это функция защиты электронной почты, которая ретроактивели обнаруживает и неутрализес вредоносных фишинговых фишинговых сообщений, которые уже доставляются в почтовые ящики Exchange Online.

ZAP не работает в автономных средах Exchange Online Protection (EOP), защищающих локальные почтовые ящики Exchange.

## <a name="how-zap-works"></a>Как работает ZAP

Подписи нежелательной почты и вредоносных программ ежедневно обновляются в режиме реального времени. Однако пользователи могут по-прежнему получать вредоносные сообщения по различным причинам, в том числе если контент веапонизед после доставки пользователям. ZAP решает эту ошибку, постоянно отслеживая обновления подписей спама и вредоносных программ в службе. ZAP может находить и удалять сообщения, которые уже находятся в почтовом ящике пользователя.

Команда ZAP работает достаточно эффективно для пользователя; они не получают уведомления об обнаружении и перемещении сообщения.

[Списки надежных отправителей](create-safe-sender-lists-in-office-365.md), правила обработки почты (также называемые правилами транспорта), правила для папки "Входящие" или дополнительные фильтры имеют приоритет перед ZAP. Как и в случае с процессом обработки почты, это означает, что даже если служба определяет для доставленного сообщения запрос ZAP, сообщение не будет обработано в соответствии с конфигурацией "Надежные отправители". Это еще одна причина, по которой следует осторожно настраивать сообщения для обхода фильтрации.

### <a name="malware-zap"></a>Вредоносная программа ZAP

Для **чтения или непрочитанных сообщений** , которые содержат вредоносную программу после доставки, ZAP помещает сообщение, содержащее вредоносное вложение. Только администраторы могут просматривать и управлять сообщениями вредоносных программ из карантина.

Вредоносная программа ZAP включена по умолчанию в политиках защиты от вредоносных программ. Для получения дополнительных сведений см. раздел [Настройка политик защиты от вредоносных программ в EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Фишинг ZAP

Для **чтения или непрочитанных сообщений** , которые определены как фишинг после доставки, результат ZAP зависит от действия, настроенного для вредоносности фильтрации **сообщений электронной почты** в соответствующей политике защиты от нежелательной почты. В приведенном ниже списке перечислены действия по фильтрации вредоносности для фишинга и их возможные результаты.

- **Добавьте X заголовков**, в **начале строки темы с текстом**: ZAP не выполняет никаких действий с сообщением.

- **Переместить сообщение в**папку "Нежелательная почта": ZAP переместит сообщение в папку нежелательной почты, если правило нежелательной почты включено в почтовом ящике (по умолчанию он включен). Для получения дополнительных сведений см. [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online в Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Сообщение о перенаправлении на адрес электронной почты**, **Удаление сообщения**, **карантина**: ZAP помещает сообщение в карантин.

По умолчанию в политиках защиты от нежелательной почты включен фишинговый ZAP, а в качестве действия по умолчанию для фильтра **фишинговых** сообщений вредоносности — **сообщение на карантине**, то есть фишинг ZAP помещает сообщение по умолчанию.

Дополнительные сведения о настройке вердиктс фильтрации нежелательной почты см [в статье Настройка политик защиты от нежелательной почты в Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Нежелательная почта

Для **непрочитанных сообщений** , которые были определены как нежелательная почта после доставки, результат ZAP зависит от действия, настроенного для фильтрации **нежелательной почты** вредоносности в соответствующей политике защиты от нежелательной почты. В приведенном ниже списке описаны действия по фильтрации вредоносности для нежелательной почты и их возможных результатов.

- **Добавьте X заголовков**, в **начале строки темы с текстом**: ZAP не выполняет никаких действий с сообщением.

- **Переместить сообщение в**папку "Нежелательная почта": ZAP переместит сообщение в папку нежелательной почты, если правило нежелательной почты включено в почтовом ящике (по умолчанию он включен). Для получения дополнительных сведений см. [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online в Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Сообщение о перенаправлении на адрес электронной почты**, **Удаление сообщения**, **карантина**: ZAP помещает сообщение в карантин. Конечные пользователи могут просматривать сообщения на карантине нежелательной почты и управлять ими.

По умолчанию в политиках защиты от нежелательной почты включена Нежелательная почта, а в качестве действия по умолчанию **для фильтрации нежелательной почты вредоносности** перемещается **сообщение в папку нежелательной**почты, что означает, что по умолчанию программа ZAP перемещает **Непрочтенные** сообщения в папку нежелательной почты

Дополнительные сведения о настройке вердиктс фильтрации нежелательной почты см [в статье Настройка политик защиты от нежелательной почты в Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Рекомендации по использованию ZAP для Office 365 Advanced Threat protection (Office 365 ATP)

ZAP не будет помещать сообщения в карантины, которые находятся в процессе [динамической доставки](dynamic-delivery-and-previewing.md) , или если фильтрация вредоносных программ уже заменила вложение **предупреждением вредоносных программ Text.txt** файл. Если для этих типов сообщений получен сигнал фишинга или спама, а фильтр вредоносности в политике защиты от нежелательной почты настроен на выполнение некоторого действия с сообщением (перемещение в папку Нежелательная почта, перенаправление, удаление, карантин), то ZAP по умолчанию будет иметь действие "переместить в нежелательное".

## <a name="how-to-see-if-zap-moved-your-message"></a>Как убедиться, что сообщение было перемещено из ZAP

Чтобы определить, переместилось ли сообщение ZAP, можно использовать [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report) или [Обозреватель угроз (а также обнаружение в режиме реального времени)](threat-explorer.md). Обратите внимание, что в случае системного действия ZAP не регистрируется в журналах аудита почтовых ящиков Exchange.

## <a name="zap-faq"></a>ZAP ЧАСТО ЗАДАВАЕМЫЕ ВОПРОСЫ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Что произойдет, если законное сообщение перемещается в папку "Нежелательная почта"?

Для [ложных срабатываний](report-junk-email-messages-to-microsoft.md)следует соблюдать обычный процесс создания отчетов. Единственная причина, по которой сообщение было бы перемещено из папки "Входящие" в папку нежелательной почты, будет вызвано тем, что это сообщение было определено как нежелательная почта или вредоносная служба.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Что делать, если используется папка карантина вместо папки "Нежелательная почта"?

ZAP будет выполнять действия с сообщением в соответствии с конфигурацией политик защиты от нежелательной почты, как описано ранее в этой статье.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Что делать, если используются надежные отправители, правила для почтового ящика или списки разрешенных и заблокированных отправителей?

Параметры "Надежные отправители", "правила обработки почты", "блокировать и разрешить организационные параметры имеют приоритет". Эти сообщения исключаются из ZAP, так как служба выполняет настройку, которую вы настроили. Это еще одна причина, по которой следует осторожно настраивать сообщения для обхода фильтрации.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Что делать, если сообщение перемещено в другую папку (например, правила для папки "Входящие")?

ZAP все еще работает, пока сообщение не было удалено или пока не было удалено одно и то же или более надежное действие, которое еще не было применено. Например, если для политики фишинга задано значение "карантин", а пользователь или администратор уже отправил сообщение электронной почты, карантин будет предпринимать действия для помещения файла в карантин.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Влияние ZAP на удержание почтовых ящиков?

ZAP не помещает сообщения в карантин из почтовых ящиков на удержании. ZAP может перемещать сообщения в папку "Нежелательная почта" в соответствии с действиями, настроенными для нежелательной почты или фишинговых вредоносности в политиках защиты от нежелательной почты.

Дополнительные сведения о удержаниях в Exchange Online можно найти в статье [удержание на месте и удержание для судебного разбирательства в Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
