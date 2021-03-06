---
title: Таблица идентитинфо в схеме расширенного поискового окна
description: Сведения об учетных записях пользователей в таблице Идентитинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Аккаунтинфо, Идентитинфо, учетная запись
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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898961"
---
# <a name="identityinfo"></a>IdentityInfo

**Область применения:**
- Защита от угроз (Майкрософт)

`IdentityInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения об учетных записях пользователей, полученных из различных служб, в том числе Azure Active Directory. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!NOTE]
>Эта таблица была переименована из `AccountInfo` . Во время переименования все сохраненные на портале запросы автоматически обновляются. Проверьте сохраненные в других запросах.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `AccountUpn` | string | Имя участника-пользователя (UPN) учетной записи |
| `OnPremSid` | string | Локальный идентификатор безопасности (SID) учетной записи |
| `CloudSid` | string | Идентификатор безопасности облака учетной записи |
| `GivenName` | string | Заданное имя или имя пользователя учетной записи |
| `Surname` | string | Фамилия, имя семейства или фамилия пользователя учетной записи |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `Department` | string | Имя отдела, к которому относится пользователь учетной записи |
| `JobTitle` | string | Должность пользователя учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `EmailAddress` | string | SMTP-адрес учетной записи |
| `SipProxyAddress` | string | Протокол передачи голоса по протоколу IP (VOIP) учетной записи |
| `City` | string | Город, в котором находится пользователь учетной записи |
| `Country` | string | Страна или регион, где находится пользователь учетной записи |
| `IsAccountEnabled` | boolean | Указывает, включена ли учетная запись |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
