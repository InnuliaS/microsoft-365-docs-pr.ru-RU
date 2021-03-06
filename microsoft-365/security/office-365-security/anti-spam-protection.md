---
title: Защита от нежелательной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о параметрах и фильтрах защиты от нежелательной почты, которые позволят предотвратить нежелательную почту в Exchange Online Protection (EOP).
ms.openlocfilehash: ce673a4bee64dfbc84f870f9cf4871e9ac32a71c
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800111"
---
# <a name="anti-spam-protection-in-eop"></a>Защита от нежелательной почты в EOP

> [!NOTE]
> Эта статья предназначена для администраторов. В разделе [Обзор фильтра нежелательной почты](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) , а также [сведения о нежелательной почте и фишинге](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online сообщения электронной почты автоматически защищаются от спама (Нежелательная почта) EOP.

Стратегия корпорации Майкрософт по обеспечению безопасности почты включает не имеющий себе равных подход для нескольких продуктов. EOP защита от нежелательной почты и фишинга применяется на платформах электронной почты для предоставления пользователям последних средств защиты от нежелательной почты и фишинга и нововведений в сети. Цель EOP  предложить функциональную и удобную почтовую службу, способную обнаруживать спам, мошеннические (фишинговые) сообщения и вредоносное программное обеспечение и защищать пользователей от них.

Все чаще электронную почту используют не по назначению. Неотслеживаемый спам может засорить почтовые ящики и сети, понизить удовлетворенность пользователей и уменьшить эффективность доставки обычных сообщений. Именно поэтому корпорация Майкрософт продолжает совершать инвестиции в технологии защиты от спама. Все начинается с ограничения и фильтрации спама.

## <a name="anti-spam-technologies-in-eop"></a>Технологии защиты от нежелательной почты в EOP

Чтобы сократить нежелательную почту, EOP включает защиту от нежелательной почты, которая использует специальные технологии фильтрации нежелательной почты, чтобы определить и отделить нежелательную почту от легальных сообщений электронной почты. Фильтрация нежелательной почты EOP рассказывает об известных угрозах нежелательной почты и фишинга и отзывов пользователей от нашей платформы потребителей, Outlook.com. Постоянная обратная связь пользователей EOP в программе классификации нежелательной почты помогает обеспечить непрерывную обучение и улучшение технологий EOP.

Параметры защиты от нежелательной почты в EOP состоят из следующих технологий:

- **Фильтрация подключений**: определяет хорошие и плохие исходные серверы электронной почты на ранних этапах подключения к входящей электронной почте через список разрешенных IP-адресов, список заблокированных IP-адресов и *список надежных* отправителей (динамический, но не редактируемый список надежных отправителей, поддерживаемых корпорацией Майкрософт). Эти параметры настраиваются в политике фильтрации подключений. Дополнительные сведения о [настройке фильтрации подключений](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Аналитика подделки использует фильтрацию подключений для создания разрешенных и заблокированных списков отправителей, которые поднимаются подмене домена электронной почты. Дополнительные сведения см. [в статье дополнительные сведения об управлении подменой в Microsoft 365](learn-about-spoof-intelligence.md).

- **Фильтрация нежелательной почты (фильтрация содержимого)**: EOP использует фильтрацию нежелательной почты **, вердиктс**нежелательные сообщения, **нежелательную почту высокой надежности**, **массовые сообщения электронной почты**, **фишинговую** почту и **фишинговую фишинг** для классификации сообщений. Вы можете настроить действия, выполняемые на основе этих вердиктс, а также настроить параметры уведомлений конечных пользователей для сообщений, помещенных в карантин, а не доставленных. Дополнительные сведения можно найти [в статье Настройка политик защиты от нежелательной почты в Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > По умолчанию фильтрация нежелательной почты настраивается на отправку сообщений, которые были помечены как нежелательная почта, в папку нежелательной почты получателя. Однако в гибридных средах, где EOP защищает локальные почтовые ящики Exchange, необходимо настроить два правила для обработки почты (также называемые правилами транспорта) в локальной организации Exchange, чтобы распознать заголовки нежелательной почты EOP, добавленные в сообщения. Дополнительные сведения см. в статье [Настройка автономной службы EOP для доставки спама в папку нежелательной почты в гибридных средах](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Фильтрация нежелательной почты**: в EOP также проверяется, чтобы пользователи не отправляли нежелательные сообщения либо в содержимом исходящих сообщений, либо при превышении ограничения исходящих сообщений. Дополнительную информацию можно узнать [в статье Настройка фильтрации исходящих нежелательных сообщений в Microsoft 365](configure-the-outbound-spam-policy.md).

- **Аналитика подделки**: Дополнительные сведения см. [в статье дополнительные сведения об управлении подменой в Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Управление ошибками в фильтре нежелательной почты

Возможно, что хорошие сообщения могут быть идентифицированы как спам (также известными как ложные срабатывания) или в папку "Входящие". Вы можете использовать предложения, приведенные в следующих разделах, чтобы узнать, что произошло, и помочь предотвратить его дальнейшие действия.

Ниже приведены некоторые рекомендации, которые применимы к одному из сценариев:

- Всегда отправляйте Неклассифицированные сообщения в корпорацию Майкрософт. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

- **Проверьте заголовки сообщений о нежелательной почте**: эти значения покажет, почему сообщение помечено как спам или почему оно пропущено при фильтрации нежелательной почты. Более подробную информацию можно узнать в статье [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).

- **Наведите запись MX на Microsoft 365**: чтобы обеспечить наилучшую защиту от EOP, мы всегда рекомендуем отправлять электронную почту в Microsoft 365 первыми. Инструкции: [CREATE DNS Records for a Host Hosting Provider для Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Если запись MX указывает на другое расположение (например, решение для борьбы с нежелательной почтой или устройство для борьбы с нежелательной почтой), то EOP не может обеспечить точную фильтрацию нежелательной почты. В этом сценарии необходимо настроить расширенную фильтрацию для соединителей (также называется _пропуск вхождения_). Инструкции см в разделе [Расширенная фильтрация соединителей в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Использовать проверку подлинности электронной почты**: Если вы владеете доменом электронной почты, вы можете использовать DNS, чтобы убедиться в подлинности сообщений от отправителей в этом домене. Для предотвращения нежелательной почты и нежелательной подмены в EOP используйте следующие способы проверки подлинности электронной почты:

  - **SPF**: инфраструктура политики отправителей проверяет IP-адрес источника сообщения относительно владельца отправляющего домена. Чтобы не [допустить подделки](set-up-spf-in-office-365-to-help-prevent-spoofing.md)и быстро настроить SPF, ознакомьтесь со статьей set up SPF. Для более глубокого понимания того, как Microsoft 365 использует SPF, или для устранения неполадок или нестандартных развертываний, таких как гибридные развертывания, начните с того, [как Microsoft 365 использует Sender Policy Framework (SPF) для предотвращения спуфинга](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys identified mail опознанная почта добавляет цифровую подпись к заголовку сообщения, отправляемого из вашего домена. Сведения о том, [как использовать DKIM для проверки исходящей электронной почты, отправленной из личного домена в Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: Доменная проверка подлинности, отчеты и соответствие, помогают системным системам назначения определить, что делать с сообщениями, которые не прошли проверку SPF или DKIM, и предоставляет другой уровень доверия партнерам электронной почты. Для получения дополнительных сведений обратитесь [к разделу Использование DMARC для проверки электронной почты в Microsoft 365](use-dmarc-to-validate-email.md).

- **Проверьте параметры массового сообщения электронной почты**: пороговое значение на уровне BCL, которое настраивается в политиках защиты от нежелательной почты определяет, помечена ли массовая почта (также известная как _серая почта_) как нежелательная почта. _Маркасспамбулкмаил_ параметр, который используется только для PowerShell, включенный по умолчанию, также влияет на результаты. Дополнительные сведения можно найти [в статье Настройка политик защиты от нежелательной почты в Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Предотвращение доставки нежелательной почты в папку "Входящие"

- **Проверьте параметры организации**: просмотрите параметры, позволяющие сообщениям пропускать фильтрацию нежелательной почты (например, при добавлении собственного домена в список разрешенных доменов в политиках защиты от нежелательной почты). Рекомендуемые параметры приведены в статье [Рекомендуемые параметры для EOP и Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md) и [Создание списков надежных отправителей](create-safe-sender-lists-in-office-365.md).

- **Убедитесь, что правило нежелательной почты включено в почтовом ящике пользователя**: он включен по умолчанию, но если он отключен, сообщения, помеченные как нежелательные, не могут быть перемещены в папку "Нежелательная почта". Для получения дополнительных сведений см. [Настройка параметров нежелательной почты в почтовых ящиках Exchange Online в Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Используйте доступные списки заблокированных отправителей**: сведения см. в разделе [Создание заблокированных списков отправителей](create-block-sender-lists-in-office-365.md).

- **Отписаться от групповой электронной почты** Если сообщение было отправлено пользователю (бюллетени, объявления о продукте и т. д.) и содержит ссылку отказа от подписки из известного источника, рассмотрите вопрос о том, что нужно отменить подписку.

- **Автономный EOP: создание правил для почтового процесса в локальной среде Exchange для фильтрации нежелательной почты EOP вердиктс**: в автономных средах EOP, где EOP защищает локальные почтовые ящики Exchange, необходимо настроить правила обработки сообщений (также называемые правилами транспорта) в локальной среде Exchange, чтобы перевести сообщение об фильтрации EOP спама, чтобы правило нежелательной почты могло переместить сообщение в папку нежелательно Дополнительные сведения см. в статье [Настройка автономной службы EOP для доставки спама в папку нежелательной почты в гибридных средах](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Предотвращение идентификации хороших сообщений электронной почты как спама

Ниже приведены некоторые действия, которые можно предпринять для предотвращения ложных срабатываний.

- **Проверьте параметры фильтра нежелательной почты Outlook пользователя**:

  - **Убедитесь, что фильтр нежелательной почты Outlook отключен**: Если для фильтра нежелательной почты Outlook задано значение по умолчанию **No автоматическая фильтрация**, Outlook не пытается классифицировать массажес как нежелательную почту.  Если установлено значение " **низкие** " или " **Высокая**", то фильтр нежелательной почты Outlook использует собственную технологию фильтра SmartScreen для обнаружения и перемещения нежелательной почты в папку нежелательной почты, поэтому вы можете получить ложные срабатывания. Обратите внимание, что корпорация Майкрософт прекратила обновление определений нежелательной почты для фильтров SmartScreen в Exchange и Outlook в ноябре 2016. Существующие определения фильтра нежелательной почты (SmartScreen) остались на месте, но их эффективность скорее всего будет снижаться со временем.

  - **Убедитесь, что параметр "только безопасные списки Outlook" отключен**: Если этот параметр включен, только сообщения от отправителей из списка "Надежные отправители" или "Надежные получатели" доставляются в папку "Входящие"; сообщения электронной почты от всех остальных пользователей автоматически перемещаются в папку "Нежелательная почта".

  Дополнительные сведения об этих параметрах приведены [в статье Настройка параметров нежелательной почты в почтовых ящиках Exchange Online в Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Используйте доступные списки надежных отправителей**: сведения см. в разделе [Создание списков надежных отправителей](create-safe-sender-lists-in-office-365.md).

- **Убедитесь, что пользователи входят в пределы отправки и получения** , как описано в разделе [Получение и отправка](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) в описании службы Exchange Online.

- **Автономный EOP: использование синхронизации службы каталогов**: Если для защиты локальной организации Exchange используется автономный EOP, необходимо синхронизировать пользовательские параметры со службой с помощью синхронизации службы каталогов. Это гарантирует использование службой EOP ваших списков надежных отправителей. Дополнительные сведения см. в разделе [Управление почтовыми пользователями с помощью синхронизации службы каталогов](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Законодательство о защите от нежелательной почты

В корпорации Майкрософт мы считаем, что разработка новых технологий и самостоятельных решений требует поддержки эффективной политики государственных учреждений и юридических платформ. В мировом росте нежелательной почты спурред многочисленные законодательные тексты для управления коммерческой почтой. Во многих странах теперь есть законы борьбы с нежелательной почтой. В США есть как федеральное, так и законное законодательство, управляющее спамом, и этот дополнительный подход помогает куртаил нежелательной почте при включении Проспер электронной коммерции. С помощью функции "Нежелательная почта" разворачиваются средства, позволяющие выбордюрить мошеннические и мошеннические сообщения электронной почты.
