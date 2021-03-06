---
title: Таблица девицелогоневентс в схеме расширенного поискового окна
description: Сведения о событиях проверки подлинности и входа в таблицу Девицелогоневентс расширенной схемы подпоиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, логоневентс, Девицелогоневентс, проверка подлинности, вход, вход
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
ms.openlocfilehash: 67fa551fd7c2add815d5698a22b5eb3ae607f716
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048283"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Область применения:**
- Защита от угроз (Майкрософт)



`DeviceLogonEvents`Таблица в схеме [Advanced поиске](advanced-hunting-overview.md) содержит сведения о входах пользователей и других событиях проверки подлинности на устройствах. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ActionType` | string |Тип действия, вызвавшего событие |
| `AccountDomain` | string | Домен учетной записи |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `LogonType` | string | Тип сеанса входа в систему, в частности:<br><br> - **Интерактивный** пользователь физически взаимодействует с компьютером с помощью локальной клавиатуры и экрана<br><br> - **Удаленный интерактивный вход (RDP)** — пользователь взаимодействует с компьютером удаленно с помощью удаленного рабочего стола, служб терминалов, удаленного помощника или других клиентов RDP<br><br> - **Network** — сеанс, запущенный при доступе к компьютеру с помощью PsExec или при доступе к общим ресурсам на компьютере, например принтерам и общим папкам.<br><br> - **Пакетный** сеанс, инициированный запланированными задачами<br><br> - **Служба** — сеанс, инициированный службами при запуске<br> |
| `LogonId` | string | Идентификатор сеанса входа в систему. Этот идентификатор уникален для одного и того же компьютера только между перезапусками |
| `RemoteDeviceName` | string | Имя компьютера, который выполнил удаленную операцию на затронутом компьютере. В зависимости от события, о котором сообщается, это имя может быть полным доменным именем (FQDN), NetBIOS-именем или именем узла без сведений о домене. |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteIPType` | string | Тип IP-адреса, например общедоступный, частный, зарезервированный, петлевой, Teredo, Фауртосиксмаппинг и Broadcast |
| `RemotePort` | int | TCP-порт на удаленном устройстве, к которому было выполнено подключение |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `InitiatingProcessAccountDomain` | string | Домен учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountName` | string | Имя пользователя учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessAccountSid` | string | Идентификатор безопасности (SID) учетной записи, в которой выполнялся процесс, ответственный за событие. |
| `InitiatingProcessIntegrityLevel` | string | Уровень целостности процесса, который инициировал событие. Windows назначает уровни целостности процессам на основе определенных характеристик, например, если они были запущены при загрузке из Интернета. Эти уровни целостности влияют на разрешения для ресурсов |
| `InitiatingProcessTokenElevation` | string | Тип маркера, указывающий на присутствие или отсутствие повышения привилегий контроля доступа пользователей (UAC), примененного к процессу, который инициировал событие. |
| `InitiatingProcessSHA1` | string | SHA-1 процесса (файл изображения), который инициировал событие |
| `InitiatingProcessSHA256` | string | SHA-256 процесса (файл изображения), который инициировал событие. Это поле обычно не заполняется — используйте столбец SHA1, если он доступен |
| `InitiatingProcessMD5` | string | Хеш MD5 для процесса (файла изображения), который инициировал событие |
| `InitiatingProcessFileName` | string | Имя процесса, который инициировал событие |
| `InitiatingProcessId` | int | Идентификатор процесса (PID), который инициировал событие |
| `InitiatingProcessCommandLine` | string | Командная строка, используемая для запуска процесса, который инициировал событие |
| `InitiatingProcessCreationTime` | datetime | Дата и время начала процесса, инициировавшего событие |
| `InitiatingProcessFolderPath` | string | Папка, содержащая процесс (файл изображения), который инициировал событие |
| `InitiatingProcessParentId` | int | Идентификатор процесса (PID) родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentFileName` | string | Имя родительского процесса, который попытался выполнить процесс, ответственный за событие. |
| `InitiatingProcessParentCreationTime` | datetime | Дата и время начала родительского объекта процесса, ответственного за событие. |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `AppGuardContainerId` | string | Идентификатор виртуального контейнера, используемого Application Guard для изоляции активности браузера |
| `IsLocalAdmin` | boolean | Логический индикатор того, является ли пользователь локальным администратором на компьютере |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
