---
title: Обязанности клиентов и партнеров в сфере облачных служб по обеспечению непрерывности бизнес-процессов предприятий
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Из этой статьи вы узнаете о том, что предпринимает корпорация Майкрософт, когда возникает инцидент, связанный с какой-либо ее службой. Это позволит вам оптимизировать свои планы по обеспечению непрерывности бизнес-процессов.
ms.openlocfilehash: 3d4a1d6c3a69be4cb3051125d5527b1f0b25b375
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067682"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>Обязанности клиентов и партнеров в сфере облачных служб по управлению непрерывностью бизнес-процессов предприятий

При предоставлении облачных служб Microsoft 365 вашим пользователям ваша организация и корпорация Майкрософт становятся партнерами. Майкрософт предоставляет эти службы, а вы отвечаете за подключение клиентских конечных точек, управление идентификаторами и доступом и способы использования этих служб. Есть и совместные обязанности, связанные с идентификаторами, а также с инфраструктурой каталогов. В статье рассматривается ряд важных нюансов, которые нужно учитывать для того, чтобы в случае инцидента, связанного со службой, ваш бизнес продолжал функционировать, и разъясняется, каких действий ожидать со стороны Майкрософт, если возник такой инцидент.

## <a name="transparency-during-service-incidents"></a>Прозрачность при инцидентах, связанных со службами

Являясь надежным партнером, Майкрософт создает высокоустойчивые облачные службы и использует упорядоченные процедуры для разрешения возможных связанных со службами инцидентов. Майкрософт осознает, как важно при возникновении инцидента, связанного со службой обеспечить клиентам**своевременную****целевую** информацию **с высоким уровнем доступности**.

## <a name="timely"></a>Своевременность
Администраторы Microsoft 365 получают оперативные уведомления из Майкрософт через панели мониторинга работоспособности служб (SHD) каждого клиента на портале администрирования Microsoft 365. Оперативная информация об инцидентах, связанных со службами, обычно предоставляется ежечасно. Если нам нужно изменить периодичность, об этом сообщается через панель мониторинга работоспособности службы.

## <a name="targeted"></a>Целевое назначение
Когда наши системы мониторинга обнаруживают какую-то проблему, мы чаще всего способны определить уязвимую клиентскую базу, в которую может входить как один клиент, так и целый регион или более, и направить этим клиентам необходимую информацию. Это помогает вам узнавать о том, о чем вам нужно знать для вашего бизнеса, и не отвлекаться на лишние уведомления, которые к вам не относятся. Например, если затронута определенная база данных почтовых ящиков, мы можем точно определить, пользователи каких клиентов имеют доступ к уязвимой инфраструктуре, и направить информацию именно им. Если нам не удается точно установить область влияния инцидента, мы информируем более широкий круг клиентов, которых этот инцидент может затронуть.

## <a name="highly-available"></a>Высокая доступность
В Майкрософт для клиентов работает несколько каналов с информацией о состоянии служб.

