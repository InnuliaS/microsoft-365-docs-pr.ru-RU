---
title: Назначение разрешений на расследования данных (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: В этой статье описывается, как настроить разрешения, необходимые для использования средства расследования данных в Microsoft 365.
ms.openlocfilehash: 855d288c373bd2525afa3b8b7a3bbd894c4683a2
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328148"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>Назначение разрешений на расследования данных (Предварительная версия)

Для получения доступа к анализу данных в центре соответствия требованиям Office 365 или Microsoft 365 необходимо быть участником группы ролей Data Инвестигатор. Чтобы добавить участников в группу ролей, необходимо быть членом группы ролей Управление организацией или назначить роль управления ролями в центре безопасности & соответствия требованиям. После того как пользователь станет участником группы ролей Инвестигатор данных, он может создавать, получать доступ и проводить расследования при расследовании данных, участником которых вы являетесь.

Чтобы назначить разрешения на расследования данных, выполните указанные ниже действия.

1. Войдите в [https://protection.office.com](https://protection.office.com) систему и войдите, используя учетные данные для учетной записи администратора в Организации.

2. В центре безопасности & соответствия требованиям нажмите кнопку **разрешения**.

3. Щелкните группу ролей **Инвестигатор данных** , а затем рядом с пунктом **элементы** в раскрывающейся странице щелкните **изменить**.

4. Нажмите кнопку **выбрать участников** , а затем нажмите кнопку **Добавить**. Выберите пользователей, которых вы хотите добавить в качестве обучений данных, и нажмите кнопку **Добавить**.

5. Добавив всех пользователей, нажмите кнопку **Готово** , а затем — кнопку **сохранить** , чтобы сохранить изменения в группе ролей.

> [!NOTE]
> Роль управления расследования данных, назначенная группе ролей Data Инвестигатор, предоставляет необходимые разрешения для доступа к средству расследования данных в центре соответствия требованиям Office 365 или Microsoft 365. По умолчанию эта роль не назначена группе ролей Управление организацией, что означает, что глобальные администраторы в организации могут не иметь доступа к средству расследования данных по умолчанию. Чтобы устранить эту проблему, можно добавить глобальных администраторов в группу ролей Data Инвестигатор или добавить роль управления расследования данных в группу ролей Управление организацией. Третий вариант — создать настраиваемую группу ролей и назначить роль управления расследованиями данных (и другие роли), а затем добавить соответствующие элементы. Для получения дополнительных сведений о группах ролей и ролях обратитесь [к разделу разрешения в центре безопасности Office 365 & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).