---
title: Функция Филепрофиле () в расширенном поиске для защиты от угроз Майкрософт
description: Узнайте, как использовать Филепрофиле (), чтобы получить сведения о файлах в расширенных запросах поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, Филепрофиле, профиле файла, функция, обогащение
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
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515942"
---
# <a name="fileprofile"></a>Филепрофиле ()

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`FileProfile()`Функция — это функция обогащения в [расширенном поиске](advanced-hunting-overview.md) , которая добавляет следующие данные в файлы, найденные в запросе.

| Column | Тип данных | Описание |
|------------|-------------|-------------|
| ХЭШЕМ | string | SHA-1 файла, к которому было применено записанное действие |
| SHA256 | string | SHA – 256 файла, к которому было применено записанное действие |
| MD5 | string | Хэш MD5 файла, к которому было применено записанное действие |
| FileSize | int | Размер файла в байтах |
| глобалпреваленце | int | Количество экземпляров сущности, которые корпорация Майкрософт соблюдает глобально |
| глобалфирстсин | datetime | Дата и время, когда объект впервые наблюдался корпорацией Майкрософт глобально |
| глобалластсин | datetime | Дата и время последней первоначальной отстановки объекта корпорацией Майкрософт |
| Подписывающего лица | string | Сведения о подписавшем файла |
| Издатель | string | Сведения о выдающем центре сертификации (ЦС) |
| сигнерхаш | string | Уникальное значение хэша, идентифицирующее подписывающий |
| исцертификатевалид | boolean | Является ли сертификат, используемый для подписи файла, допустимым |
| исрутсигнермикрософт | boolean | Указывает, является ли подписывающий корневой сертификат корпорацией Майкрософт |
| Исполняемый файл | boolean | Является ли файл переносимым исполняемым файлом (PE) |
| среатнаме | string | Имя для обнаружения вредоносных программ или других обнаруженных угроз |
| Publisher | string | Имя Организации, опубликовавшего файл |
| софтваренаме | string | Название программного продукта |

## <a name="syntax"></a>Синтаксис

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Аргументы

- **x** — столбец идентификатора файла, который будет использоваться: `SHA1` , `SHA256` , `InitiatingProcessSHA1` или `InitiatingProcessSHA256` ; функция использует, если она не `SHA1` указана
- **y** — ограничено числом записей до обогащения, 1-1000; функция использует 100, если она не указана

## <a name="examples"></a>Примеры

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project только для столбца SHA1 и обогащения

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Улучшение первых 500 записей и списков файлов с минимальным дообладанием

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)