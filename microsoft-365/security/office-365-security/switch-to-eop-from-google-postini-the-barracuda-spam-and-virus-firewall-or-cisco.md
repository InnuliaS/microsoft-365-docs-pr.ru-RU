---
title: Переключение на EOP из другой службы защиты
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
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: В этой статье рассказывается, как переключиться на Exchange Online Protection (EOP) с локального устройства электронной почты санацией или облачной службы защиты.
ms.openlocfilehash: d7b2cfbe84d1e03bcd549c5220f6063592962792
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209275"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Переход на EOP с Google Postini, Barracuda Spam and Virus Firewall или Cisco IronPort

 Задача этого раздела  помочь понять процесс перехода на Exchange Online Protection (EOP) со средств локальной санации электронной почты или облачных служб защиты и рассказать о ресурсах справки, с которых можно начать работу. Существует множество решений для фильтрации нежелательной почты, но в большинстве случаев процесс перехода на EOP примерно одинаков.

Если вы впервые используете EOP и хотите ознакомиться с обзором его функций, прежде чем приступать к переходу, начните с раздела [Обзор Exchange Online Protection](exchange-online-protection-overview.md) .

Перед переходом на EOP важно решить, будут ли почтовые ящики, защищенные EOP, располагаться в облаке, в Exchange Online, локально или будет использован гибридный сценарий. (Слово "гибридный" подразумевает, что часть почтовых ящиков будет располагаться локально, а часть  в Exchange Online.) Можно использовать любые сценарии: хранение в облаке, локальное или гибридное хранение, но для каждого случая действия по настройке могут отличаться. Ниже приведено несколько рекомендаций, призванных помочь выбрать соответствующее развертывание.

- **EOP защиту с локальными почтовыми ящиками**: Этот сценарий подходит, если вы хотите использовать существующую инфраструктуру хостинга почты или бизнес-требования для хранения локальных почтовых ящиков, и вы хотите использовать EOP в качестве облачной защиты электронной почты. Этот сценарий подробнее описан в разделе [Switch to EOP standalone](#switch-to-eop-standalone).

- **EOP защита с помощью почтовых ящиков Exchange Online**: Этот сценарий подходит для защиты от EOP и всех почтовых ящиков, размещенных в облаке. Это поможет уменьшить сложность, так как нет необходимости в обслуживании локальных серверов обмена сообщениями. В этой статье описывается, [как перейти на Exchange Online](#switch-to-exchange-online) .

- **EOP защита с помощью гибридных почтовых ящиков**: возможно, вы хотите использовать облачные почтовые ящики, но необходимо хранить почтовые ящики для локальных пользователей. Выберите этот вариант, если вы хотите, чтобы некоторые почтовые ящики размещались в локальной и другой части, размещенной в Exchange Online. Этот сценарий описан в разделе [Switch to a hybrid solution](#switch-to-a-hybrid-solution).

## <a name="switch-to-eop-standalone"></a>Переход на автономную EOP

Если в настоящее время почтовые ящики хранятся локально и используются средства локальной защиты или облачная служба санации сообщений, можно перейти на EOP, чтобы получить преимущества от использования ее функций защиты и ее доступности. Чтобы настроить EOP для сценария автономного использования, который подразумевает, что почтовые ящики хранятся локально, а для защиты почты используется EOP, выполните действия, описанные в разделе [Настройка службы EOP](set-up-your-eop-service.md). В этом разделе описаны действия по настройке защиты EOP, включающие выполнение входа, добавление домена и настройку потока обработки почты с помощью соединителей.

## <a name="switch-to-exchange-online"></a>Переход на Exchange Online

Возможно, у вас есть локальные почтовые ящики, защищенные локальным устройством, и вы хотите перейти к почтовым ящикам в облачной среде Exchange Online и EOP защиту, чтобы воспользоваться преимуществами Microsoft 365 Cloud Messaging and Protection Features. Чтобы приступить к работе, вы можете зарегистрироваться в Microsoft 365 и добавить свой домен. В этом сценарии не требуется настраивать соединители, поскольку нет маршрутизации на локальные почтовые ящики. Начните с [получения последних расширенных функций с Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) для регистрации и знакомства с ее функциями.

В процессе установки Microsoft 365 вы создадите облачные пользователи почтовых ящиков.

## <a name="switch-to-a-hybrid-solution"></a>Переход на гибридное решение

Из-за внутриорганизационных требований или нормативных актов вам может потребоваться переместить в облако только часть почтовых ящиков. При развертывании гибридного сценария можно переместить почтовые ящики в облако согласно внутриорганизационным требованиям. Переход на гибридный сценарий с защитой EOP выполняется более сложно, чем переход на полностью облачный сценарий, но корпорация Майкрософт обеспечивает полную гибридную поддержку и достаточные ресурсы, чтобы упростить такой переход.

При рассмотрении гибридного развертывания лучше всего начать с [гибридного развертывания Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). Кроме того, существует несколько различных способов маршрутизации почты в гибридном сценарии, которые важно понимать. [Маршрутизация транспорта в гибридных развертываниях Exchange](https://docs.microsoft.com/exchange/transport-routing) объясняет каждый тип, поэтому вы можете выбрать оптимальный сценарий маршрутизации в соответствии с бизнес-требованиями.

## <a name="migration-planning"></a>Планирование миграции

Если принято решение переходить на EOP, обратите особое внимание на следующие области.

- **Настраиваемые правила фильтрации**: если у вас есть настраиваемые фильтры или правила бизнес-политики для перехвата определенных нежелательных сообщений, мы рекомендуем попробовать EOP с параметрами по умолчанию в течение определенного периода времени, прежде чем вы перенесете правила. EOP предлагает защиту от нежелательной почты на уровне предприятия с использованием параметров по умолчанию, что может привести к ненужному переносу некоторых правил в EOP. Конечно же, если имеются правила, реализующие определенные пользовательские бизнес-политики, можно создать их. [Правила для поток обработки почты (правила транспорта) в Exchange Online Protection](mail-flow-rules-transport-rules-0.md) содержит подробные инструкции по созданию правил для почтового процесса в EOP.

- **Списки разрешенных IP-адресов и списки заблокированных IP-адресов**: если у вас есть разрешение на списки и списки блокировок для отдельных пользователей, то можете некоторое время скопировать списки в EOP в рамках процесса установки. Дополнительные сведения о списке разрешенных IP-адресов и списке заблокированных IP-адресов приведены в разделе [Настройка политики фильтра подключений](configure-the-connection-filter-policy.md).

- **Безопасная связь**: если у вас есть партнер, которому требуется зашифрованный обмен сообщениями, рекомендуется настроить его в центре администрирования Exchange. Чтобы настроить этот сценарий, ознакомьтесь [со статьей Настройка соединителей для защиты почтового процесса с помощью партнерской организации](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> При переходе от локальных средств к EOP можно оставить это средство или сервер на своем месте для выполнения проверки бизнес-правил. Например, если устройство выполняет настраиваемую фильтрацию для исходящей почты и вы хотите, чтобы оно продолжалось, можно настроить EOP на отправку почты непосредственно на устройство для дополнительной фильтрации перед маршрутизацией в Интернет.
