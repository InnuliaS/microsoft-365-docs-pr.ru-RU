---
title: Включение Защиты от угроз (Майкрософт) в Центре безопасности Microsoft 365
description: Узнайте, как включить Защиту от угроз (Майкрософт) и начать интеграцию инцидентов безопасности и реагирования на них.
keywords: начало работы, MTP, Защита от угроз (Майкрософт), Microsoft 365, безопасность, расположение данных
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808454"
---
# <a name="turn-on-microsoft-threat-protection"></a>Включение Защиты от угроз (Майкрософт)

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Защита от угроз (Майкрософт) объединяет процесс реагирования на инциденты, интегрируя основные возможности Advanced Threat Protection (ATP) в Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

## <a name="check-your-eligibility"></a>Проверка правомочности
Защиту от угроз (Майкрософт) могут использовать клиенты, у которых есть лицензия Microsoft 365 E5 или аналогичная лицензия.  Дополнительные сведения см. в статье [Требования к лицензированию](prerequisites.md#licensing-requirements).

## <a name="start-using-the-service"></a>Начало работы со службой
Включение службы Защиты от угроз (Майкрософт) объединяет данные из различных интегрированных служб. Данные будут обрабатываться и храниться централизованно, чтобы предоставить новые рекомендации и сделать возможными централизованные рабочие процессы реагирования.

До включения службы параметры **Инциденты** и **Центр уведомлений** не отображаются в меню Центра безопасности Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).

![Изображение меню Центра безопасности Microsoft 365 без функций Защиты от угроз (Майкрософт)](../images/mtp-off.png)
*Центр безопасности Microsoft 365 с отключенной службой Защиты от угроз (Майкрософт)*

Чтобы включить службу Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**. Для выполнения этой задачи вам нужны права глобального администратора или администратора безопасности в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Если для вашей организации подготовлена служба ATP в Microsoft Defender, данные будут храниться и обрабатываться в том же расположении центра обработки данных, которое вы выбрали для [данных ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). В противном случае вам будет предложено выбрать новое расположение центра обработки данных для Защиты от угроз (Майкрософт). Согласие необходимо дать до предоставления службам общего доступа к данным и их агрегации.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы
После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)
- Возможности [расширенного поиска](advanced-hunting-overview.md) на существующей странице **Поиск**

![Изображение меню Центра безопасности Microsoft 365 с функциями Защиты от угроз (Майкрософт)](../images/mtp-on.png)
*Центр безопасности Microsoft 365 с возможностью управления инцидентами и другими функциями Защиты от угроз (Майкрософт)*

### <a name="getting-azure-atp-data"></a>Получение данных Azure ATP
Чтобы предоставить доступ к данным Azure ATP службе Защиты от угроз (Майкрософт), убедитесь в том, что включена интеграция Microsoft Cloud App Security с Azure ATP. [Подробнее об этой интеграции](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Выключение Защиты от угроз (Майкрософт)
Чтобы прекратить использование службы Защиты от угроз (Майкрософт), в Центре безопасности Microsoft 365 выберите **Параметры** > **Защита от угроз (Майкрософт)** > **Согласиться или отказаться**. Снимите флажок **Включение Защиты от угроз (Майкрософт)** и сохраните изменения.

Данные будут удалены без возможности восстановления, и соответствующие функции будут удалены из Центра безопасности Microsoft 365.

## <a name="get-assistance"></a>Получение помощи

Сотрудники Майкрософт могут помочь в подготовке или отмене подготовки службы и связанных ресурсов в клиенте. Чтобы получить помощь, [обратитесь в службу поддержки Premier](https://go.microsoft.com/fwlink/?LinkID=733758).

## <a name="related-topics"></a>См. также

- [Обзор Защиты от угроз (Майкрософт)](microsoft-threat-protection.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Обзор ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Office 365 ATP](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Обзор Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Хранение данных в службе ATP в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)