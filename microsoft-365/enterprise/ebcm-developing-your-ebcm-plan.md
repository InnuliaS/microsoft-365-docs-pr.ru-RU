---
title: Рекомендации по разработке плана управления непрерывностью бизнес-процессов в вашей компании
author: chrfox
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
description: Факторы, которые следует учитывать при разработке плана непрерывности бизнес-процессов, совместимого с облачными службами.
ms.openlocfilehash: 4a133c65f6a5a2de44e871995886a01c2ce8e9a9
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122339"
---
# <a name="developing-your-continuity-plan"></a>Разработка плана непрерывности

В этой статье приводятся инструкции по разработке плана непрерывности бизнес-процессов с учетом зависимостей Microsoft 365. Здесь мы рекомендуем методы анализа ваших бизнес-функций и определения тех, которые зависят от служб Microsoft 365. Вы проводите этот анализ, учитывая, что будут сбои в работе служб и вам нужно подготовиться к таким возможным событиям.

В широком смысле слова планирование непрерывности бизнес-процессов включает четыре аспекта: оценку, планирование, проверку возможностей и взаимодействие и координацию.

## <a name="assesment"></a>Оценка
Сначала необходимо определить бизнес-функции в организации, а также поддерживающие их службы и процессы. Это включает анализ последствий для деятельности, где оценивается степень важности каждой бизнес-функции и определяются те процессы и службы, от которых зависит каждая из функций. Ниже приведен пример таблицы, который поможет вам приступить к оценке.

**Пример оценки последствий для деятельности (ОПД)**

Это документ ОПД для `name of the service, system, process, or function`

|Поля ОПД|Описание|
|---------|---------|
|Тип ОПД|`is it a business process or technology, service or system?`|
|Название ОПД|`name of the service/system/function/process`|
|описание службы|`give a full description of the service, process, or function`|
|функция в работе компании|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|финансовый год:|`the current fiscal year, re-evaluate these on a regular basis`|
|степень важности|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|бизнес-подразделение|`name of the business unit that owns this business function`|
|бизнес-процесс (служба, функция)|`the name of the process, service, or feature`|
|старший руководитель рабочей группы |`the name and contact information of the senior leader of the business group that owns this business process`|
|Установлены ли для технологии **внутренние** соглашения об уровне обслуживания (SLA) или об уровнях операционной поддержки (OLA)?|`please explain in as much detail as possible`|
|Установлены ли для технологии **внешние** соглашения об уровне обслуживания (SLA) или об уровнях операционной поддержки (OLA)?|`please explain in as much detail as possible`|
|Имеет ли технология общепризнанные исполнительные полномочия, определяющие конкретный процесс SLA? Если да, подробно опишите.|`details here`|
|Приведет ли утеря или раскрытие данных, связанных с этими службами, к серьезным последствиям? Если да, подробно опишите.|`details here`|
|Существует ли у службы обходной путь или готовый к использованию аналог для некоторых или всех основных функций и возможностей? Если да, подробно опишите.|`details here`|
|Занимается ли служба обработкой, хранением или передачей данных клиента (PII — данные, идентифицирующие личность)? Если да, подробно опишите.|`details here`|
|состояние ОПД|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|дата завершения|`the date this BIA was completed`|
|ОПД провел|`name of the person or group who is responsible for developing and maintaining this BIA`|
|ОПД утвердил|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|участники|`optional list of the people who helped develop this BIA and their contact information`|
|место утверждения ОПД|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Планирование

Далее рассмотрите бизнес-процессы, чтобы понять, где существуют каскадные отношения зависимостей. Исходя из результата, можно задать приоритеты и сформировать стратегии отказоустойчивости, а также стандартные рабочие процедуры, поддерживающие стратегии.

