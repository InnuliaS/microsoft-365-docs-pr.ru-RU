---
title: Шаг 1. Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Убедитесь, что используемая вами конфигурация соответствует критериям Microsoft 365 корпоративный для сетевой инфраструктуры.
ms.openlocfilehash: 6d9133fa6f3c993efe88ea53b412b9a272c1b98b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631493"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a>Шаг 1. Условия, при выполнении которых можно считать сетевую инфраструктуру настроенной

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Убедитесь, что сетевая инфраструктура соответствует указанным ниже обязательным условиям и что рассмотрены необязательные условия.

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Обязательное: ваша сеть готова к Microsoft 365 корпоративный

- Пропускная способность интернет-канала в ваших офисах является достаточной для трафика Microsoft 365, в том числе установки и обновлений Office 365, Microsoft Intune и Windows 10 Корпоративная.
- В целом ваша сеть соответствует [эталонной архитектуре Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).
- Выполнено пилотное развертывание и тестирование изменений в вашей сети, и они соответствуют вашим требованиям к задержке трафика.

Чтобы выполнить это требование, см. [шаг 1](networking-provide-bandwidth-cloud-services.md).

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Обязательное: локальные офисы имеют локальные подключения к Интернету и разрешение имен

Для каждого локального офиса вы настроили доступ к Интернету через локального поставщика услуг Интернета, чьи DNS-серверы используют локальный общедоступный IP-адрес, который определяет их местоположение в Интернете. Это обеспечивает максимальную производительность для пользователей, работающих с облачными службами Microsoft 365.

Если вы не используете локального поставщика услуг Интернета для каждого филиала, это может снизить производительность, так как в этом случае сетевой трафик проходит через основной канал организации либо запросы к данным обрабатываются удаленными серверами переднего плана.

### <a name="how-to-test"></a>Проверка
С помощью соответствующего средства или веб-сайта на устройстве в этом офисе определите IP-адрес, используемый прокси-сервером. Например, можно использовать веб-страницу [для определения своего IP-адреса](https://www.whatismypublicip.com/). Этот общедоступный IP-адрес, назначенный вашим поставщиком услуг Интернета, должен быть локальным в географическом смысле. Его не должно быть в диапазоне общедоступных IP-адресов центрального офиса или облачного поставщика безопасности сети.

Чтобы выполнить это требование, см. [этап 2](networking-dns-resolution-same-location.md).

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a>Необязательное: вы удалили ненужные развороты пакетов

Вы изучили развороты пакетов и определили их влияние на производительность во всех своих офисах. Вы удалили ненужные развороты пакетов или вместе со сторонним поставщиком реализовали оптимальный обмен трафиком Microsoft 365 для их сети.

Чтобы выполнить это требование, см. [шаг 3](networking-avoid-network-hairpins.md) (при необходимости).


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Необязательное: вы настроили обход трафика в интернет-браузерах и на пограничных устройствах

Вы развернули последние файлы PAC в своих локальных интернет-браузерах, чтобы трафик на доменные имена DNS Microsoft 365 обходил прокси-серверы.

Вы настроили обход трафика или минимальную обработку трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить" в брандмауэрах, а также на устройствах расшифровки и анализа SSL-трафика и устройствах анализа пакетов.


### <a name="how-to-test"></a>Проверка

С помощью средств ведения журналов на пограничных устройствах убедитесь, что трафик, направляемый в назначения Microsoft 365, не проверяется, не шифруется и не задерживается каким-либо другим способом.

Чтобы выполнить это требование, см. [шаг 4](networking-configure-proxies-firewalls.md) (при необходимости).


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-microsoft-365-applications-are-configured-for-optimal-performance"></a>Требование выполнять не обязательно: ваши клиенты и приложения Microsoft 365 настроены для оптимальной производительности

Вы оптимизировали параметры протокола TCP на своих клиентских устройствах, а также для служб Exchange Online, Skype для бизнеса Online, SharePoint Online и Project Online.

Чтобы выполнить это требование, см. [шаг 5](networking-optimize-tcp-performance.md) (при необходимости).

## <a name="results-and-next-steps"></a>Результаты и дальнейшие действия

Пользователи интрасети теперь готовы использовать облачные службы Microsoft 365 с помощью эффективного сетевого пути в Интернет.

|||
|:-------|:-----|
|![Этап 2. Удостоверения](../media/deploy-foundation-infrastructure/identity_icon-small.png)| Если вы выполняете этапы полного развертывания Microsoft 365 корпоративный, следующий этап —[удостоверения](identity-infrastructure.md). |
