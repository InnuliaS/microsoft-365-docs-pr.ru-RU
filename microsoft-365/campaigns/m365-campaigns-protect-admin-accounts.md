---
title: Защита учетных записей администраторов
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Узнайте, как настроить и защитить учетные записи администратора.
ms.openlocfilehash: 857c24ac0ec134e119b3de083afe8dc3269bdbe2
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183402"
---
# <a name="protect-your-administrator-accounts"></a>Защита учетных записей администраторов

Так как учетные записи администраторов поставляются с повышенными привилегиями, они являются ценными целями для хакеров и кибератакных злоумышленников. В этой статье описываются:

- Настройка дополнительной учетной записи администратора для экстренных ситуаций.
- Способы защиты учетных записей.
 
При регистрации в Microsoft 365 Business и вводе сведений вы автоматически становится глобальным администратором. Глобальный администратор имеет полный контроль над учетными записями пользователей и всеми другими параметрами в центре администрирования Майкрософт, но существует множество различных типов учетных записей администраторов с различной степенью доступа. Для получения сведений о различных уровнях доступа для каждого типа роли администратора, ознакомьтесь с развернутыми [ролями](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .


## <a name="create-additional-admin-accounts"></a>Создание дополнительных учетных записей администраторов

Используйте учетные записи администраторов только для администрирования. Администраторы должны иметь отдельную учетную запись для обычного использования приложений Office и использовать их административную учетную запись только при необходимости управлять учетными записями, устройствами и при работе с другими функциями администрирования.  Кроме того, рекомендуется удалить корпоративную лицензию Microsoft 365 из учетных записей администраторов, чтобы их не нужно было платить.

Вы хотите настроить по крайней мере одну дополнительную учетную запись глобального администратора, чтобы предоставить администратору доступ к другому доверенному сотруднику. Вы также можете создавать отдельные учетные записи администраторов для управления пользователями (эта роль называется **администратором управления пользователями**). Более подробную информацию можно узнать в статье [сведения о ролях администратора](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .

Чтобы создать дополнительные учетные записи администратора:

 1. Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования</a> и выберите **Пользователи** \> **Активные пользователи** в левой панели навигации.

    ![Выбор пользователей и активных пользователей в левой панели навигации](media/Activeusers.png)

2. На странице **Активные пользователи** выберите **Добавить пользователя** в верхней части страницы и на панели **Новый пользователь** введите имя и другие сведения.
3. Разверните раздел **роли** и выберите **глобальный администратор** , чтобы предоставить этому пользователю доступ к глобальному администратору. Вы также можете выбрать **настраиваемого администратора** и выбрать любую из отображаемых ролей.

    Введите альтернативную электронную почту в текстовом поле Альтернативный адрес электронной почты. Вы можете использовать этот адрес для восстановления сведений о пароле в случае блокировки. Для глобальных администраторов на этот адрес также будет отправлена инструкция выставления счетов.

    ![Выбор роли администратора](media/adminroles.png)
    
4. В разделе **лицензии на продукты** переместите селектор для **Microsoft 365 Business** в автономный **режим** , а для параметра **создать пользователя без лицензии продукта** . ****

    ![Выбор лицензии на продукт](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Создание учетной записи администратора аварийного администратора

Кроме того, необходимо создать учетную запись резервного копирования, которая не настроена с использованием многофакторной проверки подлинности (MFA), чтобы не заблокировать себя (например, если вы потеряете номер телефона, который вы используете в качестве второй из проверки). Убедитесь, что пароль для этой учетной записи является фразой или длиной не менее 16 символов. Это часто называется "учетной записью с разделением текста".

## <a name="create-a-user-account-for-yourself"></a>Самостоятельное создание учетной записи пользователя

Используйте учетную запись пользователя для участия в совместной работе с вашей организацией, включая проверку почты. Это означает, что учетные данные администратора могут быть похожи на *Алиса. чавез<span></span>@Contoso. org* и обычная учетная запись пользователя могут быть похожи на *Алиса<span></span>@Contoso. com*.

Чтобы создать новую учетную запись пользователя, выполните указанные ниже действия.
1. Откройте <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">центр администрирования</a> и выберите **Пользователи** \> **Активные пользователи** в левой панели навигации.
2. На странице **Активные пользователи** выберите **Добавить пользователя** в верхней части страницы и на панели **Новый пользователь** введите имя и другие сведения.
3. Разверните раздел **роли** и выберите пункт **пользователь (нет административного доступа)**.
1. В разделе **лицензии на продукты** переместите селектор для **Microsoft 365 Business** в положение **включено**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Зарегистрируйте каждый из этих учетных записей для многофакторной проверки подлинности.


## <a name="additional-recommendations"></a>Дополнительные рекомендации

- Убедитесь, что учетные записи администратора также настроены для многофакторной проверки подлинности. Мы покажем, как это сделать: [Настройка политик условного доступа](m365-campaigns-conditional-access.md).
- Перед использованием учетных записей администраторов закройте все несвязанные сеансы и приложения браузера, в том числе личные учетные записи электронной почты. Вы также можете использовать в частных или инкогнито окнах браузера.
- После выполнения задач администратора не забудьте выйти из сеанса браузера.