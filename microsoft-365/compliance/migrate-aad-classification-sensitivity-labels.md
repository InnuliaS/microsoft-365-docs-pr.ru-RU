---
title: Метки классификации и конфиденциальности Azure Active Directory для групп Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: В этой статье обсуждаются классические метки классификации и чувствительностьности Azure Active Directory.
ms.openlocfilehash: f11473653884392048d5f9a84f8e284dba5f6f27
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755393"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Метки классификации и конфиденциальности Azure Active Directory для групп Microsoft 365

В этой статье обсуждаются классические метки классификации и чувствительностьности Azure Active Directory.

[Эти службы](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)поддерживают метки конфиденциальности.

Полные сведения о метках конфиденциальности можно узнать в [статье сведения о метках чувствительности](sensitivity-labels.md).

Чтобы узнать больше о метках конфиденциальности и их поведении для сайтов и групп Microsoft 365, ознакомьтесь со статьей [Использование меток конфиденциальности для защиты содержимого в Microsoft Teams, microsoft 365 группы и сайтов SharePoint](sensitivity-labels-teams-groups-sites.md).

В следующих сценариях приведены рекомендации по переходу с классической классификации AAD на метки конфиденциальности.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Сценарий 1: клиент никогда не использовал классические классификации AAD или метки чувствительности для документов и сообщений электронной почты

- Администратор клиента включает метки конфиденциальности для групп, устанавливая флаг клиента "Енаблемиплабелс" в true с помощью командлета AAD PowerShell.
- Администратор клиента создает метки конфиденциальности в [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com).
    - Администратор клиента может выбирать действия, связанные с файлами и электронной почтой, такие как шифрование и водяные знаки.
    - Администратор клиента может выбрать для меток конфиденциальности группы Microsoft 365 и действия, связанные с сайтами SharePoint Online.
- Администратор клиента публикует политику.
- В **совместимых рабочих нагрузках** отображаются метки конфиденциальности. Используйте метки конфиденциальности для создания групп. Совместимыми рабочими нагрузками являются службы, поддерживающие метки конфиденциальности.
- **Несовместимые рабочие нагрузки** — это службы, которые пока не поддерживают метки конфиденциальности. Группы можно создавать, но они не могут быть связаны с меткой чувствительности с помощью несовместимых рабочих нагрузок. Чтобы связать эти группы с метками конфиденциальности, администраторы клиента могут запускать командлеты PowerShell.

Таблица 1. Поведение совместимых и несовместимых рабочих нагрузок — создание, изменение и удаление групп

|Workload|Какой список меток пользователи видят в окне группы?|Создание новой группы |Изменить группу |Delete group |
|:-------|:-------|:--------|:--------|:--------|   
|Совместима   |Метки конфиденциальности. |Поведение не изменяется. |Поведение не изменяется. |Поведение не изменяется. |
|Не совместимо |Метки чувствительности не отображаются. |Пользователь может создать группу без выбора метки конфиденциальности. <br><br> Обратите внимание, что администратор может запускать командлеты для применения меток конфиденциальности в фоновом режиме. |**Вариант 1**: метка чувствительности не была выбрана ранее. Пользователь может редактировать группу.<br><br> **Вариант 2**: метка чувствительности, ранее примененная в фоновом режиме с помощью командлета. Пользователь может успешно редактировать группу, исключая тот случай, когда пользователь выбирает недопустимую комбинацию параметра конфиденциальности по отношению к метке. |Поведение не изменяется.|

> [!NOTE]
> В случае с клиентом Outlook для настольных ПК (Win 32) после того, как администратор включит метки конфиденциальности на своем клиенте и пользователь находится в более ранней версии клиента Outlook для настольных ПК (Win 32):
> - Пользователи видят метки конфиденциальности в более ранней версии клиента Outlook для настольных компьютеров.
> - Тем не менее, когда пользователь редактирует группу и сохраняет группу с меткой конфиденциальности, выбранная настройка конфиденциальности переопределяется параметром конфиденциальности примененной метки чувствительности.
> Пользователям рекомендуется выполнить обновление предыдущей версии клиента Outlook до новой версии.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Сценарий 2: клиент уже использует классическое [классификацию](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization) AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Случай а: клиент никогда не использовал метки чувствительности для документов и сообщений электронной почты

