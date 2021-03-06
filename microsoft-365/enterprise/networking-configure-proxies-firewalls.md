---
title: Шаг 4. Настройка обхода трафика
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Настройте веб-браузеры и пограничные устройства для обхода трафика в доверенные места Microsoft 365.
ms.openlocfilehash: 3e0f9cec8d0d1385025289f1a07d2380be34f1a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631505"
---
# <a name="step-4-configure-traffic-bypass"></a>Шаг 4. Настройка обхода трафика

*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![Этап 1. Сеть](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Так как обычный интернет-трафик может быть опасным, в традиционных сетях организаций для обеспечения безопасности используются пограничные устройства, такие как прокси-серверы, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных.  Некоторые проблемы, связанные с устройствами сетевого перехвата, описаны в статье [Использование сторонних сетевых устройств или решений для трафика Microsoft 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Однако доменные имена DNS и IP-адреса, используемые облачными службами Microsoft 365, хорошо известны. Кроме того, сам трафик и службы надежно защищены. Поэтому вашим пограничным устройствам не нужно дублировать эту защиту. Промежуточные адреса и двойная обработка трафика Microsoft 365 могут значительно снизить производительность.

Первым шагом в устранении промежуточных адресов и двойной обработки является идентификация трафика Microsoft 365. Корпорация Майкрософт определила следующие типы доменных имен DNS и диапазонов IP-адресов (так называемые конечные точки):

- **Оптимизация.** Требуются для подключения ко всем службам Microsoft 365 и представляют более 75 % пропускной способности, подключений и данных Microsoft 365. Эти конечные точки представляют сценарии Microsoft 365, которые наиболее чувствительны к производительности, задержке в сети и доступности.
- **Разрешение.** Требуются для подключения к определенным службам и функциям Microsoft 365, но не так чувствительны к производительности и задержке в сети, как конечные точки категории "Оптимизация".
 - **По умолчанию.** Представляют службы и зависимости Microsoft 365, не требующие оптимизации. Конечные точки категории "По умолчанию" можно рассматривать как обычный интернет-трафик.

Доменные имена DNS и диапазоны IP-адресов можно найти на странице [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

Корпорация Майкрософт рекомендует:

- использовать скрипты автоматической настройки прокси-сервера (PAC) в интернет-браузерах локальных компьютеров для обхода прокси-серверов для доменных имен DNS облачных служб Microsoft 365. См. последний скрипт PAC для Microsoft 365 в статье [Скрипт Get-Pacfile в PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

- проанализировать пограничные устройства, чтобы определить двойную обработку, а затем настроить пересылку трафика в конечные точки "Оптимизировать" и "Разрешить" без обработки. Это известно как обход трафика. 

Ниже описаны рекомендации для вашей сетевой инфраструктуры.

![Рекомендации по оптимизации локального трафика](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

К пограничным устройствам относятся брандмауэры, устройства расшифровки и анализа SSL-трафика, устройства анализа пакетов и системы защиты от потери данных. Чтобы настроить или обновить конфигурацию пограничных устройств, можно использовать сценарий или вызов метода REST для применения структурированного списка конечных точек в веб-службе конечных точек Office 365. Дополнительные сведения см. в статье [Веб-служба IP-адресов и URL-адресов в Microsoft 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

Обратите внимание, что вы настраиваете обход только для трафика в конечные точки Microsoft 365 категорий "Оптимизировать" и "Разрешить". Остальной интернет-трафик будет передаваться через прокси и обрабатываться системами безопасности.

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a>Оптимизация трафика для удаленных сотрудников, использующих VPN-подключения

Подключения виртуальной частной сети (VPN) обычно используются удаленными сотрудниками для доступа к ресурсам в интрасети организации. Обычное VPN-подключение направляет ВЕСЬ трафик, включая интернет-трафик, в интрасеть организации. Интернет-трафик направляется на устройства периметра сети организации и устройства обработки пакетов. На этот трафик влияют задержки пути и обработки, которые могут значительно снизить скорость работы и повлиять на производительность ваших удаленных сотрудников. 

Раздельное туннелирование — это возможность VPN-подключения для направления определенного трафика через Интернет вместо его отправки через VPN-подключение к интрасети. Для оптимизации производительности удаленных сотрудников при работе с основными службами Microsoft 365, такими как Teams, SharePoint Online и Exchange Online, настройте раздельное туннелирование VPN-подключений для отправки трафика с целью оптимизации категории конечных точек прямо через Интернет. 

Подробные сведения см. в статье [Оптимизация подключения для удаленных пользователей с помощью раздельного VPN-туннелирования](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).

Чтобы протестировать, насколько близко вы находитесь к точке входа в глобальную сеть Майкрософт, а также к точке подключения сети организации к поставщику услуг интернета, воспользуйтесь [средством подключения сети Office 365](https://connectivity.office.com/).

Прежде чем перейти к следующему шагу, проверьте [условия](networking-exit-criteria.md#crit-networking-step4), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 5](../media/stepnumbers/Step5.png)|[Оптимизация производительности клиентов и служб](networking-optimize-tcp-performance.md) |



