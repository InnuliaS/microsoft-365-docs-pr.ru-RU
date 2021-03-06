---
title: Расчет оценки соответствия требованиям Майкрософт (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Сведения о том, как оценка соответствия требованиям Майкрософт вычисляет персонализированный балл на основе действий, предпринимаемых для решения рисков и повышая уровень соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024679"
---
# <a name="compliance-score-preview-calculation"></a>Расчет оценки соответствия требованиям (Предварительная версия)

> [!IMPORTANT]
> Рекомендации рейтинга соответствия требованиям и диспетчера соответствия требованиям не должны рассматриваться в качестве гарантии соответствия требованиям. Вы можете оценивать и проверять эффективность клиентских элементов управления в соответствии с нормативной средой. В настоящее время эти службы находятся в предварительной версии и подчиняются условиям и условиям в [терминах веб-служб](https://go.microsoft.com/fwlink/?linkid=2108910). Кроме того [, вы также найдете рекомендации по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-compliance-score-works"></a>Принцип действия оценки соответствия требованиям

На панели мониторинга оценки соответствия отображается показатель, который измеряет выполнение действий по улучшению в элементах управления. Каждое действие влияет на вашу оценку в зависимости от возможных рисков. Ваш рейтинг поможет определить, какое действие необходимо уделить, чтобы улучшить общую оценку соответствия требованиям.

Отображаемые значения оценки соответствия требованиям для элемента управления *полностью* применяются к общему показателю на уровне прохода или отказа. Элемент управления реализован и проходит последующий тест оценки. 

Точки добавляются к показателю соответствия требованиям, если элемент управления содержит:

- **Состояние реализации** равно **реализованной** или **альтернативной реализации**, а также
- **Результат проверки** равен **пройденному**.

Оценка элемента управления это сумма баллов, полученных в результате выполнения действий по улучшению. Сумма контрольных показателей — это показатель оценки. **Сумма результатов оценки — это общий показатель соответствия требованиям.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Первоначальный балл, основанный на базовом показателе защиты данных Microsoft 365
  
Оценка соответствия дает вам начальный балл, основанный на базовом уровне защиты данных (Майкрософт) 365. Этот базовый план представляет собой набор элементов управления, включающих ключевые нормативные требования и стандарты для защиты данных и общего управления данными. Этот базовый план рисует элементы в основном с помощью NIST CSF (Национальный институт стандартов и технологий Циберсекурити Framework) и ISO (Международная организация по стандартизации), а также из FedRAMP (Федеральный показатель рисков и программного обеспечения управления авторизацией) и GDPR (общее количество требований к защите данных Европейского союза).

Базовая оценка защиты данных (предоставляется по умолчанию всем организациям) используется для расчета начальной оценки перед настройкой любых других оценок. При первом посещении рейтинг соответствия уже собирает сигналы из решений Microsoft 365. Вы увидите, как выполняется Организация относительно основных стандартов защиты данных и нормативных требований, а также ознакомьтесь с предлагаемыми действиями по улучшению.

Так как каждая организация обладает особыми потребностями, для оценки соответствия требованиям необходимо настроить собственные оценки и управлять ими, чтобы свести к минимуму риски и уменьшить риски.

## <a name="how-compliance-score-continuously-assesses-controls"></a>Как показатель соответствия постоянно оценивает элементы управления

Оценка соответствия автоматически сканирует среду Microsoft 365 и определяет параметры системы непрерывно и автоматически обновляет состояние технического контроля. Показатель безопасности — это основной механизм, который выполняет мониторинг.

Состояние элемента управления обновляется на панели мониторинга оценки соответствия требованиям каждые 24 часа. Когда вы следуйте рекомендациям по внедрению элемента управления, вы увидите состояние элемента управления, обновленного на следующий день.

Например, если включить многофакторную проверку подлинности (MFA) на портале Azure AD, рейтинг соответствия будет определять параметр и отражается в сведениях о решении на доступ к управлению. И наоборот, если вы не включили MFA, то есть флаги оценки соответствия требованиям, которые необходимо выполнить.

При общедоступной предварительной версии постоянная оценка доступна для части элементов управления, но не для всех.

#### <a name="learn-more"></a>Подробнее
[Узнайте о безопасном показателе и принципах его работы](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Типы и точки действий

Оценка соответствия отслеживает два типа действий: действия, которыми вы управляете, и действия, которыми управляет Майкрософт. Оба типа действий имеют точки, которые подсчитаны к общему показателю при завершении:

1. **Ваши баллы** влияют на оценку соответствия требованиям, основанным на элементах управления, управляемых вашей организацией.
2. **Управляемые точки Майкрософт** вносят вклад в оценку соответствия требованиям, основанным на действиях, управляемых корпорацией Майкрософт в качестве поставщика облачных служб.

Действиям назначаются значения оценки, зависящие от того, являются ли они обязательными или непревентивными, а также являются ли они превентивными, обнаруживающее или корректирующими.

### <a name="mandatory-and-discretionary-actions"></a>Обязательные и избирательные действия

 - **Обязательные действия** не могут быть обходиться намеренно или случайно. Пример — это централизованно управляемая политика паролей, устанавливающая требования к длине, сложности и сроку действия пароля. Для доступа к системе пользователи должны выполнить эти требования.
  
 - Для выполнения **избирательных действий** пользователям необходимо иметь представление о политике и действовать соответствующим образом. Например, политика, требующая, чтобы пользователи блокировали свой компьютер при их выходе, это неизбирательное действие, так как оно зависит от пользователя.
  
### <a name="preventative-detective-and-corrective-actions"></a>Меры по превентивной, обнаруживающее и корректирующим действиям
  
 - Действия, связанные с **превентивной превентивной** адресацией. Например, защита информации на REST с помощью шифрования является предупредительным действием при атаках и нарушениях безопасности. Разделение обязанностей является превентивным действием по управлению конфликтами интересов и защите от мошенничества.
  
 - **Действия обнаруживающее** активно контролируют системы на обнаружение нерегулярных условий или поведений, представляющих риск, или которые можно использовать для обнаружения вторжений или нарушений. Примеры включают аудит системного доступа и привилегированные административные действия. Аудит соответствия нормативным требованиям — это тип действия обнаруживающее, используемого для обнаружения проблем с процессами.
  
- **Действия по исправлению** попытаются сохранить неблагоприятные последствия инцидента безопасности как минимум, предпринять корректирующие меры, чтобы уменьшить немедленный эффект, и при необходимости отменить повреждение. Ответ на инцидент конфиденциальности — это корректирующее действие по ограничению повреждений и восстановления систем в работоспособном состоянии после нарушения безопасности.
  
Каждое действие имеет значение, назначенное в показателе соответствия требованиям, в зависимости от того, какой риск он представляет:

|**Тип**|**Назначенная Оценка**|
|:-----|:-----|
| Обязательная превентивная | 27 |
| Неизбирательные дискреционные меры | 9  |
| Обнаруживающее является обязательным | 3  |
| Дискреционный обнаруживающее | 1  |
| Корректирующая обязательная | 3  |
| Корректирующая избирательность | 1  |
  
![Значения точек контроля для оценки соответствия требованиям](../media/compliance-score-controls-scoring.png "Значения точек контроля для оценки соответствия требованиям")