1. В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)мы рекомендуем создавать метки чувствительности с одинаковым именем в соответствии с существующими классическими метками Azure AD.
2. Используйте командлет PowerShell, чтобы применить эти метки конфиденциальности к существующим группам Microsoft 365 и сайтам SharePoint с помощью сопоставления имен.
3. Администратор может удалить классические метки Azure AD:
    - Совместимые рабочие нагрузки отображают эти метки конфиденциальности и группы, созданные ими.
    - Несовместимость рабочих нагрузок при создании групп без присоединения к ним метки чувствительности.
4. Администраторы могут запускать командлеты PowerShell, чтобы применить метки конфиденциальности к этим группам без меток.
    - Кроме того, администратор может сохранить обычные метки Azure AD:
        - Совместимые рабочие нагрузки отображают эти метки конфиденциальности, а группы создаются с ними. Совместимыми рабочими нагрузками являются службы, поддерживающие метки конфиденциальности.
        - Несовместимые рабочие нагрузки работают при создании групп и отображают классические метки Azure AD. Эти обычные метки Azure AD присоединяются к этим группам, созданным с помощью несовместимых рабочих нагрузок.
5. Мы настоятельно рекомендуем администраторам запускать командлеты PowerShell для применения меток конфиденциальности к этим группам со классическими метками Azure AD.

Таблица 2. Поведение совместимых и несовместимых рабочих нагрузок — создание, изменение и удаление групп

|Workload|Какой список меток пользователи видят в окне группы?|Создание новой группы |Изменить группу |Delete group |
|:-------|:-------|:--------|:--------|:--------|   
|Совместима   |Метки конфиденциальности. |Поведение не изменяется. |Поведение не изменяется. |Поведение не изменяется. |
|Не совместимо |Старые классические метки AAD. |Пользователь может создать группу с выбранной классической меткой Azure AD. <br><br>Обратите внимание, что администратор может запускать командлеты для применения меток конфиденциальности в фоновом режиме. |**Вариант 1**: метка чувствительности не была выбрана ранее. Пользователь может редактировать группу.<br><br> **Случай 2**: предварительно выбранные метки AAD Classic. Пользователь может редактировать группу.<br><br> **Case 3**: метка чувствительности, ранее примененная в фоновом режиме с помощью командлета. Пользователь должен иметь возможность редактировать группу, исключая один случай, когда пользователь выбирает недопустимую комбинацию параметра конфиденциальности по отношению к метке. |Пользователь может удалить группу. |

> [!NOTE]
> В случае с клиентом Outlook для настольных ПК (Win 32) после того, как администратор включит метки конфиденциальности на своем клиенте и пользователь находится в более ранней версии клиента Outlook для настольных ПК (Win 32):
> - Пользователи видят метки конфиденциальности в более ранней версии клиента Outlook для настольных компьютеров.
> - Тем не менее, когда пользователь редактирует группу и сохраняет группу с меткой конфиденциальности, выбранная настройка конфиденциальности переопределяется параметром конфиденциальности примененной метки чувствительности.
> Пользователям рекомендуется выполнить обновление предыдущей версии клиента Outlook до новой версии.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Случай б. клиенты используют метки чувствительности для документов и сообщений электронной почты

1. После того как администратор включит функцию меток конфиденциальности на клиенте, установив для флага клиента "Енаблемиплабелс" значение true, отображаются метки "документ" и "чувствительность к электронной почте" в диалоговых окнах "создать" и "создать" и "Изменить".
2. Администратор может использовать одни и те же метки документов и меток электронной почты для применения конфиденциальности и доступа внешних пользователей к группе/сайту или команде, указывая соответствующие параметры группы:
    1. В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)выберите вкладку **сайты и группы** .
    2. Редактирование документа или метки чувствительности электронной почты.

## <a name="sample-script"></a>Образец сценария

Пример сценария для переноса групп с классическими метками AAD на метки конфиденциальности приведен в разделе [Классическая классификация групп Azure AD](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

