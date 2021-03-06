---
title: BitLocker для шифрования
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Сведения о том, как Office 365 использует шифрование BitLocker, что снижает вероятность кражи данных из-за потери или кражи компьютеров и дисков.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033627"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker и распределенный диспетчер ключей (DKM) для шифрования

Microsoft Servers использует BitLocker для шифрования дисков, содержащих данные о клиентах, в оставшейся части уровня громкости. Шифрование BitLocker — это функция защиты данных, встроенная в Windows. BitLocker — это одна из технологий, используемых для защиты от угроз, в случае возникновения промежутков в других процессах или элементах управления (например, управления доступом или повторном использовании оборудования), которые могут привести к тому, что кто-то получает физический доступ к дискам с данными клиента. В этом случае BitLocker исключает возможность кражи или разглашения данных из-за потери, кражи или неправильного списания компьютеров и дисков.

BitLocker развернут с помощью стандарта расширенного шифрования AES (AES) 256-bit на дисках, содержащих данные клиентов в Exchange Online, SharePoint Online и Skype для бизнеса. Секторы диска шифруются с помощью полного ключа шифрования тома (ФВЕК), который шифруется с помощью главного ключа тома (ВМК), который, в свою очередь, связан с доверенным платформенным модулем на сервере. ВМК напрямую защищает ФВЕК, поэтому защита ВМК становится критической. На следующем рисунке показан пример цепочки защиты ключей BitLocker для данного сервера (в данном случае с использованием сервера Exchange Online).

В следующей таблице описывается цепь защиты ключей BitLocker для данного сервера (в данном случае это сервер Exchange Online).

| ПРЕДОХРАНИТЕЛЬ КЛЮЧА | ДЕТАЛИЗАЦИИ | СПОСОБ СОЗДАНИЯ? | ГДЕ ОН ХРАНИТСЯ? | ЗАЩИТИТЬ |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 — разрядный внешний ключ | На сервер | API BitLocker | Доверенный платформенный модуль или безопасный секрет | Защищенное хранилище или управление доступом |
|  |  |  | Реестр сервера почтовых ящиков | Шифрование доверенного платформенного модуля |
| Числовой пароль 48 цифры | На диск | API BitLocker | Active Directory | Защищенное хранилище или управление доступом |
| Сертификат X. 509 как агент восстановления данных (DRA), также называемый предохранителем открытых ключей | Среда (например, клиент Exchange Online) | Центр сертификации Майкрософт | Система построения | Ни один пользователь не имеет полного пароля для закрытого ключа. Пароль находится в разделе физическая защита. |


Управление ключами BitLocker включает управление ключами восстановления, которые используются для разблокировки и восстановления зашифрованных дисков в центре обработки данных Майкрософт. Microsoft 365 хранит основные ключи в защищенном общем ресурсе, доступном только для тех пользователей, которые были настроены на экран и утверждены. Учетные данные ключей хранятся в защищенном репозитории для данных управления доступом (вызов "Secret Store"), который требует высокого уровня разрешений на повышение прав и управления для доступа с помощью средства повышения уровня доступа по требованию.

BitLocker поддерживает ключи, которые делятся на две категории управления:

- Ключи, управляемые BitLocker, которые обычно кратковременно зависят от времени существования экземпляра операционной системы, установленного на сервере или на заданный диск. Эти ключи удаляются и сбрасываются во время переустановки сервера или форматирования диска.

- Ключи восстановления BitLocker, управляемые вне BitLocker, но используемые для расшифровки диска. BitLocker использует ключи восстановления для сценария, в котором переустанавливается операционная система, а зашифрованные диски данных уже существуют. Ключи восстановления также используются зондами мониторинга доступности управляемого контента в Exchange Online, где респонденту может потребоваться разблокировать диск.

Тома, защищенные с помощью BitLocker, шифруются с помощью полного ключа шифрования тома, который, в свою очередь, шифруется с помощью главного ключа тома. BitLocker использует алгоритмы, совместимые с FIPS, чтобы убедиться, что ключи шифрования никогда не хранятся и не отправляются по каналу в Clear. Реализация Microsoft 365 для защиты данных клиентов по умолчанию не отличается от реализации BitLocker по умолчанию.
