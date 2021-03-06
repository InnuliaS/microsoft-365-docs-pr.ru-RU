---
title: Настройка защиты от фишинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Администраторы могут научиться определять причины и способ сообщения фишинга в Microsoft 365, а также что делать, чтобы предотвратить большее количество фишинговых сообщений в будущем.
ms.openlocfilehash: ac416da714e30491f679e22909010a8c02fac843
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755056"
---
# <a name="tune-anti-phishing-protection"></a>Настройка защиты от фишинга

Несмотря на то что в Microsoft 365 существует множество функций защиты от фишинга, которые включены по умолчанию, некоторые фишинговые сообщения могут быть по-прежнему доставляются в почтовые ящики. В этом разделе описывается, что можно сделать, чтобы узнать, почему сообщение фишинга было получено, и что можно сделать для настройки параметров защиты от фишинга в организации Microsoft 365 _без случайного внесения_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Сначала выполните действия, связанные с любыми скомпрометированными учетными записями, и убедитесь, что вы блокируете все сообщения с фишингом от получения

Если учетная запись получателя была скомпрометирована в результате фишингового сообщения, выполните действия, описанные в разделе [ответ на скомпрометированную учетную запись электронной почты в Microsoft 365](responding-to-a-compromised-email-account.md).

Если ваша подписка включает Advanced Threat protection (ATP), вы можете использовать [Office 365 Threat Intelligence](office-365-ti.md) , чтобы определить других пользователей, которые также получили сообщение фишинга. Вы можете заблокировать фишинговые сообщения с дополнительными параметрами:

- [Безопасные ссылки ATP](set-up-atp-safe-links-policies.md)

- [Безопасные вложения ATP](set-up-atp-safe-attachments-policies.md)

- [Политики защиты от фишинга ATP в Microsoft 365](configure-atp-anti-phishing-policies.md). Обратите внимание, что вы можете временно увеличить **пороговые значения расширенного фишинга** в политике от **стандарта** к **агрессивному**, **более агрессивному**или **наиболее агрессивному**.

Убедитесь, что функции ATP включены.

## <a name="report-the-phishing-message-to-microsoft"></a>Сообщить о phishing-сообщениях корпорации Майкрософт

Создание отчетов о фишинговых сообщениях полезно при настройке фильтров, используемых для защиты всех клиентов в Microsoft 365. Инструкции приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Проверка заголовков сообщений

Вы можете проверить заголовки сообщения фишинга, чтобы убедиться, что вы можете сделать что-либо, чтобы предотвратить появление более фишинговых сообщений. Другими словами, исследование заголовков сообщений поможет определить параметры в Организации, которые отвечают за разрешение фишинговых сообщений в.

