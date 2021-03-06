---
title: Проверка подлинности электронной почты в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Администраторы могут узнать об использовании проверки подлинности электронной почты (SPF, DKIM и DMARC) в Exchange Online Protection (EOP) для предотвращения спуфинга, фишинга и спама.
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209503"
---
# <a name="email-authentication-in-eop"></a>Проверка подлинности электронной почты в EOP

Проверка подлинности электронной почты (также известная как проверка адреса электронной почты) — это набор стандартов для борьбы со спуфингом (сообщения электронной почты от поддельных отправителей). В организациях Microsoft 365 с почтовыми ящиками Exchange Online, а также в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online применяются следующие стандарты для проверки входящей электронной почты с помощью EOP:

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

Проверка подлинности электронной почты удостоверяет, что письма отправителя (например, regina@contoso.com) являются подлинными и получены доменом электронной почты из ожидаемых источников (например, contoso.com)

Далее в этой статье описываются принципы работы этих технологий, а также их использование службой EOP для проверки входящих писем.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Использование проверки подлинности электронной почты для предотвращения спуфинга

DMARC предотвращает спуфинг, анализируя адрес **отправителя** в сообщениях (адрес электронной почты отправителя, который пользователи видят в своих почтовых клиентах). Организации, которые получают электронную почту, также могут убедиться, что домен электронной почты прошел проверку SPF или DKIM, т. е. проверку подлинности, и угроза спуфинга отсутствует. 

Однако проблема заключается в том, что записи SPF, DKIM и DMARC в DNS для проверки подлинности электронной почты (известные под общим названием политик проверки подлинности электронной почты) не обязательны. Таким образом, хотя домены с надежными политиками проверки подлинности электронной почты, например, microsoft.com и skype.com, защищены от спуфинга, домены, которые используют менее надежные политики либо вообще не имеют никакой специальной политики, являются основной целью спуфинга.

В марте 2018 г. только 9 % доменов компаний из списка Fortune 500 публиковали надежные политики проверки подлинности электронной почты. В остальных компаниях (91%) адреса могут быть подделаны злоумышленниками. Если не используется какой-либо другой механизм фильтрации электронной почты, сообщения от поддельных отправителей в этих доменах могут быть доставлены пользователям.

