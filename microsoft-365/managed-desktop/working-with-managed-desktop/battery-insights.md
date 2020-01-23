---
title: Получение сведений о батарее
description: ''
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b14ef9970aa709ad5e23fdae467992497a1331e8
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260161"
---
# <a name="battery-insights"></a>Получение сведений о батарее
Это представление предоставляет метрики энергопотребления, аккумулятора и использования приложений для настольных устройств, управляемых Майкрософт. В этих целях приложение считается "используемым", если оно работает и в фокусе.

Чтобы просмотреть данные об использовании, перейдите на вкладку **батарея** .

![Область батареи: прогнозируемый срок работы батареи на модель устройства в верхнем левом углу, в верхнем левом углу, в таблице "сведения" в нижней части. Ссылка на документацию в верхнем правом углу.](images/insights_battery.png)

## <a name="predicted-battery-life"></a>Прогнозируемый срок работы батареи

В области **предполагаемой длительности работы батареи** мы предоставляем прогноз для предполагаемого времени работы батарей для устройств, организованных по модели устройств.

> [!NOTE]
> Эти данные извлекаются из-за выборки энергопотребления, времени использования и мощности аккумулятора из случайного <em>выбора</em> устройств в управляемом развертывании настольных систем Майкрософт, которые также сообщают о данных.

Таблица предоставляет прогнозируемый срок работы батареи (в часах), среднее время работы от аккумулятора для тех же моделей в других управляемых настольных системах Майкрософт, а также количество устройств, сообщающих эти данные в вашей среде. Отсортируйте данные, выбрав заголовки столбцов.



## <a name="top-energy-consumers"></a>Топ потребителей

В области **Топ потребителей** вы найдете приложения в вашей среде, которые потребляют наибольшую энергию в милливатт-hours (МВХ). Отображаемые приложения относятся к конкретному устройству, которое выбирается в разделе **предполагаемая продолжительность работы батарей** слева. Например, чтобы просмотреть потребление для каждого приложения для устройств Microsoft Surface Book 2, выберите эту строку в области срок действия аккумулятора. Если вы не выбираете какую-либо модель, отображаются данные о потреблении для всех приложений, которые у нас есть данные для совместного использования.

 Для каждого приложения цветные сегменты показывают, как вы распределяете использование энергии приложением в следующих категориях:

- ЦП
- Display
- Сеть
- Другие

"Другое" может включать энергопотребление в различных источниках, таких как активность диска, использование мобильного широкополосного подключения и энергия, потеряющая доступ к внутренним сопротивлением. 

Приложения, отображаемые в * * потребителей высшего энергопотребления "

Вы можете отфильтровать это представление, чтобы отображались только фоновые приложения, фоновые приложения или и то, и другое, с помощью меню в правом верхнем углу. Приложения переднего плана — это те, у которых есть взаимодействие с пользователем за последние 28 дней, например, выбор чего-нибудь с помощью мыши.

## <a name="insights"></a>Аналитика

Область **Insights** показывает самых трех потребителей Energy Energy в категориях ЦП и сети. В сравнении со всеми развертываниями на настольных компьютерах Майкрософт используются эти элементы выше среднего. Ресурс Display не отображается, так как он сильно зависит от времени использования устройств и параметров яркости экрана. 

Для получения дополнительных сведений выберите вхождения в столбце **сведения** .

## <a name="battery-optimization"></a>Оптимизация заряда батареи

Windows 10 предлагает множество [параметров устройств](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) для улучшения энергопотребления и увеличения времени работы батарей для настольных устройств, управляемых Майкрософт. Некоторые из этих параметров могут привести к снижению числа других функций Windows, поэтому необходимо учитывать другие факторы, такие как роль устройства в Организации. Поддержка Windows поддерживает список этих [советов по экономии заряда](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Пользователи могут настраивать некоторые параметры самостоятельно, не требуя повышения прав или поддержки администратора. Для других параметров требуется поддержка ИТ ИТ ИТ администратора.