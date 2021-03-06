---
title: Обновление Microsoft 365 для бизнеса пользователей до последней версии клиента Office
f1.keywords:
- NOCSH
ms.author: kwekuako
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Узнайте, как обновить пользователей до последней версии клиента Office.
ms.openlocfilehash: fb2513b2112dd8427222d43d14184895df3b594b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778881"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Обновление Microsoft 365 для бизнеса пользователей до последней версии клиента Office

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 достиг конца поддержки

До 13 октября 2020 г. Office 2010 дойдет до конца. Когда Office 2010 достигает конца поддержки, корпорация Майкрософт больше не предоставляет следующие возможности:

- Техническая поддержка для проблем

- Исправление ошибок для обнаруженных проблем

- Исправления безопасности для обнаруженных уязвимостей

Более подробную информацию вы найдете в статье [Office 2010 End of support](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) .

 **Это правильный раздел?**
  
 Если вы являетесь администратором, ответственным за подписку на Microsoft 365 для бизнеса в вашей организации, вы находитесь в нужном месте. Администраторы, как правило, несут ответственность за такие задачи, как Управление пользователями, сброс паролей, управление установками Office, а также добавление и удаление лицензий.

 Если вы не являетесь администратором и у вас есть продукт [семейства Microsoft 365](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) , ознакомьтесь со статьей [Обновление Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) для получения сведений об обновлении старой версии Office для дома.

## <a name="get-ready-to-upgrade"></a>Подготовка к обновлению

Администратор управляет тем, какие версии Office могут устанавливать сотрудники Организации. Настоятельно рекомендуется помочь пользователям в вашей организации, на котором запущены более ранние версии Office, например Office 2010, Office 2013 или Office 2016, до последней версии, чтобы воспользоваться преимуществами безопасности и повышения производительности.

## <a name="upgrade-steps"></a>Действия по обновлению

The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.
  
## <a name="step-1---check-system-requirements"></a>Шаг 1. Проверка требований к системе

[Проверьте требования к системе](https://products.office.com/office-system-requirements) для Office, чтобы убедиться, что устройства совместимы с последней версией Office. Например, на компьютерах под управлением Windows XP или Windows Vista невозможно установить более новые версии Office.
  
> [!TIP]
> Если у вас есть пользователи в вашей организации, на компьютерах которых установлены старые версии Windows, рекомендуем обновить систему до Windows 10. В Windows 7 достигнут конец поддержки. [Поддержка чтения для Windows 7 заканчивается в январе 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) для получения дополнительных сведений.

Ознакомьтесь с [требованиями к системе для Windows 10](https://www.microsoft.com/windows/windows-10-specifications) , чтобы узнать, можно ли обновить операционные системы.

### <a name="check-application-compatibility"></a>Проверка совместимости приложений

Чтобы обеспечить успешное обновление, рекомендуем определить все приложения Office, включая сценарии VBA, макросы, надстройки сторонних разработчиков, а также сложные документы и электронные таблицы, и оценить их совместимость с последней версией Office.
  
Например, если в текущей версии Office вы используете надстройки сторонних разработчиков, обратитесь к поставщику, чтобы узнать, совместимы ли они с последней версией Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Шаг 2. Проверка существующего плана подписки

В некоторых планах Microsoft 365 нет полнофункциональных версий Office, и действия по обновлению отличаются, если ваш план не включает Office.
  
Не знаете, какой план подписки у вас? Ознакомьтесь [с подпиской Microsoft 365 для бизнеса?](../admin-overview/what-subscription-do-i-have.md)
  
Если ваш текущий план включает в себя Office, перейдите к разделу [Шаг 3. Удаление Office](#step-3---uninstall-office).
  
В противном случае выберите один из вариантов ниже.
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Варианты обновления для планов, не включающих в себя Office

 **Вариант 1: переключение подписки Office**

Переключитесь на подписку, включающую Office. Обратитесь [к другому плану Microsoft 365 для бизнеса](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Вариант 2: приобретение индивидуальных, одноразовых покупок Office или приобретение Office с помощью корпоративной лицензии**

 - Приобретение отдельного, одноразового приобретения Office. Ознакомьтесь с [ &amp; разделами Office для дома](https://products.office.com/home-and-business) и [Office профессиональный](https://products.office.com/professional)

     OR

 - Приобретите несколько копий Office с помощью корпоративной лицензии. Ознакомьтесь со статьей [Сравнение пакетов, доступных по программе корпоративного лицензирования](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Шаг 3. Удаление Office

Перед установкой последней версии Office мы рекомендуем удалить все более ранние версии Office. Тем не менее, если вы передумали об обновлении Office, обратите внимание на следующие случаи, в которых вы не сможете переустановить Office после его удаления.
  
Если у вас есть надстройки сторонних производителей, обратитесь к производителю, чтобы узнать, есть ли у вас обновление, которое будет работать с последней версией Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Выберите версию Office, которую нужно удалить

- [С компьютера](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Из Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Известные проблемы при попытке переустановить предыдущие версии Office после удаления

 **Office через корпоративную лицензию** Если у вас больше нет доступа к исходным файлам этих версий Office с корпоративной лицензией, вы не сможете переустановить их.

 **Office, предварительно установленный на компьютере** Если у вас больше нет диска или ключа продукта (если Office поставляется вместе с одним), его невозможно будет переустановить.

 **Неподдерживаемые подписки** Если ваша копия Office была получена по прекращенным подпискам, например Office 365 Small Business Premium или Office 365 для среднего бизнеса, вы не сможете установить более старую версию Office, если у вас нет ключа продукта, прилагаемого к вашей подписке.

If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.

## <a name="step-4---assign-office-licenses-to-users"></a>Шаг 4. Назначение лицензий на Office пользователям

Если вы еще не сделали это, назначьте лицензии всем пользователям в вашей организации, которым требуется установить Office, ознакомьтесь с [разрешениями Назначение лицензий пользователям в Microsoft 365 для бизнеса](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Шаг 5. Установка Office

Если вы проверили, что у всех пользователей есть лицензии, на последнем этапе необходимо установить Office, ознакомиться в статье [Загрузка и установка или повторная установка Office на компьютере или Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).
  
> [!TIP]
> Если вы не хотите, чтобы пользователи установили Office самостоятельно, ознакомьтесь со статьей [Управление параметрами загрузки программ в office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). [Средство развертывания Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) можно использовать для загрузки программного обеспечения Office в локальную сеть и последующего развертывания Office с помощью метода развертывания программного обеспечения, который обычно используется.
