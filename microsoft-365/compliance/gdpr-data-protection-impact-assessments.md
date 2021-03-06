---
title: Оценка влияния на защиту данных
description: Эти документы предоставляют управляющим данными информацию. которая поможет им определить, требуется ли оценка DPIA, и если да, то какие сведения необходимо в нее включить.
keywords: Оценка влияния на защиту данных, DPIA, Dynamics 365, профессиональные службы Майкрософт, Microsoft 365, документация по Microsoft 365, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 21bda86075b2ab1e542e482e8c0a1edee640035e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558079"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>Оценка влияния на защиту данных в рамках GDPR

Общий регламент по защите данных (GDPR) вводит новые правила для организаций, предоставляющих товары и услуги жителям Европейского союза (ЕС) или занимающихся сбором и анализом данных резидентов ЕС, независимо от того, где находитесь вы или ваше предприятие. Дополнительные сведения можно найти в разделе [Сводка по GDPR](gdpr.md). В этом документе вы можете получить сведения относительно оценки влияния на защиту данных (DPIA) в рамках GDPR при использовании продуктов и служб Майкрософт.

## <a name="terminology"></a>Термины

Полезные определения терминов GDPR, используемых в этом документе:

- *Управляющий данными (управляющий)* — юридическое лицо, орган государственной власти, агентство или другое лицо, которое отдельно от других или вместе с ними определяет цели и средства обработки персональных данных.  
- *Персональные данные* и *субъект данных* — все сведения, относящиеся к определенному или определяемому физическому лицу ("субъект данных"). Определяемым физическим лицом считается лицо, которого можно прямо или косвенно определить.  
- *Обработчик* — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое обрабатывает персональные данные от лица управляющего.  
- *Данные клиента* — это данные, которые создаются и хранятся в ходе повседневной работы компании.

## <a name="what-is-a-dpia"></a>Что такое DPIA?

Общий регламент по защите данных (GDPR) требует, чтобы управляющие подготовили оценку влияния на защиту данных (DPIA) для операций, которые "с высокой вероятностью могут повлечь значительный риск для прав и свобод физических лиц". Продукты и службы Майкрософт не имеют характеристик, требующих DPIA. Однако это продукты и службы с широкими возможностями настройки, поэтому иногда конфигурация Майкрософт может требовать DPIA. Корпорация Майкрософт не контролирует такие данные и практически не имеет соответствующих аналитических сведений. Управляющим данными необходимо определить, какое использование данных является надлежащим.

## <a name="dpia-in-action"></a>Выполнение DPIA

Руководство по DPIA применимо к Office 365, Azure, Dynamics 365, службе поддержки и профессиональному обслуживанию Майкрософт. В этом руководстве рассматриваются следующие вопросы:

**Когда требуется DPIA?**

Рассматривая вопрос о необходимости DPIA, следует учесть перечисленные ниже факторы риска. Другие факторы потенциального риска и дополнительные сведения см. в части 1 каждой инструкции.  

- Систематическая расширенная оценка данных на основе автоматизированной обработки.  
- Масштабная обработка определенных категорий данных (данные, используемые для уникальной идентификации физического лица) или персональных данных о судимостях и преступлениях.
- Масштабное систематическое отслеживание общедоступной области.

В GDPR поясняется: "Обработка персональных данных не считается масштабной, если это обработка персональных данных пациентов или клиентов отдельным врачом, другим специалистом в области здравоохранения или юристом. В таких случаях оценка влияния на защиту данных не должна быть обязательной".

**Что требуется для выполнения DPIA?**

DPIA предоставляет подробные сведения о планируемой обработке, которые описаны в части 2 руководства. Эти сведения включают следующие данные.

- Оценка необходимости и пропорциональности операций обработки данных по отношению к целям DPIA.  
- Оценка рисков для прав и свобод физических лиц.
- Предполагаемые меры по устранению рисков, в том числе меры предосторожности, меры безопасности и механизмы для обеспечения защиты персональных данных и соблюдения требований GDPR.
- Цели обработки  
- Категории обрабатываемых персональных данных  
- Хранение данных  
- Размещение и передача персональных данных  
- Предоставление данных сторонним субобработчикам  
- Предоставление данных независимым третьим сторонам  
- Права субъектов данных

## <a name="additional-considerations"></a>Дополнительные рекомендации

Конкретные сведения, которые могут быть важны для вашей реализации Майкрософт, см. ниже.

- [Office 365](gdpr-dpia-office365.md). Этот документ применим к приложениям и службам Office 365, включая, в том числе, Exchange Online, SharePoint Online, Yammer, Skype для бизнеса и Power BI. Дополнительные сведения см. в таблицах [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) и [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia).  
- [Azure](gdpr-dpia-azure.md). Клиентам рекомендуется сотрудничать с уполномоченными по защите личных данных и юрисконсультами, чтобы определить необходимость выполнения DPIA и ее содержимое в связи с использованием Microsoft Azure.  
- [Dynamics 365](gdpr-dpia-dynamics.md). Содержимое DPIA может отличаться в зависимости от того, какие инструменты Dynamics 365 вы используете. Конкретные сведения см. в [части 2 "Содержимое DPIA"](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).
- [Служба поддержки и профессионального обслуживания Майкрософт](gdpr-dpia-prof-services.md). Профессиональные услуги не предполагают определенной стандартной или автоматизированной обработки данных и не предназначены для обработки особых категорий данных или выполнения задач, которые упрощают или требуют наблюдения за общедоступными данными. Дополнительные сведения см. в разделе [Часть 1. Определение необходимости выполнения DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed). Управляющие данными должны рассматривать описанные выше элементы DPIA, а также любые другие важные факторы в контексте конкретной реализации и использования профессиональных услуг. Сведения о профессиональных услугах см. в разделе [Часть 2. Содержимое DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).

## <a name="learn-more"></a>Подробнее

- [Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
