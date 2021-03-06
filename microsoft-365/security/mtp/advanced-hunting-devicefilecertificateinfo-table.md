---
title: Таблица девицефилецертификатеинфо в схеме расширенного поискового окна
description: Сведения о подписывании файлов в таблице Девицефилецертификатеинфо расширенной схемы поискового подсистемы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, цифровая подпись, сертификат, подписывание файлов, Девицефилецертификатеинфо
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
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899319"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Область применения:**
- Защита от угроз (Майкрософт)

`DeviceFileCertificateInfo`Таблица в схеме [Advanced поиске](advanced-hunting-overview.md) содержит сведения о сертификатах подписи файлов. В этой таблице используются данные, полученные из действий по проверке сертификатов, которые регулярно выполняются для файлов в конечных точках.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `IsSigned` | boolean | Указывает, подписан ли файл |
| `SignatureType` | string | Указывает, были ли сведения о подписи прочитаны как внедренный контент в самом файле или прочитаны из внешнего файла каталога |
| `Signer` | string | Сведения о подписавшем файла |
| `SignerHash` | string | Уникальное значение хэша, идентифицирующее подписывающий |
| `Issuer` | string | Сведения о выдающем центре сертификации (ЦС) |
| `IssuerHash` | string | Уникальное хэш-значение, идентифицирующее выставляющий центр сертификации (CA) |
| `CertificateSerialNumber` | string | Идентификатор сертификата, который является уникальным для выдающего центра сертификации (CA). |
| `CrlDistributionPointUrls` | string |  Массив JSON список URL-адресов сетевых ресурсов, содержащих сертификаты и списки отзыва сертификатов (CRL) |
| `CertificateCreationTime` | datetime | Дата и время создания сертификата |
| `CertificateExpirationTime` | datetime | Дата и время истечения срока действия сертификата |
| `CertificateCountersignatureTime` | datetime | Дата и время, когда сертификат был каунтерсигнед |
| `IsTrusted` | boolean | Указывает, является ли файл доверенным на основе результатов функции Винверифитруст, который проверяет наличие неизвестных сведений о корневых сертификатах, недопустимые подписи, отозванные сертификаты и другие сомнительные атрибуты |
| `IsRootSignerMicrosoft` | boolean | Указывает, является ли подписывающий корневой сертификат корпорацией Майкрософт |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться вместе со столбцами DeviceName и timestamp. | 

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
