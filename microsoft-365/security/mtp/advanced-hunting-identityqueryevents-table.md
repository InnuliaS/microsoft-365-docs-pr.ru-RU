---
title: Таблица идентитикуеревентс в схеме расширенного поискового окна
description: Сведения о событиях запросов Active Directory в таблице Идентитикуеревентс расширенной схемы поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитикуеревентс, Azure AD, Active Directory, Azure ATP, удостоверения, запросы LDAP
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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899117"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityQueryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о запросах, выполненных для объектов Active Directory, таких как пользователи, группы, устройства и домены. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `Query` | string | Тип запроса: Куериграуп, Куерюсер или Енумератеусерс |
| `QueryObject` | string | Имя пользователя, группы, устройства, домена или любого другого типа сущностей, запрашиваемых |
| `Protocol` | string | Протокол, используемый при обмене данными |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `DeviceName` | string | Полное доменное имя (FQDN) конечной точки |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Location` | string | Город, страна или другое географическое расположение, связанное с событием |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