В частности, следует проверить поле заголовка **X-Forefront-защиты от спама-Report** в заголовках сообщений для указания пропущенных фильтров нежелательной почты или фишинга в значении фильтра нежелательной почты ВРЕДОНОСНОСТИ (SFV). Для сообщений, пропускаемых при фильтрации, будет задано значение `SCL:-1` , то есть одно из параметров, разрешенное этим сообщением путем переопределения спама или вердиктс фишинга, определенных службой. Дополнительные сведения о том, как получить заголовки сообщений и полный список всех доступных заголовков сообщений для защиты от нежелательной почты и фишинга, приведены [в статье заголовки сообщений по защите от нежелательной почты в Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Рекомендации по обеспечению защиты

- По месячной основе выполните [оценку](../mtp/microsoft-secure-score.md) безопасности для оценки параметров безопасности Организации.

- Для сообщений, которые отправляются в карантин по ошибке, или для сообщений, разрешенных с помощью, рекомендуется искать эти сообщения в [обозревателе угроз и обнаружения в режиме реального времени](threat-explorer.md). Вы можете выполнять поиск по отправителю, получателю или ИДЕНТИФИКАТОРу сообщения. Найдя сообщение, перейдите к разделу сведения, щелкнув тему. Для сообщения, помещенного в карантин, посмотрите, что такое технология обнаружения, чтобы можно было использовать для переопределения соответствующий метод. Для разрешенного сообщения проверьте, какая политика разрешает сообщение. 

- Поддельная почта помечается как "фишинг" в ATP. Иногда подмена неблагоприятна, и иногда пользователям не требуется карантина. Чтобы свести к минимуму влияние на пользователей, периодически изучите [отчет аналитики подделки](learn-about-spoof-intelligence.md). После того как вы проверили и внесли необходимые переопределения, можете быть уверены, что необходимо [настроить логику операций подделки](set-up-anti-phishing-policies.md#spoof-settings) для **карантина** подозрительных сообщений, а не доставки их в папку нежелательной почты пользователя.

- Вы можете повторить этот шаг для олицетворения (домена или пользователя). Отчет об олицетворении находится в разделе **Threat Management** \> **Dashboard** \> **Insights**панели управления угрозами.

- Периодически изучите [отчет о состоянии защиты от угроз](view-reports-for-atp.md#threat-protection-status-report).

- Некоторые пользователи случайно разрешают фишинговые сообщения, помещая собственные домены в списке Разрешить отправителя или разрешить домены в политиках защиты от нежелательной почты. Несмотря на то, что эта конфигурация позволит использовать некоторые законные сообщения, она также позволит использовать вредоносные сообщения, которые обычно блокируются фильтрами нежелательной почты и/или фишинга. Вместо того чтобы разрешать домен, следует исправить базовую проблему.

  Лучший способ работы с законными сообщениями, которые блокируются Microsoft 365 (ложные срабатывания), которые включают отправителей в вашем домене, — полностью и полностью настраивают записи SPF, DKIM и DMARC в DNS для _всех_ доменов электронной почты:

  - Убедитесь, что запись SPF определяет _все_ источники электронной почты для отправителей в вашем домене (не забывайте о сторонних службах!).

  - Используйте жесткое завершение ( \- все), чтобы убедиться, что нежелательные отправители отклоняются почтовыми системами, настроенными для этого. Можно использовать [логику подделки](learn-about-spoof-intelligence.md) для определения отправителей, использующих ваш домен, чтобы вы могли добавить авторизованных отправителей сторонних поставщиков в запись SPF.

  Инструкции по настройке можно найти в следующих статьях:
  
  - [Настройка SPF для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена](use-dkim-to-validate-outbound-email.md)

  - [Использование протокола DMARC для проверки электронной почты](use-dmarc-to-validate-email.md)

- По мере возможности рекомендуется доставлять электронную почту для домена непосредственно в Microsoft 365. Другими словами, укажите запись MX домена Microsoft 365 в Microsoft 365. Exchange Online Protection (EOP) может предоставить лучшую защиту облачных пользователей, когда их почта доставляется непосредственно в Microsoft 365. Если необходимо использовать сторонние системы электронной почты санацией перед EOP, используйте расширенную фильтрацию для соединителей. Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Пользователи должны [сообщить сообщения](enable-the-report-message-add-in.md) в корпорацию Майкрософт, что может обучить систему. Кроме того, администраторы должны использовать возможности [отправки администратором](admin-submission.md) .

- Многофакторная проверка подлинности (MFA) является хорошим способом предотвращения скомпрометированных учетных записей. Необходимо строго рассмотреть включение MFA для всех пользователей. Для поэтапного подхода Начните с включения MFA для наиболее важных пользователей (администраторов, руководителей и т. д.), прежде чем включать MFA для всех. Инструкции приведены в разделе [Настройка многофакторной проверки подлинности](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Правила пересылки внешним получателям часто используются злоумышленниками для извлечения данных. Используйте сведения о **правилах пересылки почтовых ящиков** в [показателе безопасности Майкрософт](../mtp/microsoft-secure-score.md) , чтобы найти и даже предотвратить появление правил пересылки внешним получателям. Дополнительные сведения приведены в статье [Устранение внешних правил переадресации клиентов с помощью оценки безопасности](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
