---
title: Добавление пользователей и назначение лицензий
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Узнайте, как добавлять пользователей и назначать лицензии в Microsoft 365 одновременно.
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015891"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Одновременное добавление пользователей и назначение лицензий

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Пользователям в вашей группе требуется учетная запись пользователя, прежде чем она сможет войти в систему и получить доступ к [Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/?LinkID=519395). Самый простой способ добавить учетные записи пользователей — добавить их по одной в центр администрирования Microsoft 365. После выполнения этого действия пользователям будут назначены лицензии Microsoft 365, учетные данные входа и почтовые ящики Microsoft 365.

## <a name="before-you-begin"></a>Подготовка

Для добавления пользователей и назначения лицензий необходимо быть глобальным, лицензированным или администратором пользователей. Более подробную информацию можно узнать в статье [сведения о ролях администратора](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Контрольное значение: Добавление пользователей в центре администрирования

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Действия, использованные в видеоролике, показывают другую отправную точку для добавления пользователей, но оставшиеся действия аналогичны следующим процедурам.

## <a name="add-users-one-at-a-time"></a>Добавление пользователей по одному

::: moniker range="o365-worldwide"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.
2. Перейдите к **Users** разделу > **Активные пользователи**пользователей и выберите **Добавить пользователя**.
3. В области **Настройка** основных сведений введите основные сведения о пользователе, а затем нажмите кнопку **Далее**.
    - **Name (имя** ) Введите имя и фамилию, отображаемое имя и имя пользователя.
    - **Domain (домен** ) Выберите домен для учетной записи пользователя. Например, если имя пользователя пользователя — Жакоб, а домен — contoso.com, он будет входить с помощью jakob@contoso.com.
    - **Параметры паролей** Выберите использование автоматически созданного пароля или создайте для пользователя свой надежный пароль.
    - Пользователь должен изменить свой пароль через 90 дней. Кроме того, вы можете указать, что **этот пользователь должен изменить пароль при первом входе в систему**.
    - Укажите, нужно ли отправлять пароль в сообщении электронной почты при добавлении пользователя.
4. В области **Назначение лицензий на продукты** выберите расположение и соответствующую лицензию для пользователя. Если у вас нет доступных лицензий, вы по-прежнему можете добавить пользователя и приобрести дополнительные лицензии. Разверните **приложения** , а затем выберите или отмените выбор приложения, чтобы ограничить количество приложений, для которых у пользователя есть лицензия. Нажмите кнопку **Далее**.
5. В области **необязательные параметры** разверните узел **роли** , чтобы сделать этого пользователя администратором. Разверните **сведения о профиле** , чтобы добавить дополнительные сведения о пользователе.
6. Нажмите кнопку **Далее**, просмотрите параметры нового пользователя, внесите изменения, а затем нажмите кнопку **завершить добавление**, а затем **закройте**.

::: moniker-end

::: moniker range="o365-germany"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.
2. Перейдите к **Users** разделу > **Активные пользователи**пользователей и выберите **Добавить пользователя**.
3. В области **Новый пользователь** заполните указанные ниже сведения. Когда все будет готово, нажмите кнопку **Добавить**.
    - **Имя.** Введите имя и фамилию, отображаемое имя и имя пользователя.
    - **Domain (домен** ) Например, если имя пользователя пользователя — Жакоб, а домен — contoso.com, войдите в систему, введя jakob@contoso.com.
    - **Контактные данные.** Разверните этот раздел, чтобы указать мобильный телефон, адрес и другие сведения.
    - **Password (пароль** ) Используйте автоматически сгенерированный пароль или разверните, чтобы указать надежный пароль для пользователя. Они должны изменить свой пароль через 90 дней. Кроме того, вы можете **потребовать смену пароля при первом входе пользователя**.
    - **Роли.** Разверните этот раздел, если пользователя нужно назначить администратором.
    - **Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.

::: moniker-end

::: moniker range="o365-21vianet"

1. Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.
2. Перейдите к **Users** разделу > **Активные пользователи**пользователей и выберите **Добавить пользователя**.
3. В области **Новый пользователь** заполните указанные ниже сведения. Когда все будет готово, нажмите кнопку **Добавить**.
    - **Имя.** Введите имя и фамилию, отображаемое имя и имя пользователя.
    - **Domain (домен** ) Например, если имя пользователя пользователя — Жакоб, а домен — contoso.com, войдите в систему, введя jakob@contoso.com.
    - **Контактные данные.** Разверните этот раздел, чтобы указать мобильный телефон, адрес и другие сведения.
    - **Password (пароль** ) Используйте автоматически сгенерированный пароль или разверните, чтобы указать надежный пароль для пользователя. Они должны изменить свой пароль через 90 дней. Кроме того, вы можете **потребовать смену пароля при первом входе пользователя**.
    - **Роли.** Разверните этот раздел, если пользователя нужно назначить администратором.
    - **Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Одновременное добавление нескольких пользователей

Для одновременного добавления нескольких пользователей можно использовать любой из следующих методов:
  
- **Использование электронной таблицы для массового добавления пользователей.** Ознакомьтесь [со статьей Добавление нескольких пользователей одновременно](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).
- **Автоматизация добавления учетных записей и назначения лицензий.** [В разделе Создание учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell). Выберите этот метод, если вы уже знакомы с использованием командлетов Windows PowerShell.
- **Использование ActiveDirectory** [Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization). Используйте средство Azure AD Connect для репликации учетных записей пользователей Active Directory (и других объектов Active Directory) в Microsoft 365. При синхронизации добавляются только учетные записи пользователей. Для использования электронной почты и других приложений Office необходимо назначить лицензии синхронизированным пользователям.
- **Миграция с Exchange** Узнайте о [способах переноса нескольких учетных записей электронной почты в Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). При переносе нескольких почтовых ящиков в Microsoft 365 с помощью прямой, поэтапного или гибридного метода Exchange пользователи автоматически добавляются в ходе миграции. При миграции добавляются только учетные записи пользователей. Необходимо назначить лицензии пользователям, чтобы они могли использовать электронную почту и другие приложения Office. Если пользователю не назначена лицензия, его почтовый ящик отключается по истечении 30-дневного льготного периода. Узнайте, как [назначать лицензии пользователям](../manage/assign-licenses-to-users.md) в центре администрирования Microsoft 365.

## <a name="next-steps"></a>Дальнейшие действия

После добавления пользователя вы получите по электронной почте уведомление от корпорации Майкрософт. Сообщение электронной почты содержит идентификатор пользователя и пароль, чтобы пользователи могли входить в Microsoft 365. Для этого следуйте стандартной процедуре передачи паролей. Поделитесь [руководством по быстрому использованию](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) для новых пользователей, например, как [скачать и установить приложения Office на ПК или Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) и как [настроить приложения Office и электронную почту на мобильном устройстве](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Связанные материалы

[Добавление нового сотрудника в Microsoft 365](add-new-employee.md) (статья) \
[Одновременное добавление нескольких пользователей в Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) (статья) \
[Восстановление пользователя в Microsoft 365](restore-user.md) (статья) \
[Назначение лицензий пользователям](../manage/assign-licenses-to-users.md) (статья) \
[Удаление пользователя из Организации](delete-a-user.md) (статья)