- Если Центр администрирования или панель мониторинга работоспособности службы Центра администрирования недоступны, проверить состояние службы можно через наш [резервный сайт](https://status.office365.com/).
- В учетной записи Twitter [@MSFT365Status](https://twitter.com/msft365status?lang=en) мы будем отвечать на отчеты о влиянии и публиковать оперативную информацию о событиях, затрагивающих работоспособность служб, с панели мониторинга.
- Благодаря приложению администрирования для администраторов клиента Microsoft 365 узнавать о состоянии службы Microsoft 365 для вашей организации можно в мобильном режиме. Администраторы клиента могут просматривать сведения о работоспособности службы и оперативную информацию о состоянии обслуживания с мобильного устройства. Дополнительные сведения см. в статье [Вопросы и ответы о приложении администрирования](https://docs.microsoft.com/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide).
- Доступ к служебным сообщениям обеспечивается через [API служебных сообщений Microsoft 365 ](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api)— так гораздо проще осуществлять мониторинг своей среды. Подключение к API позволяет вам получать актуальные данные о работоспособности служб и размещать информацию на внутренней панели мониторинга, сообщая об инцидентах пользователям своего предприятия. Информирование внутри организации может уменьшить количество обращений в вашу службу поддержки во время сбоя.
- Если возникают серьезные инциденты, Майкрософт публикует обзоры последствий инцидентов (PIR) в центре администрирования панели мониторинга работоспособности службы. Обзоры последствий инцидентов содержат основные сведения, которые помогают понять, что вызвало сбой. Обзор обычно состоит из следующих разделов:
    - влияние на пользователей;
    - область влияния;
    - дата и время начала и окончания инцидента;
    - основная причина;
    - предпринятые действия;
    - дальнейшие шаги.
- В Центре сообщений Microsoft 365 доступна дополнительная информация, например, уведомления о предстоящих изменениях, новых возможностях или запланированном обслуживании.
- Дополнительные сведения о разных каналах информирования и способах мониторинга работоспособности служб см. в [руководстве по работоспособности и непрерывности работы служб](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).
 
Доступ к облачным службам Microsoft 365 подразумевает партнерство между вашей организацией и корпорацией Майкрософт. В приведенной ниже таблице резюмируется баланс ответственности корпорации Майкрософт и клиента при возникновении инцидентов, связанных со службами, и при осуществлении обычных операций.

![баланс ответственности клиента и Майкрософт](../media/ebcm/responsibilities.png)

## <a name="your-environment---service-continuity"></a>Ваша среда — залог непрерывности работы служб
При составлении плана по обеспечению непрерывности бизнес-процессов нужно принимать во внимание события, которые могут повлиять на вашу организацию и на ее возможности для коммуникации в целом. По большому счету, на ваш бизнес могут влиять три фактора.

### <a name="people"></a>Люди
Имеет смысл рассмотреть вероятность наступления событий, которые могут оказать влияние на ваш персонал, например, стихийных бедствий или эпидемий. О таких вещах вспоминают редко, поскольку они вряд ли способны оказать широкомасштабное влияние на персонал, рассредоточенный в самых разных местах. Однако если большая часть персонала окажется не в сети, не остановится ли ваш бизнес? Как можно снизить риски в такой ситуации?

### <a name="location"></a>Расположение
Сотрудникам многих организаций нужно физически находиться в определенном месте или расположении в сети, чтобы подключаться к системам предприятия и облачным службам.  
В опубликованных корпорацией Майкрософт [принципах сетевого подключения](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)содержатся рекомендации для предприятий по настройке сетевого подключения к облачным ресурсам. Варианты оптимизации включают построение распределенных VPN в туннельном режиме для подключения непосредственно из сети пользователя, а не через туннель VPN.  Эти принципы подключения важны для обслуживания подключений с небольшой задержкой, а для устойчивости служб при общей совместной работе необходимы альтернативные способы подключения к корпоративным ресурсам.

### <a name="systems"></a>Системы
Многие решения для совместной работы зависят от таких систем, как, например, корпоративная глобальная сеть (WAN). Что произойдет с вашей организацией, если такая система станет недоступной?
Ниже изображены проблемы, влияние которых может проявиться по сразу нескольким направлениям. В таблице рядом приведены примеры, которые стоит рассмотреть.

![диаграмма-венна](../media/ebcm/venn-diagram.png)

При планировании обеспечения непрерывности бизнес-процессов необходимо учитывать все эти направления. Например, если вы хотите, чтобы пользователи работали в корпоративной сети, а на улице — снежная буря, как этим пользователям получить доступ к основным ресурсам? Если из-за погоды в офис добраться невозможно, а техническим специалистам службы поддержки нужно подключиться к корпоративной сети, есть ли в вашей организации политика, согласно которой у этих специалистов дома имеются персональные корпоративные ноутбуки?
