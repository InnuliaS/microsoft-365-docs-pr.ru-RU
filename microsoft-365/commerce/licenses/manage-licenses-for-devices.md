---
title: Управление лицензиями для устройств
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Узнайте, как назначать лицензии группам для использования с устройствами.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: ce3c8f7d669f2fe5d19c48d7a1fb1f224aaec7f4
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402874"
---
# <a name="manage-licenses-for-devices"></a>Управление лицензиями для устройств

Если у вас есть приложения Microsoft 365 для Enterprise (Device) или Microsoft 365 для образовательных учреждений (Device), вы можете назначить лицензии устройствам с помощью групп Azure AD. Когда устройство имеет лицензию, любой пользователь, использующий это устройство, может использовать приложения Microsoft 365 для предприятия (ранее именуемые Office 365 профессиональный плюс). Например, предположим, что у вас есть 20 ноутбуков и планшетов, используемых людьми в вашей организации. При назначении лицензии каждому устройству каждый пользователь, который входит в систему на одном из устройств, использует приложения Microsoft 365 для предприятий без необходимости в собственной лицензии.

> [!IMPORTANT]
> Лицензирование на основе устройств для приложений Microsoft 365 для предприятий доступно только в качестве лицензии на надстройку для некоторых коммерческих клиентов и клиентов для образования. Для коммерческих клиентов лицензия — это *приложения Microsoft 365 для Enterprise (Device)* , доступные только через корпоративное соглашение/Корпоративное соглашение. Для учебных заведений лицензия — это *приложения Microsoft 365 для образовательных учреждений (Device)* , доступные только через регистрацию для решений для образования (ИС). Для получения дополнительных сведений прочитайте запись в блоге о [доступности для образования](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Чтобы получить коммерческую доступность, обратитесь к представителю учетной записи Майкрософт.

Для начала создайте группу в центре администрирования Azure Active Directory, а затем назначьте устройства группе. Дополнительные сведения о лицензировании устройств, в том числе требования к устройствам, доступных типах групп и настройке приложений Microsoft 365 для предприятий для использования лицензирования устройств, представлены в разделе [Лицензирование на основе устройств для приложений microsoft 365 для предприятий](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Для выполнения задач, описанных в этой статье, необходимо быть глобальным администратором.

## <a name="assign-licenses-to-devices"></a>Назначение лицензий устройствам

При назначении лицензий группе вы назначаете лицензии всем устройствам в группе. Одну подписку можно назначить только одной группе.

1. В центре администрирования Microsoft 365 перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. На странице **лицензии** выберите **Microsoft 365 приложения для образовательных учреждений (устройство)** или **приложения Microsoft 365 для Enterprise (Device)**.
3. На следующей странице выберите подписку, а затем выберите **назначить лицензии**.
4. В области **назначить лицензии группе** введите имя группы, а затем выберите его из результатов, чтобы добавить его в список.
5. Нажмите кнопку **назначить**, а затем нажмите кнопку **Закрыть**.

## <a name="unassign-licenses-from-devices"></a>Отмена назначения лицензий для устройств

При отмене назначения лицензий группе вы удаляете лицензии со всех устройств в группе. Все приложения и связанные с ними данные доступны только для чтения.

1. В центре администрирования перейдите на страницу лицензии **выставления счетов**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. На странице **лицензии** выберите **Microsoft 365 приложения для образовательных учреждений (устройство)** или **приложения Microsoft 365 для Enterprise (Device)**.
3. На следующей странице выберите подписку, нажмите кнопку **Дополнительные действия**, а затем выберите пункт **Отменить назначение лицензий**.
4. В диалоговом окне **Отмена назначения лицензий** выберите **Отменить назначение**.