![Политики DMARC компаний из списка Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Доля компаний малого и среднего бизнеса, не входящих в список Fortune 500, которые публикуют строгие политики проверки подлинности электронной почты, небольшая, и снижается для доменов электронной почты, которые находятся за пределами Северной Америки и Западной Европы.

Это серьезная проблема, так как предприятие может не иметь четкого представления о том, как работает проверка подлинности электронной почты, в то время как злоумышленники отлично это знают и могут этим воспользоваться. Так как фишинг является серьезной проблемой, а также из-за ограниченного внедрения политик проверки подлинности электронной почты, корпорация Майкрософт использует *неявную проверку подлинности* для проверки входящих писем.

Неявная проверка подлинности проводится на основе многочисленных расширений для обычных политик проверки подлинности электронной почты. Эти расширения включают репутацию отправителя, журнал отправителя, журнал получателя, анализ поведения и другие дополнительные методы. Сообщение, отправленное с домена, который не использует политики проверки подлинности электронной почты, помечается как поддельное, если оно не содержит другие сигналы, подтверждающие его подлинность.

Общее извещение корпорации Майкрософт см. в статье [Море фишинга, часть 2 — Улучшенные средства борьбы со спуфингом в Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Многофакторная аутентификация

Хотя SPF, DKIM и DMARC полезны сами по себе, они не позволяют сообщить о достаточности проверки подлинности в случае, если в сообщении не содержится записей о явной проверке подлинности. Поэтому корпорация Майкрософт разработала алгоритм неявной проверки подлинности, который объединяет несколько сигналов в одно значение, — _многофакторную аутентификацию_. Значение многофакторной аутентификации добавляется в заголовок **Authentication-Results** в заголовках сообщений.

> Authentication-Results:<br/>&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\>

Эти значения описываются в разделе [Заголовок сообщения Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).

Изучив заголовки сообщений, администраторы и даже пользователи могут увидеть, каким образом Microsoft 365 определил, что отправитель поддельный.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Почему проверки подлинности электронной почты может быть недостаточно для борьбы со спуфингом

Использование только записей проверки подлинности электронной почты для определения, является ли входящее письмо поддельным, имеет следующие ограничения:

- В отправляющем домене могут отсутствовать необходимые записи DNS, или же они могут быть неправильно настроены.

- Записи DNS исходного домена настроены правильно, но он не совпадает с доменом в адресе отправителя. SPF и DKIM не требуют использовать домен в адресе отправителя. Злоумышленники или надежные службы могут зарегистрировать домен, настроить для него записи SPF и DKIM, использовать совершенно другой домен в адресе отправителя, и это сообщение пройдет проверку SPF и DKIM.

Многофакторная аутентификация позволяет устранить эти ограничения, пропуская сообщения, которые иначе не прошли бы проверку подлинности.

> [!NOTE]
> Как упоминалось выше, при неявной проверке подлинности используется несколько сигналов, чтобы определить, является ли сообщение подлинным. Для наглядности в приведенных ниже примерах рассматриваются результаты проверки подлинности электронной почты. Другие интеллектуальные факторы серверной части могли определить сообщения, которые прошли проверку подлинности, как поддельные, а сообщения, которые не прошли проверку, как подлинные.

Например, для домена fabrikam.com записи SPF, DKIM или DMARC отсутствуют. Сообщения от отправителей в домене fabrikam.com могут не пройти многофакторную аутентификацию (обратите внимание на значение `compauth` и причину):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Если fabrikam.com настраивает запись SPF и не настраивает DKIM, сообщение может пройти многофакторную аутентификацию, так как домен, прошедший проверку SPF, соответствует домену в адресе отправителя:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Если fabrikam.com настраивает запись DKIM и не настраивает SPF, сообщение может пройти многофакторную аутентификацию, так как домен в подписи DKIM соответствует домену в адресе отправителя:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Если домен в записи SPF или подписи DKIM не соответствует домену в адресе отправителя, сообщение может не пройти многофакторную аутентификацию.

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Решения для добросовестных отправителей, которые отправляют письма без проверки подлинности

Microsoft 365 сохраняет сведения о том, кто отправляет непроверенную электронную почту вашей организации. Если служба считает, что отправитель является ненадежным, она будет помечать почту как не прошедшую многофакторную аутентификацию. Чтобы избежать этого, воспользуйтесь рекомендациями из этого раздела.

### <a name="configure-email-authentication-for-domains-you-own"></a>Настройка проверки подлинности электронной почты для доменов, которыми вы владеете

Этот метод можно использовать для устранения спуфинга внутри организации, а также междоменного спуфинга, если вы владеете несколькими клиентами или взаимодействуете с ними. Он также позволяет устранить междоменный спуфинг, когда сообщения отправляются пользователям в среде Microsoft 365 или третьим сторонам, размещенным другими поставщиками.

- [Настройте записи SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) для ваших доменов.

- [Настройте записи DKIM](use-dkim-to-validate-outbound-email.md) для ваших основных доменов.

- [Рекомендуем настроить записи DMARC ](use-dmarc-to-validate-email.md) для вашего домена, чтобы определить добросовестных отправителей.

Майкрософт не предоставляет подробные рекомендации по реализации для записей SPF, DKIM и DMARC. Однако большой объем информации доступен в Интернете. Существуют также сторонние компании, которые могут помочь вашей организации настроить записи для проверки подлинности электронной почты.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Вы не знаете все источники ваших писем

Многие домены не публикуют записи SPF, так как они не знают все источники сообщений электронной почты. Начните с публикации записи SPF, содержащей все источники электронной почты, о которых вы знаете (особенно при наличии корпоративного трафика), и опубликуйте нейтральную политику SPF `?all`. Например:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Этот пример означает, что электронная почта из вашей корпоративной инфраструктуры пройдет проверку подлинности, а электронная почта из неизвестных источников будет возвращаться к нейтральному состоянию.

Microsoft 365 будет рассматривать входящие письма из вашей корпоративной инфраструктуры как прошедшие проверку подлинности, а письма из неизвестных источников могут быть помечены как поддельные (в зависимости от того, может ли Microsoft 365 выполнить неявную проверку подлинности). Но это все равно является шагом вперед по сравнению с ситуацией, когда все электронные письма помечались как поддельные в Microsoft 365.

Приступив к работе с политикой возврата SPF `?all`, вы можете постепенно найти и добавить больше источников для ваших сообщений, а затем обновить запись SPF с помощью более строгой политики.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Использование аналитики спуфинга для настройки разрешенных отправителей непроверенной электронной почты

Вы также можете использовать [аналитику спуфинга](learn-about-spoof-intelligence.md), чтобы предоставить отправителям разрешение на передачу непроверенных сообщений в вашей организации.

Для внешних доменов поддельный пользователь — это домен в адресе отправителя, а инфраструктура отправки — это либо исходный IP-адрес (разделенный на /24 диапазоны CIDR), либо домен организации в записи обратного поиска в DNS (запись типа PTR).

На снимке экрана, приведенном ниже, исходный IP-адрес — 131.107.18.4, с записью типа PTR outbound.mail.protection.outlook.com. Она будет отображаться как outlook.com для инфраструктуры отправки.

Чтобы предоставить этому отправителю разрешение на отправку неавторизованной электронной почты, измените значение с **Нет** на **Да**.

![Настройка разрешенных отправителей для защиты от спуфинга](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Создание разрешающей записи для пары отправитель-получатель

Чтобы обойти фильтрацию спама и некоторые компоненты фильтрации фишинга, но оставить фильтрацию вредоносных программ для определенных отправителей, см. статью [Создание списков надежных отправителей в Microsoft 365](create-safe-sender-lists-in-office-365.md).

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Попросите отправителя настроить проверку подлинности электронной почты для доменов, которые вам не принадлежат

Из-за проблем со спамом и фишинговыми сообщениями корпорация Майкрософт рекомендует проверку подлинности электронной почты для всех организаций электронной почты. Вместо настройки переопределения вручную в вашей организации вы можете попросить администратора в отправляющем домене настроить записи проверки подлинности электронной почты.

- Даже если им не нужно было публиковать записи проверки подлинности в прошлом, они придется сделать это сейчас, если они отправляют электронную почту в корпорацию Майкрософт.

- Настройте SPF для публикации IP-адреса отправителя для вашего домена, а также настройте DKIM (при наличии) для добавления цифровой подписи к сообщениям. Кроме того, следует рассмотреть возможность настройки записей DMARC.

- Если они используют массовые рассылки для отправки электронной почты от их имени, убедитесь, что домен в адресе отправителя (если он принадлежит им) соответствует домену, который прошел проверку SPF или DMARC.

- Убедитесь, что указанные ниже расположения (если они используют их) включены в запись SPF:
  
  - Локальные почтовые серверы.
  - Электронная почта, отправленная SaaS-поставщиком (программное обеспечение как услуга).
  - Электронная почта, отправленная службой размещения в облаке (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services и т. д.).

- Для небольших доменов, размещенных поставщиком услуг Интернета, настройте запись SPF согласно инструкциям поставщика.

Хотя сначала может показаться сложным заставить домены отправителя настроить проверку подлинности, но со временем, когда все новые и новые фильтры почты начнут отправлять в нежелательную почту или даже отклонять их почту, это заставит из настроить корректные записи для гарантии нормальной доставки почты. Кроме того, они могут помочь в борьбе с фишингом и снизить его вероятность в своей организации либо в организациях, которым они отправляют почту.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Сведения для поставщиков инфраструктуры (поставщики услуг Интернета, ESP и службы размещения в облаке)

Если вы размещаете электронную почту для домена или предоставляете инфраструктуру для размещения, которая позволяет отправлять почту, выполните указанные ниже действия.

- Убедитесь, что у ваших клиентов есть документация, в которой объясняется, как пользователи могут настраивать записи SPF.

- Рассмотрите возможность использования подписей DKIM для исходящих писем, даже если клиент не настроил эту опцию явным образом (подпись с доменом по умолчанию). Вы можете даже дважды подписать электронную почту с помощью подписей DKIM (один раз с доменом клиента, если они настроили эту опцию, и еще раз с помощью подписи DKIM вашей организации)

Доставка в корпорацию Майкрософт не гарантируется, даже если пройдена проверка подлинности электронной почты, поступающей с вашей платформы, но, по крайней мере, вы можете быть уверены, что корпорация Майкрософт не будет направлять ваши письма в папку с нежелательными сообщения, которые не прошли проверку подлинности.

Дополнительные сведения о рекомендациях поставщиков услуг см. в статье [M3AAWG: Рекомендации по обмену мобильными сообщениями для поставщиков услуг](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
