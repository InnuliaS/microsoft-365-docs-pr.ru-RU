---
title: Рекомендации по настройке EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Следуйте этим рекомендациям для автономной защиты Exchange Online (EOP), чтобы настроить их для успешной работы и избежать распространенных ошибок конфигурации.
ms.openlocfilehash: e5e87883e9c8aad21552ebf306a9716f14532884
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739086"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Рекомендации по настройке автономной EOP

Следуйте этим рекомендациям для автономной защиты Exchange Online (EOP), чтобы настроить их для успешной работы и избежать распространенных ошибок конфигурации. Предполагается, что вы уже завершили установку EOP. В противном случае изучите статью [Настройка службы EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Использование тестового домена

Рекомендуем опробовать функции службы в тестовом домене, поддомене или небольшом домене, прежде чем использовать их в крупных рабочих доменах.

## <a name="synchronize-recipients"></a>Синхронизация получателей

Если ваша организация имеет существующие учетные записи пользователей в локальной среде Active Directory, вы можете синхронизировать эти учетные записи с Azure Active Directory в облаке. Рекомендуется использовать синхронизацию службы каталогов. Дополнительные сведения о преимуществах использования синхронизации службы каталогов и действиях по ее настройке можно найти [в разделе Manage Mail Users in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Рекомендуемые параметры

Мы поможем администраторам безопасности настроить параметры безопасности для удовлетворения потребностей Организации. Несмотря на то, что как правило, в EOP и Office 365 ATP рекомендуется использовать два уровня безопасности: Standard и Option. Эти параметры перечислены в разделе [Рекомендуемые параметры безопасности для EOP и Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Параметры прочих и неизменяемых политик

Эти параметры охватывают ряд функций, которые выходят за пределы политик безопасности.

|||||
|---|---|---|---|
|**Имя компонента безопасности**|**Standard**|**Жестк**|**Comment**|
|[Настройка SPF для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Да|Да||
|[Проверка исходящей электронной почты, отправляемой с личного домена в Office 365, с помощью DKIM](use-dkim-to-validate-outbound-email.md)|Да|Да||
|[Использование протокола DMARC для проверки электронной почты в Office 365](use-dmarc-to-validate-email.md)|Да|Да|Используется `action=quarantine` для стандартных и `action=reject` для ограничений.|
|Развертывание [надстройки Report Message](enable-the-report-message-add-in.md) для усовершенствования сведений о подозрительных сообщениях для конечных пользователей|Да|Да||
|Планирование отчетов о вредоносных и нежелательных сообщениях|Да|Да||
|Автоматическая переадресация на внешние домены запрещена или не отслеживается|Да|Да||
|Общий аудит должен быть включен|Да|Да||
|[Подключение IMAP к почтовому ящику](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|[Подключение POP к почтовому ящику](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|Отправка с проверкой подлинности SMTP|Отключено|Отключено|Для отправки электронной почты клиентам POP3 и IMAP4 требуется отправка с проверкой подлинности по протоколу SMTP клиента (также называемой отправкой SMTP-сообщений или SMTP-АУТЕНТИФИКАЦИей).|
|Подключение EWS к почтовому ящику|Отключено|Отключено||
|[Подключение PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Отключено|Отключено|Доступно для пользователей почтовых ящиков или почтовых пользователей (объекты пользователей, возвращаемые командлетом [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Добавление отправителей в белый список с помощью [логики анализа подделки](learn-about-spoof-intelligence.md)|Да|Да||
|[Пограничная блокировка на основе каталогов (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Включена|Включена|Тип домена = удостоверяющий|
|[Настройка многофакторной проверки подлинности для всех учетных записей администраторов](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Включена|Включена||
|

## <a name="troubleshooting"></a>Устранение неполадок

Устранение общих проблем и тенденций с помощью отчетов в центре администрирования. Используйте средство трассировки сообщений, чтобы найти конкретные данные о сообщении. Узнайте больше о составлении отчетов [и трассировке сообщений в Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Узнайте больше о средстве трассировки сообщений в [трассировке сообщений в центре безопасности & соответствия требованиям](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Сообщить о ложных срабатываниях и ложных негативах в корпорацию Майкрософт

Чтобы упростить фильтрацию нежелательной почты в службе для всех, необходимо сообщить о ложном срабатывании (хорошее сообщение отмечено как плохое) и ложные отрицательные (недопустимые сообщения электронной почты) в корпорацию Майкрософт для анализа. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Создание правил транспорта

Создайте правила для обработки почтовых ящиков (также называемые правилами транспорта) или настраиваемые фильтры в соответствии с бизнес-потребностями.

When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.

При развертывании новых правил рассмотрите возможность добавления действия **Создать отчет об инциденте** для отслеживания используемого правила.

В гибридных средах, в которых ваша организация включает как локальные Exchange, так и Exchange Online, рассмотрите условия, которые вы используете в правилах для обработки почтового процесса. Если вы хотите применить правила ко всей Организации, обязательно используйте условия, доступные как в локальном, так и в Exchange Online. В обеих средах доступны и другие условия, но они доступны только в одной среде или другом. Дополнительные сведения о [правилах для поток обработки почты (правила транспорта) в Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
