---
title: Закрытие учетной записи
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Сведения о том, как закрыть учетную запись с помощью корпорации Майкрософт.
ms.openlocfilehash: 905b3d1dfef44a6b1f78c5afe5f7673aec6b8894
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809380"
---
# <a name="close-your-account"></a>Закрытие учетной записи

При закрытии учетной записи Майкрософт все сведения, связанные с вашей учетной записью, будут удалены. Эти сведения включают подписки, лицензии, способы оплаты, пользователей и данные пользователя. Прежде чем приступать к этому процессу, обязательно выполните резервное копирование всех данных, которые необходимо сохранить.

## <a name="step-1-delete-users"></a>Шаг 1: удаление пользователей

Удалите всех пользователей за исключением одного глобального администратора, который завершает действия для закрытия учетной записи. Перед удалением каталога в конце этого процесса необходимо удалить всех остальных пользователей.

Если пользователи синхронизируются из локальной среды, сначала отключите синхронизацию, а затем удалите пользователей в облачном каталоге с помощью командлетов портала Azure или Azure PowerShell.

Чтобы удалить пользователей, обратитесь к <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">администратору управления пользователями: Удаление одного или нескольких пользователей</a>.

Вы также можете использовать командлет <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove – MsolUser</a> PowerShell для массового удаления пользователей.

Если организация использует службу Active Directory, которая синхронизируется с Azure AD, удалите учетную запись пользователя из Active Directory. Инструкции см в разделе <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">массовое удаление пользователей в Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Шаг 2: Отмена всех активных подписок

1. В центре администрирования откройте страницу "Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& услуг</a> ".

2. Если список подписок находится в представлении **таблицы** , справа выберите **карточки**.

3. Найдите активную подписку, а затем в разделе **параметры & действий** выберите **Отменить подписку**.

4. Следуйте инструкциям для завершения процесса.

5. Повторите шаги с 1 по 4 для отмены всех активных подписок.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Шаг 3: удаление всех отключенных подписок

1. В центре администрирования откройте страницу "Услуги по **выставлению счетов** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& услуг</a> ".

2. Если список подписок находится в представлении **таблицы** , справа выберите **карточки**.

3. Рядом с полем **состояние подписки**выберите **отключено**.

4. Найдите отключенную подписку, а затем в разделе **параметры & действий** нажмите кнопку **Удалить**.

5. В диалоговом окне **Удаление подписки** установите флажок **я понимаю воздействие** , а затем выберите **удалить подписку**.

6. Для каждой отключенной подписки Повторяйте шаги 4 и 5 до тех пор, пока не будут удалены все подписки.

## <a name="step-4-disable-multi-factor-authentication"></a>Шаг 4: отключение многофакторной проверки подлинности

1. В центре администрирования перейдите на страницу **Пользователи** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a> .

2. Выберите **многофакторную проверку подлинности**.

3. На странице многофакторная проверка подлинности отключите все учетные записи, кроме учетной записи глобального администратора, которую вы используете в текущий момент.

Вы также можете <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">Отключить многофакторную проверку подлинности для нескольких пользователей с помощью PowerShell</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Шаг 5: Удаление каталога в Azure Active Directory

1. Войдите в <a href="https://aad.portal.azure.com/" target="_blank">центр администрирования Azure AD</a> , используя учетную запись глобального администратора.

2. Выберите **Azure Active Directory**.

3. Перейдите к каталогу, который требуется удалить.

4. Выберите команду **Удалить каталог**.

5. Если в каталоге не удается выполнить одну или несколько проверок, вы увидите ссылку на дополнительные сведения о том, как прохождение проверок. После того как вы пройдете все проверки, нажмите кнопку **Удалить** , чтобы завершить процесс.

После выполнения этого последнего действия ваша учетная запись будет закрыта и удалена.