---
title: Таблица алертинфо в схеме расширенного поискового окна
description: Сведения о событиях создания оповещений в таблице Алертинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, Алертинфо, предупреждение, серьезность, категория, МИТРЕ, ATT&а,, мдатп, МКАС, Майкрософт для пакета ATP 365, и Azure ATP.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899021"
---
# <a name="alertinfo"></a>AlertInfo

**Область применения:**
- Защита от угроз (Майкрософт)



`AlertInfo`В таблице в [расширенной](advanced-hunting-overview.md) схеме Поиск содержатся сведения об ОПОВЕЩЕНИЯХ из пакета ATP для защитника майкрософт, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AlertId` | string | Уникальный идентификатор оповещения |
| `Title` | string | Название оповещения |
| `Category` | string | Тип индикатора угрозы или нарушения, определенного оповещением |
| `Severity` | string | Указывает возможное воздействие (высокое, среднее или низкое) индикатора угрозы или нарушения, определенного оповещением |
| `ServiceSource` | string | Продукт или услуга, которые предоставили информацию оповещений |
| `DetectionSource` | string | Технология обнаружения или датчик, идентифицирующий существенный компонент или активность |
| `AttackTechniques` | string | МИТРЕ ATT&а, связанные с действием, которое инициировало оповещение |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
