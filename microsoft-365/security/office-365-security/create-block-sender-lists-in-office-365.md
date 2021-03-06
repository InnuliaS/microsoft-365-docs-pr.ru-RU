---
title: Создание списков заблокированных отправителей
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
search.appverid:
- MET150s
description: Администраторы могут узнать о доступных и предпочтительных параметрах для блокировки входящих сообщений в Exchange Online Protection (EOP).
ms.openlocfilehash: 2862fa4a33a31eac9c61f94aa929133d2dc69fc8
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545904"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Создание списков заблокированных отправителей в EOP

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP предлагает несколько способов блокировки электронной почты от нежелательных отправителей. К этим параметрам относятся Заблокированные отправители, списки отправителей и заблокированные списки доменов в политиках защиты от нежелательной почты, правилах для почтовых ящиков Exchange (также называемые правилами транспорта) и список заблокированных IP-адресов (фильтрация подключений). В совокупности эти параметры можно рассматривать как _Заблокированные списки отправителей_.

Наилучший способ заблокировать отправители зависит от области влияния. Для одного пользователя верное решение может быть заблокированными отправителями Outlook. Для многих пользователей один из других вариантов будет более соответствующим. Следующие параметры ранжированы по обеим областям влияния и широте. Список ведет от узкого к широкому, но для получения подробных рекомендаций *Ознакомьтесь с конкретными* рекомендациями.

1. Заблокированные отправители Outlook (список заблокированных отправителей, хранящийся в каждом почтовом ящике)

2. Заблокированные списки отправителей или заблокированные списки доменов (политики защиты от нежелательной почты)

3. Правила потока обработки почты

4. Список заблокированных IP-адресов (фильтрация подключений)

> [!NOTE]
> Несмотря на то, что параметры блокировки на уровне Организации можно использовать для устранения ложных отрицательных результатов (пропущенных нежелательных сообщений), их также следует отправлять в корпорацию Майкрософт для анализа. Управление ложными негативами с помощью блочных списков значительно увеличивает административные издержки. Если вы используете блокирующие списки, чтобы отследить пропущенные нежелательные сообщения, вам необходимо сохранить в [корпорацию Майкрософт сообщения и файлы отчета](report-junk-email-messages-to-microsoft.md) .

В отличие от этого, у вас также есть несколько параметров, позволяющих всегда разрешать электронную почту из определенных источников, используя _списки надежных отправителей_. Дополнительные сведения см. в статье [Создание списков надежных отправителей](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Общие сведения о сообщениях электронной почты

Стандартное SMTP-сообщение электронной почты состоит из *конверта сообщения* и его содержимого. Конверт сообщения содержит сведения, необходимые для передачи и доставки сообщения между SMTP-серверами. Содержимое сообщения разделяется на поля заголовка сообщения, которые в совокупности называются *заголовком сообщения*, и текста сообщения. Конверт сообщения описан в RFC 5321, а заголовок сообщения описан в RFC 5322. Получатели не видят собственно конверт сообщения, так как он создается процессом передачи сообщений, и фактически не является частью сообщения.

- `5321.MailFrom`Адрес электронной почты, который используется для передачи сообщения по протоколу SMTP, — это адрес электронной почты, который также называется адресом **электронной почты** , отправителями и отправителями конвертов. Этот адрес электронной почты обычно записывается в поле заголовка " **Возврат-путь** " в заголовке сообщения (хотя можно указать другой адрес электронной почты для **получения пути** ). Если сообщение не может быть доставлено, это получатель отчета о недоставке (также известного как сообщение о недоставке или сообщение Bounce).

- `5322.From`(Другое название — "адрес **From** отправителя" или "отправитель P2") — это адрес электронной почты в поле заголовка " **от** ", а это адрес электронной почты отправителя, отображаемый в почтовых клиентах.

Часто `5321.MailFrom` `5322.From` адреса и адреса одинаковы (взаимодействие между пользователями). Однако при отправке сообщения электронной почты от имени другого пользователя адреса могут отличаться.

Заблокированные списки отправителей и заблокированные списки доменов в политиках защиты от нежелательной почты в EOP проверяют оба `5321.MailFrom` `5322.From` адреса. Заблокированные отправители Outlook используют только `5322.From` адрес.

## <a name="use-outlook-blocked-senders"></a>Использование заблокированных отправителей Outlook

Если Нежелательная почта получает небольшое количество пользователей, пользователи или Администраторы могут добавить адреса электронной почты отправителя в список заблокированных отправителей почтового ящика. Инструкции приведены в статье [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

При успешной блокировке сообщений из списка заблокированных отправителей пользователя в поле заголовка **X-Forefront-защиты от спама-Report** будет содержаться значение `SFV:BLK` .

> [!NOTE]
> Если нежелательные сообщения являются новостями из надежных и распознаваемых источников, то отмена подписки на электронную почту является еще одним вариантом прекращения приема сообщений пользователем.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Использование списков заблокированных отправителей и заблокированных списков доменов

Если затрагивается несколько пользователей, область расширяется, поэтому следующий наиболее подходящий вариант блокирует списки отправителей или заблокированные списки доменов в политиках защиты от нежелательной почты. Сообщения от отправителей в списках помечаются как **Нежелательная почта**, а действие, настроенное для фильтра **нежелательной почты** вредоносности, принимается на сообщение. Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

Максимальное число таких списков составляет около 1000 записей.

## <a name="use-mail-flow-rules"></a>Использование правил для обработки почтового процесса

Если необходимо заблокировать сообщения, отправленные определенным пользователям или всей Организации, можно использовать правила для обработки почтового процесса. Правила для обработки почтовых ящиков более гибки, чем блокирование списков отправителей или заблокированных списков отправителей, так как они также могут искать нежелательные сообщения по ключевым словам или другим свойствам.

Независимо от условий или исключений, которые вы используете для идентификации сообщений, необходимо настроить действие, чтобы задать для сообщения уровень вероятности нежелательной почты равным 9, который помечает сообщение как **Нежелательная почта высокой надежности**. Дополнительные сведения см. в статье [Использование правил для обработки почты для установки вероятности нежелательной почты в сообщениях](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Очень просто создавать *неагрессивные* правила, поэтому важно определить только те сообщения, которые вы хотите заблокировать с использованием определенных критериев. Кроме того, обязательно включите аудит для правила и проверьте результаты правила, чтобы убедиться, что все работает должным образом.

## <a name="use-the-ip-block-list"></a>Использование черного списка IP-адресов

Если невозможно использовать один из других вариантов для блокировки отправителя, *только тогда* следует использовать список заблокированных IP-адресов в политике фильтрации подключений. Дополнительные сведения см. в статье [Configure the connection filter policy](configure-the-connection-filter-policy.md). Важно, чтобы количество заблокированных IP-адресов было минимальным, поэтому *не* рекомендуется блокировать все диапазоны IP-адресов.

*Особенно* следует избегать добавления диапазонов IP-адресов, принадлежащих к службам-получателям (например, Outlook.com) или общим инфраструктурам, а также убедиться в том, что список ЗАБЛОКИРОВАННЫХ IP-адресов будет проверяться как часть обычного обслуживания.
