---
title: Отмена назначения лицензий пользователям
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Сведения о том, как отменить назначение лицензий для учетных записей пользователей.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015939"
---
# <a name="unassign-licenses-from-users"></a>Отмена назначения лицензий пользователям

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Вы можете отменить назначение лицензий пользователям на странице " **Активные пользователи** " или на странице " **лицензии** ". Используемый способ зависит от того, хотите ли вы отменить назначение лицензий на продукты определенным пользователям или отменить назначение пользователей для конкретного продукта.

::: moniker-end

## <a name="before-you-begin"></a>Подготовка

- Чтобы отменить назначение лицензий, вы должны быть глобальной, лицензией и администратором пользователей. Дополнительные сведения см. в статье [Роли администраторов в Microsoft 365](../add-users/about-admin-roles.md).
- Вы можете [удалить лицензии из учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).
- Вы также можете [удалить учетные записи пользователей](../add-users/delete-a-user.md) , которым назначена лицензия, чтобы сделать их лицензия доступной другим пользователям. При удалении учетной записи пользователя ее лицензия немедленно становится доступной для назначения другому пользователю.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Отмена назначения лицензий с помощью страницы "лицензии"

При отмене назначения лицензий с помощью страницы " **лицензии** " вы отдаете лицензии для определенного продукта не более чем 20 пользователям.

1. В центре администрирования перейдите на страницу лицензии **выставления счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. Выберите продукт, для которого требуется отменить назначение лицензий.
3. Выберите пользователей, для которых требуется отменить назначение лицензий.
4. Выберите отменить **Назначение лицензий**.
5. В поле отменить **Назначение лицензий** выберите отменить **назначение**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Отмена назначения лицензий с помощью страницы "активные пользователи"

При отмене назначения лицензий с помощью страницы " **Активные пользователи** " вы отдаете им лицензии на продукты.

### <a name="unassign-licenses-from-one-user"></a>Отмена назначения лицензий для одного пользователя
  
1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.
2. Выберите строку пользователя, для которого требуется отменить назначение лицензии.
3. В области справа выберите **Лицензии и приложения**.
4. Разверните раздел **лицензии** , снимите флажки для лицензий, которые требуется отменить, а затем нажмите кнопку **сохранить изменения**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Отмена назначения лицензий для одного пользователя

1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.
2. Выберите пользователя, для которого требуется отменить назначение лицензии.
3. В правой части в строке **лицензии на продукты** выберите **изменить**.
4. В области **лицензии на продукты** установите переключатель в положение **выключена** для лицензии, которую вы хотите отменить для пользователя. Например, если вы отключили лицензию Office 365 корпоративный E3, она отбудет отнести эту лицензию и все службы в рамках этой лицензии для этого пользователя.
5. В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Отмена назначения лицензий для одного пользователя

1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.
2. Выберите пользователя, для которого требуется отменить назначение лицензии.
3. В правой части в строке **лицензии на продукты** выберите **изменить**.
4. В области **лицензии на продукты** установите переключатель в положение **выключена** для лицензии, которую вы хотите отменить для пользователя. Например, если вы отключили лицензию Office 365 корпоративный E3, она отбудет отнести эту лицензию и все службы в рамках этой лицензии для этого пользователя.
5. В нижней части области **Лицензии на продукты** последовательно нажмите **Сохранить** \> **Закрыть** \> **Закрыть**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Отмена назначения лицензий для нескольких пользователей

1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">активные пользователи</a> страницы.
2. Выберите кружки рядом с именами пользователей, для которых требуется отменить назначение лицензий.
3. Нажмите вверху **Дополнительные параметры (...)** и выберите **Управление лицензиями на продукты**.
4. В области **Управление лицензиями на продукты** выберите **Заменить имеющиеся назначения лицензий на продукты** \> **Далее**.
5. В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **закрытие**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Отмена назначения лицензий для нескольких пользователей

1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">активные пользователи</a> страницы.
2. Установите флажки рядом с именами пользователей, для которых требуется отменить назначение всех лицензий.
3. В области **Массовые действия** выберите **Изменить лицензии продуктов**.
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **Закрыть** \> **окно**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Отмена назначения лицензий для нескольких пользователей
  
1. В центре администрирования перейдите в раздел **Пользователи ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">активные пользователи</a> страницы.
2. Установите флажки рядом с именами пользователей, для которых требуется отменить назначение всех лицензий.
3. В области **Массовые действия** выберите **Изменить лицензии продуктов**.
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
5. В нижней части области **заменить существующие продукты** установите флажок **удалить все лицензии продуктов из выбранных пользователей** , а затем нажмите кнопку **заменить** \> **Закрыть** \> **окно**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Что происходит с данными пользователя при удалении лицензии?

- При удалении лицензии у пользователя данные, связанные с этой учетной записью, хранятся в течение 30 дней. По истечении 30-дневного льготного периода данные удаляются и не могут быть восстановлены.
- Файлы, сохраненные в OneDrive для бизнеса, не удаляются, пока пользователь не будет удален из центра администрирования Microsoft 365 или удален с помощью синхронизации Active Directory. Дополнительные сведения см. в разделе " [Хранение и удаление OneDrive](https://docs.microsoft.com/onedrive/retention-and-deletion)".
- После удаления лицензии почтовый ящик пользователя больше не может быть доступен для поиска с помощью средства обнаружения электронных данных, такого как поиск контента или Расширенное обнаружение электронных данных. Дополнительные сведения см. в разделе "поиск отключенных или отключенных почтовых ящиков" в разделе [Поиск содержимого в Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Если у вас есть Корпоративная подписка, например Office 365 корпоративный E3, Exchange Online позволяет сохранить данные почтового ящика удаленной учетной записи пользователя с помощью [неактивных почтовых ящиков](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Дополнительные сведения см в статье [Создание неактивных почтовых ящиков и управление ими в Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Сведения о том, как заблокировать доступ пользователя к данным Microsoft 365 после удаления лицензии и получения доступа к данным, приведенные в статье [Удаление бывшего сотрудника](../add-users/remove-former-employee.md).
- Если удалить лицензию пользователя, но у нее все еще установлены приложения Office, они увидят [нелицензированные продукты и ошибки активации в Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) при использовании приложений Office.

## <a name="next-steps"></a>Дальнейшие действия

Если вы не собираетесь [переназначить неиспользуемые лицензии другим пользователям](../../managed-desktop/get-started/assign-licenses.md), рекомендуем [Удалить лицензии из подписки](../../commerce/licenses/buy-licenses.md) , чтобы вы не оплачиваете больше лицензий, чем требуется.

## <a name="related-content"></a>Связанные материалы

[Удаление лицензий из подписки](../../commerce/licenses/remove-licenses-from-subscription.md) (статья) \
[Назначение лицензий пользователям](assign-licenses-to-users.md) (статья) \
[Общие сведения о подписках и лицензиях в Microsoft 365 для бизнеса](../../commerce/licenses/subscriptions-and-licenses.md) (статья)