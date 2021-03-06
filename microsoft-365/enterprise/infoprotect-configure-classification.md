---
title: Шаг 2. Настройка классификации для среды
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как настроить различные способы классификации данных в организации.
ms.openlocfilehash: 57d4c692630826f371ea825d86fc64b959b71df2
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005814"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Шаг 2. Настройка классификации для среды

*Этот этап не является обязательным. Он применяется к планам E3 и E5 Microsoft 365 корпоративный.*

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

На этом шаге вы проведете работу с юридическим отделом и отделом соответствия требованиям и определите схему классификации данных в своей организации.

## <a name="microsoft-365-classification-types"></a>Типы классификации Microsoft 365

В Microsoft 365 имеются четыре указанных ниже типа классификации.

- Типы конфиденциальной информации
- Метки хранения
- Метки конфиденциальности
- Метки и защита Azure Information Protection

### <a name="sensitive-information-types"></a>Типы конфиденциальной информации

Типы конфиденциальной информации для Microsoft 365 определяют порядок распознавания определенных типов информации, в частности, конфиденциальных данных сотрудников или клиентов, таких как номера паспортов и кредитных карт. Типы конфиденциальной информации могут использоваться для поиска конфиденциальных данных и их защиты с помощью правил и политик защиты от потери данных (DLP). За дополнительной информацией обратитесь к статье [о составе политики DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains). 

Типы конфиденциальной информации особенно полезны для обеспечения соответствия требованиям и соблюдения нормативных актов, таких как Общий регламент по защите данных (GDPR).

### <a name="retention-labels"></a>Метки хранения

Одна из составляющих стратегии управления данными должна определять, как долго следует хранить документы определенных типов или с определенным содержимым в соответствии с правилами организации и региональными нормативными требованиями. Например документы некоторых типов должны храниться в течение установленного времени, а затем удаляться, а другие документы хранятся бессрочно.

Для документов, хранящихся в Microsoft 365, вы определяете метки хранения и применяете их к документам и данным, хранящимся в электронной почте Exchange, SharePoint Online, OneDrive для бизнеса и в сообщениях чата и каналов Teams. 

При использовании меток хранения необходимо задать метку для каждой категории файлов, к которым должна применяться политика хранения. В метке хранения можно указать следующие данные:

- Набор дескрипторов для файлов (например, для разных отделов, категорий файлов или нормативов).
- Параметры хранения файлов, к которым приложены метки хранения, такие как сроки хранения и действия по истечении срока.

Также можно автоматически применять метки хранения к файлам, настроив сайт SharePoint Online так, чтобы ко всем новым документам на сайте применялась стандартная метка хранения. 

За дополнительной информацией обращайтесь к [обзору меток хранения](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Метки конфиденциальности

Одна из мер защиты и поддержания безопасности для документов определенного типа или с определенным содержимым состоит в применении к ним особой метки, которая говорит о необходимости применения дополнительной защиты. С помощью меток конфиденциальности в Microsoft 365 можно:

- Применять параметры защиты, такие как шифрование, разрешения или подложка.
- С помощью защиты конечных точек в Windows Information Protection (WIP) предотвращать копирование такого содержимого в сторонние приложения, такие как Twitter или Gmail, или копирование на съемные носители, такие как USB-накопитель.
- С помощью Microsoft Cloud App Security (CAS) защищать содержимое в сторонних приложениях и службах. 
- Классифицировать содержимое, не используя параметры защиты.

При использовании меток конфиденциальности следует задать метку для каждого уровня защиты и безопасности информации. Например можно создать три метки конфиденциальности:

- Базовый уровень
- Конфиденциальный
- Строго контролируемый

Если вы храните файлы со строго регулируемыми данными на сайте SharePoint Online и хотите, чтобы у этих файлов вне сайта были такие же разрешения, как на сайте, требуется создать дополнительные метки конфиденциальности, разрешения которых совпадают с разрешениями сайта.

За дополнительными сведениями обратитесь к [обзору меток конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Метки и защита Azure Information Protection

Метки Azure Information Protection можно использовать для классификации, а при необходимости и для защиты документов и сообщений электронной почты в организации. Эти метки можно применять к документам, которые хранятся за пределами Microsoft 365. Они могут применяться автоматически (администраторами, которые определяют правила и условия), вручную (пользователями) или с сочетанием этих вариантов, когда пользователи получают рекомендации.

Чтобы спланировать и развернуть метки Azure Information Protection, выполните указанные ниже действия.

1. Изучите [требования для Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Выполните [стратегический план развертывания для классификации, маркирования и защиты](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Дополнительные сведения см. в [документации по библиотеке Azure Information Protection](https://docs.microsoft.com/information-protection/).

Существующие метки Azure Information Protection без проблем работают с метками конфиденциальности. Например, можно одновременно использовать существующие метки Azure Information Protection и метки, которые применяются к документам и электронной почте.

Если имеются как метки конфиденциальности, так и метки Azure Information Protection, следует [перенести метки Azure Information Protection на метки конфиденциальности](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).

## <a name="example-classification-for-gdpr"></a>Пример: классификация для GDPR

Пример схемы классификации, включающей личные данные для GDPR, см. в статье [Разработка архитектуры схемы классификации для персональных данных](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

## <a name="take-it-for-a-test-drive"></a>Тестовый запуск

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Руководство по лаборатории тестирования: классификация данных](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step2), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 3](../media/stepnumbers/Step3.png)|[Настройка усиленной защиты для Office 365](infoprotect-configure-increased-security-office-365.md)|