В этом определении соответствий вам поможет [карта служб Microsoft](https://docs.microsoft.com/ru-RU/azure/azure-monitor/insights/service-map). Карта служб Microsoft автоматически обнаруживает компоненты приложений в системах Windows и Linux и сопоставляет все зависимости TCP, определяет подключения и удаленные сторонние системы, от которых зависит приложение. Кроме того, она сопоставляет зависимости с традиционно темными зонами вашей сети, такими как Active Directory.

Ниже приведен образец анализа зависимостей (АЗ), с которого можно начать. В ходе анализа зависимостей (АЗ) вы будете определять и проверять зависимости процесса. Убедитесь в том, что охвачены коллеги, поставщики, клиенты, партнеры и устройства. Данные этого анализа будут использоваться для выявления несоответствий между требованиями для восстановления процесса и возможностями восстановления поддерживаемых зависимостей.


|поле|описание|
|---------|---------|
|тип процесса|         |
|анализ провел|         |
|анализ выполнил|         |
|дата выполнения|         |
|участники|         |
  
## <a name="capability-validation"></a>Проверка возможностей

После того как вы описали бизнес-процессы и сопоставили их отношения с другими процессами и технологиями, необходимо создать сценарии проверки для всех процессов. В принципе, определите, как вы будете проверять свои планы непрерывности бизнес-процессов. Возможно, вы обнаружите, что некоторые из них важнее других, и вам нужно будет сделать их приоритетными.
Не забывайте, что после утверждения плана важно проводить с сотрудниками регулярные тренинги по реагированию на инциденты и по мерам обеспечения непрерывности. Следует использовать обзоры последствий инцидента для улучшения ваших стратегий устойчивости, добавляя сведения после каждой проверки или теста.

## <a name="incident-coordination-and-communication"></a>Координация и коммуникации при инциденте

Во время сбоя в работе службы обычные каналы коммуникаций могут быть повреждены или ослаблены, поэтому вам следует заранее подготовить альтернативные варианты, чтобы во время инцидента ваша организация могла оставаться на связи. Крайне важно, чтобы каналы коммуникаций были установлены еще до сбоя, проверены на предмет безопасности и соответствия требованиям, а пользователи научились их использовать. Переход из известного состояния в другое известное состояние при сбое гораздо предпочтительнее для пользователей, которые во время кризиса ищут ситуативные, неизвестные решения.

В корпорации Майкрософт рабочая группа каждой службы установила внутренние альтернативные каналы коммуникаций, чтобы мы могли действовать согласованно, когда наши стандартные каналы коммуникаций недоступны. К ним относятся резервные каналы телефонии и аудиоконференций, группы Yammer, группы Teams, внутренние панели мониторинга работоспособности службы и внутреннее программное обеспечение для управления инцидентами.

В ходе анализа последствий для деятельности и анализа зависимостей вы будете сопоставлять критически важные процессы и технологии или службы, от которых они зависят. Обратите особое внимание на коммуникации во время этого этапа планирования и продумайте альтернативы. Ниже приведены некоторые примеры.

- Если ваш приоритетный способ информирования пользователей и заинтересованных лиц — электронная почта, а служба электронной почты вышла из строя или недоступна, вы можете использовать в качестве резервных другие службы, такие как Microsoft Teams, Yammer или сторонние службы. Здесь важно определить это заранее и обучить пользователей правильным действиям. Сообщения в Yammer будут бесполезны, если никто не знает об их существовании или никто не добавил их в закладки.  
- Если ваши внутренние процессы управления инцидентами используют голосовые сообщения для координации решений, создайте альтернативное решение для телефонии, которое будет использоваться в кризисной ситуации. Это решение необязательно должно быть полным аналогом основной службы, но следует обеспечить минимальный уровень совместной работы, чтобы координировать работу групп в сфере бесперебойной работы и управления инцидентами. Кроме того, вы можете попросить пользователей внести свои номера мобильных телефонов в глобальный список адресов, чтобы создать дополнительный уровень коммуникаций в чрезвычайных ситуациях.
- Возможно, вам понадобится создать настраиваемую панель мониторинга работоспособности службы или подобную площадку, где можно видеть обновления состояния во время инцидента. Заблаговременное обучение пользователей, куда обращаться за нужными сведениями, поможет сократить количество лишних обращений в службу поддержки и даст пользователям уверенность в том, что проблема решается быстро и эффективно. Используйте API каналов связи со службой Office 365, чтобы связать его со службой Microsoft 365 и еще больше повысить уровень видимости.  
- Важно, чтобы все хорошо знали, где находятся ваши планы непрерывности бизнес-процессов и стандартные рабочие процедуры. Рекомендуем хранить копии критически важных документов в сети и вне сети, например настроить в SharePoint Online или OneDrive для бизнеса автоматическую синхронизацию с локальными устройствами. Возможно, вам также понадобится сохранить распечатанные копии. В чрезвычайной ситуации ими смогут воспользоваться Сервисный центр / Сетевой операционный центр и другие подобные рабочие группы, которые имеют решающее значение для восстановления.

## <a name="know-your-external-points-of-integration"></a>Узнайте о своих внешних точках интеграции

Независимо от бизнес-модели, у каждой компании есть точки интеграции с клиентами, партнерами и поставщиками. Производственно-сбытовая цепочка, имеющая коммерческую ценность, строится на интеграции с внешними объектами. Для налаживания непрерывности бизнес-процессов в случае нарушения работы службы необходимо учесть и защитить каждую точку интеграции.  
При анализе производственно-сбытовой цепочки внешние коммуникации следует рассматривать так же, как и внутренние. Ваши клиенты полагаются на ваши серверы Exchange Online как на единственный способ связи с вами? Вы установили альтернативные способы связи и сообщили о них своим поставщикам, на тот случай, если это влияет на время приведения в рабочее состояние? Ниже приведен образец таблицы, в которой показано, как выстроить свой процесс рассуждений.

|имя внешнего объекта|сценарий угрожающего инцидента|встроенные службы Microsoft 365|альтернативные решения|
|---------|---------|---------|---------|
|`vendor name`|поток обработки почты|Exchange Online — единственное средство связи с Contoso|настройка внешних каналов Microsoft Teams или сторонней программы для совместной работы          |
|`service supplier name`|чат|Microsoft Teams|сторонний сервис обмена мгновенными сообщениями|
|`partner name`|голос|Microsoft Teams|мобильная или открытая ТСОП      |
|`supplier name`|общий доступ к файлам|Внешний общий доступ к сайтам SharePoint и OneDrive|общий доступ к сторонним файлам         |