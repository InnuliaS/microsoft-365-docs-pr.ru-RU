---
title: Таблица DeviceTvmSecureConfigurationAssessmentKB в схеме расширенного поиска угроз
description: Узнайте о различных настройках безопасности, оцененных в Контроле угроз и уязвимостей, в таблице DeviceTvmSecureConfigurationAssessmentKB схемы расширенного поиска угроз.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, Настройка безопасности, МИТРЕ ATT&а Framework, база знаний, KB, Девицетвмсекуреконфигуратионассессменткб
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
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327999"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="ca908-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="ca908-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="ca908-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ca908-105">**Applies to:**</span></span>
- <span data-ttu-id="ca908-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ca908-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ca908-107">В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="ca908-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ca908-108">Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="ca908-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="ca908-109">Используйте этот справочник для создания запросов, возвращающих данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="ca908-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ca908-110">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ca908-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ca908-111">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ca908-111">Column name</span></span> | <span data-ttu-id="ca908-112">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ca908-112">Data type</span></span> | <span data-ttu-id="ca908-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ca908-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="ca908-114">string</span><span class="sxs-lookup"><span data-stu-id="ca908-114">string</span></span> | <span data-ttu-id="ca908-115">Уникальный идентификатор определенной настройки</span><span class="sxs-lookup"><span data-stu-id="ca908-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ca908-116">string</span><span class="sxs-lookup"><span data-stu-id="ca908-116">string</span></span> | <span data-ttu-id="ca908-117">Оценка влияния настройки на общую оценку конфигурации (1–10)</span><span class="sxs-lookup"><span data-stu-id="ca908-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="ca908-118">string</span><span class="sxs-lookup"><span data-stu-id="ca908-118">string</span></span> | <span data-ttu-id="ca908-119">Отображение названия настройки</span><span class="sxs-lookup"><span data-stu-id="ca908-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="ca908-120">string</span><span class="sxs-lookup"><span data-stu-id="ca908-120">string</span></span> | <span data-ttu-id="ca908-121">Описание ошибки настройки</span><span class="sxs-lookup"><span data-stu-id="ca908-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="ca908-122">string</span><span class="sxs-lookup"><span data-stu-id="ca908-122">string</span></span> | <span data-ttu-id="ca908-123">Описание связанного риска</span><span class="sxs-lookup"><span data-stu-id="ca908-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ca908-124">string</span><span class="sxs-lookup"><span data-stu-id="ca908-124">string</span></span> | <span data-ttu-id="ca908-125">Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности</span><span class="sxs-lookup"><span data-stu-id="ca908-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="ca908-126">string</span><span class="sxs-lookup"><span data-stu-id="ca908-126">string</span></span> |<span data-ttu-id="ca908-127">Подкатегория или подгруппа, к которой относится настройка.</span><span class="sxs-lookup"><span data-stu-id="ca908-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ca908-128">Во многих случаях здесь описываются конкретные возможности или функции.</span><span class="sxs-lookup"><span data-stu-id="ca908-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="ca908-129">string</span><span class="sxs-lookup"><span data-stu-id="ca908-129">string</span></span> | <span data-ttu-id="ca908-130">Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке</span><span class="sxs-lookup"><span data-stu-id="ca908-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="ca908-131">string</span><span class="sxs-lookup"><span data-stu-id="ca908-131">string</span></span> | <span data-ttu-id="ca908-132">Список приемов платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="ca908-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="ca908-133">string</span><span class="sxs-lookup"><span data-stu-id="ca908-133">string</span></span> | <span data-ttu-id="ca908-134">Список тактик платформы Mitre ATT&CK, относящихся к настройке</span><span class="sxs-lookup"><span data-stu-id="ca908-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ca908-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ca908-135">Related topics</span></span>

- [<span data-ttu-id="ca908-136">Заблаговременный поиск угроз</span><span class="sxs-lookup"><span data-stu-id="ca908-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ca908-137">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ca908-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ca908-138">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ca908-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ca908-139">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="ca908-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ca908-140">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ca908-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ca908-141">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ca908-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ca908-142">Обзор контроля угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="ca908-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)