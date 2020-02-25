---
title: Обновление пользователей Office 365 для бизнеса до последней версии клиента Office
f1.keywords:
- NOCSH
ms.author: janellem
author: janellem
manager: eliree
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Узнайте, как обновить пользователей до последней версии клиента Office.
ms.openlocfilehash: b5b44681b26d25ec389fa12d5eee9de34f37ce43
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42256902"
---
# <a name="upgrade-your-office-365-for-business-users-to-the-latest-office-client"></a><span data-ttu-id="14ad9-103">Обновление пользователей Office 365 для бизнеса до последней версии клиента Office</span><span class="sxs-lookup"><span data-stu-id="14ad9-103">Upgrade your Office 365 for business users to the latest Office client</span></span>

## <a name="office-2010-reaches-end-of-support"></a><span data-ttu-id="14ad9-104">Office 2010 достиг конца поддержки</span><span class="sxs-lookup"><span data-stu-id="14ad9-104">Office 2010 reaches end-of-support</span></span>

<span data-ttu-id="14ad9-105">До 13 октября 2020 г. Office 2010 дойдет до конца.</span><span class="sxs-lookup"><span data-stu-id="14ad9-105">Office 2010 will reach its end of support on October 13, 2020.</span></span> <span data-ttu-id="14ad9-106">Когда Office 2010 достигает конца поддержки, корпорация Майкрософт больше не предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="14ad9-106">When Office 2010 reaches its end of support, Microsoft will no longer provide the following:</span></span>

- <span data-ttu-id="14ad9-107">Техническая поддержка для проблем</span><span class="sxs-lookup"><span data-stu-id="14ad9-107">Technical support for issues</span></span>

- <span data-ttu-id="14ad9-108">Исправление ошибок для обнаруженных проблем</span><span class="sxs-lookup"><span data-stu-id="14ad9-108">Bug fixes for issues that are discovered</span></span>

- <span data-ttu-id="14ad9-109">Исправления безопасности для обнаруженных уязвимостей</span><span class="sxs-lookup"><span data-stu-id="14ad9-109">Security fixes for vulnerabilities that are discovered</span></span>

<span data-ttu-id="14ad9-110">Более подробную информацию вы найдете в статье [Office 2010 End of support](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) .</span><span class="sxs-lookup"><span data-stu-id="14ad9-110">See [Office 2010 end of support roadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) for more information.</span></span>

 <span data-ttu-id="14ad9-111">**Это правильный раздел?**</span><span class="sxs-lookup"><span data-stu-id="14ad9-111">**Is this the right topic for you?**</span></span>
  
 <span data-ttu-id="14ad9-112">Если вы являетесь администратором, ответственным за подписку на Office 365 для бизнеса в вашей организации, вы находитесь в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="14ad9-112">If you're the admin responsible for the Office 365 for business subscription in your organization, you're in the right place.</span></span> <span data-ttu-id="14ad9-113">Администраторы, как правило, несут ответственность за такие задачи, как Управление пользователями, сброс паролей, управление установками Office, а также добавление и удаление лицензий.</span><span class="sxs-lookup"><span data-stu-id="14ad9-113">Admins are typically responsible for tasks like managing users, resetting passwords, managing Office installs and adding or removing licenses.</span></span>

 <span data-ttu-id="14ad9-114">Если вы не являетесь администратором и у вас есть продукт [Office для дома](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) , ознакомьтесь со статьей [Обновление Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) для получения сведений об обновлении старой версии Office для дома.</span><span class="sxs-lookup"><span data-stu-id="14ad9-114">If you're not an admin and you have an [Office for home](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) product, see [How do I upgrade Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) for information about upgrading your older, home use version of Office.</span></span>

## <a name="getting-ready-to-upgrade"></a><span data-ttu-id="14ad9-115">Подготовка к обновлению</span><span class="sxs-lookup"><span data-stu-id="14ad9-115">Getting ready to upgrade</span></span>

<span data-ttu-id="14ad9-116">Администратор управляет тем, какие версии Office могут устанавливать сотрудники Организации.</span><span class="sxs-lookup"><span data-stu-id="14ad9-116">As an admin, you control what version of Office people in your organization can install.</span></span> <span data-ttu-id="14ad9-117">Настоятельно рекомендуется помочь пользователям в вашей организации, на котором запущены более ранние версии Office, например Office 2010, Office 2013 или Office 2016, до последней версии, чтобы воспользоваться преимуществами безопасности и повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="14ad9-117">We highly recommend that you help users in your organization running older versions of Office such as Office 2010, Office 2013, or Office 2016 upgrade to the latest version to take advantage of its security and productivity improvements.</span></span>

## <a name="upgrade-steps"></a><span data-ttu-id="14ad9-118">Действия по обновлению</span><span class="sxs-lookup"><span data-stu-id="14ad9-118">Upgrade steps</span></span>

<span data-ttu-id="14ad9-p104">Ниже приведены пошаговые инструкции, которые помогут вам обновить программное обеспечение пользователей до последней версии классического клиента Office. Рекомендуем ознакомиться с этими шагами до начала обновления.</span><span class="sxs-lookup"><span data-stu-id="14ad9-p104">The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.</span></span>
  
## <a name="step-1---check-system-requirements"></a><span data-ttu-id="14ad9-121">Шаг 1. Проверка требований к системе</span><span class="sxs-lookup"><span data-stu-id="14ad9-121">Step 1 - Check system requirements</span></span>

<span data-ttu-id="14ad9-122">[Проверьте требования к системе](https://products.office.com/office-system-requirements) для Office, чтобы убедиться, что устройства совместимы с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-122">[Check the system requirements](https://products.office.com/office-system-requirements) for Office to make sure your devices are compatible with the latest version of Office.</span></span> <span data-ttu-id="14ad9-123">Например, на компьютерах под управлением Windows XP или Windows Vista невозможно установить более новые версии Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-123">For example, newer versions of Office can't be installed on computers running Windows XP or Windows Vista.</span></span>
  
> [!TIP]
> <span data-ttu-id="14ad9-124">Если у вас есть пользователи в вашей организации, на компьютерах которых установлены старые версии Windows, рекомендуем обновить систему до Windows 10.</span><span class="sxs-lookup"><span data-stu-id="14ad9-124">If you have users in your organization running older versions of Windows on their PCs or laptops, we recommend upgrading to Windows 10.</span></span> <span data-ttu-id="14ad9-125">В Windows 7 достигнут конец поддержки.</span><span class="sxs-lookup"><span data-stu-id="14ad9-125">Windows 7 has reached end of support.</span></span> <span data-ttu-id="14ad9-126">[Поддержка чтения для Windows 7 заканчивается в январе 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="14ad9-126">Read [Support for Windows 7 ends in January 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) for more info.</span></span>

<span data-ttu-id="14ad9-127">Ознакомьтесь с [требованиями к системе для Windows 10](https://www.microsoft.com/windows/windows-10-specifications) , чтобы узнать, можно ли обновить операционные системы.</span><span class="sxs-lookup"><span data-stu-id="14ad9-127">Check out the [Windows 10 system requirements](https://www.microsoft.com/windows/windows-10-specifications) to see if you can upgrade their operating systems.</span></span>

### <a name="check-application-compatibility"></a><span data-ttu-id="14ad9-128">Проверка совместимости приложений</span><span class="sxs-lookup"><span data-stu-id="14ad9-128">Check application compatibility</span></span>

<span data-ttu-id="14ad9-129">Чтобы обеспечить успешное обновление, рекомендуем определить все приложения Office, включая сценарии VBA, макросы, надстройки сторонних разработчиков, а также сложные документы и электронные таблицы, и оценить их совместимость с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-129">To ensure a successful upgrade, we recommend identifying your Office applications--including VBA scripts, macros, third-party add-ins, and complex documents and spreadsheets--and assessing their compatibility with the latest version of Office.</span></span>
  
<span data-ttu-id="14ad9-130">Например, если в текущей версии Office вы используете надстройки сторонних разработчиков, обратитесь к поставщику, чтобы узнать, совместимы ли они с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-130">For example, if you're using third-party add-ins with your current Office install, contact the manufacture to make sure they're compatible with the latest version of Office.</span></span>
  
## <a name="step-2---check-your-existing-subscription-plan"></a><span data-ttu-id="14ad9-131">Шаг 2. Проверка существующего плана подписки</span><span class="sxs-lookup"><span data-stu-id="14ad9-131">Step 2 - Check your existing subscription plan</span></span>

<span data-ttu-id="14ad9-132">Некоторые планы Office 365 не включают в себя полнофункциональные классические версии приложений Office, и в этом случае для обновления потребуются другие действия.</span><span class="sxs-lookup"><span data-stu-id="14ad9-132">Some Office 365 plans don't include the full desktop versions of Office and the steps to upgrade are different if your plan doesn't include Office.</span></span>
  
<span data-ttu-id="14ad9-133">Не знаете, какой план подписки у вас?</span><span class="sxs-lookup"><span data-stu-id="14ad9-133">Not sure which subscription plan you have?</span></span> <span data-ttu-id="14ad9-134">Узнайте [, что у меня есть подписка на Office 365 для бизнеса?](../admin-overview/what-subscription-do-i-have.md)</span><span class="sxs-lookup"><span data-stu-id="14ad9-134">See [What Office 365 for business subscription do I have?](../admin-overview/what-subscription-do-i-have.md)</span></span>
  
<span data-ttu-id="14ad9-135">Если ваш текущий план включает в себя Office, перейдите к разделу [Шаг 3. Удаление Office](#step-3---uninstall-office).</span><span class="sxs-lookup"><span data-stu-id="14ad9-135">If your existing plan includes Office, move on to [Step 3 - Uninstall Office](#step-3---uninstall-office).</span></span>
  
<span data-ttu-id="14ad9-136">В противном случае выберите один из вариантов ниже.</span><span class="sxs-lookup"><span data-stu-id="14ad9-136">If your existing plan doesn't include Office, then select from the options below:</span></span>
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a><span data-ttu-id="14ad9-137">Варианты обновления для планов, не включающих в себя Office</span><span class="sxs-lookup"><span data-stu-id="14ad9-137">Upgrade options for plans that don't include Office</span></span>

 <span data-ttu-id="14ad9-138">**Вариант 1: переключение подписки Office**</span><span class="sxs-lookup"><span data-stu-id="14ad9-138">**Option 1: Switch Office subscriptions**</span></span>

<span data-ttu-id="14ad9-139">Переключитесь на подписку, включающую Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-139">Switch to a subscription that includes Office.</span></span> <span data-ttu-id="14ad9-140">[В разделе переключение на другой план Office 365 для бизнеса](../../commerce/subscriptions/switch-to-a-different-plan.md).</span><span class="sxs-lookup"><span data-stu-id="14ad9-140">See [Switch to a different Office 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).</span></span>

<span data-ttu-id="14ad9-141">**Вариант 2: приобретение индивидуальных, одноразовых покупок Office или приобретение Office с помощью корпоративной лицензии**</span><span class="sxs-lookup"><span data-stu-id="14ad9-141">**Option 2: Buy individual, one-time purchases of Office, or buy Office through a volume license**</span></span>

 - <span data-ttu-id="14ad9-142">Приобретение отдельного, одноразового приобретения Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-142">Buy an individual, one-time purchase of Office.</span></span> <span data-ttu-id="14ad9-143">Ознакомьтесь с [разделами Office для &amp; дома](https://products.office.com/home-and-business) и [Office профессиональный](https://products.office.com/professional)</span><span class="sxs-lookup"><span data-stu-id="14ad9-143">See [Office Home &amp; Business](https://products.office.com/home-and-business) or [Office Professional](https://products.office.com/professional)</span></span>

     <span data-ttu-id="14ad9-144">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="14ad9-144">OR</span></span>

 - <span data-ttu-id="14ad9-145">Приобретите несколько копий Office с помощью корпоративной лицензии.</span><span class="sxs-lookup"><span data-stu-id="14ad9-145">Buy multiple copies of Office through a volume license.</span></span> <span data-ttu-id="14ad9-146">Ознакомьтесь со статьей [Сравнение пакетов, доступных по программе корпоративного лицензирования](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span><span class="sxs-lookup"><span data-stu-id="14ad9-146">See, [Compare suites available through volume licensing](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).</span></span>

## <a name="step-3---uninstall-office"></a><span data-ttu-id="14ad9-147">Шаг 3. Удаление Office</span><span class="sxs-lookup"><span data-stu-id="14ad9-147">Step 3 - Uninstall Office</span></span>

<span data-ttu-id="14ad9-148">Перед установкой последней версии Office мы рекомендуем удалить все более ранние версии Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-148">Before installing the latest version of Office, we recommend you uninstall all older versions of Office.</span></span> <span data-ttu-id="14ad9-149">Тем не менее, если вы передумали об обновлении Office, обратите внимание на следующие случаи, в которых вы не сможете переустановить Office после его удаления.</span><span class="sxs-lookup"><span data-stu-id="14ad9-149">However, if you change your mind about upgrading Office, note the following instances where you won't be able to reinstall Office after uninstalling it.</span></span>
  
<span data-ttu-id="14ad9-150">Если у вас есть надстройки сторонних производителей, обратитесь к производителю, чтобы узнать, есть ли у вас обновление, которое будет работать с последней версией Office.</span><span class="sxs-lookup"><span data-stu-id="14ad9-150">We recommend if you have third-party add-ins, contact the manufacturer to see if there's an update that will work with the latest version of Office.</span></span>

### <a name="select-the-version-of-office-you-want-to-uninstall"></a><span data-ttu-id="14ad9-151">Выберите версию Office, которую нужно удалить</span><span class="sxs-lookup"><span data-stu-id="14ad9-151">Select the version of Office you want to uninstall</span></span>

- [<span data-ttu-id="14ad9-152">С компьютера</span><span class="sxs-lookup"><span data-stu-id="14ad9-152">From a PC</span></span>](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [<span data-ttu-id="14ad9-153">Из Mac</span><span class="sxs-lookup"><span data-stu-id="14ad9-153">From a Mac</span></span>](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a><span data-ttu-id="14ad9-154">Известные проблемы при попытке переустановить предыдущие версии Office после удаления</span><span class="sxs-lookup"><span data-stu-id="14ad9-154">Known issues trying to reinstall older versions of Office after an uninstall</span></span>

 <span data-ttu-id="14ad9-155">**Office через корпоративную лицензию** Если у вас больше нет доступа к исходным файлам этих версий Office с корпоративной лицензией, вы не сможете переустановить их.</span><span class="sxs-lookup"><span data-stu-id="14ad9-155">**Office through a volume license** If you no longer have access to the source files of these volume license versions of Office, you won't be able to reinstall it.</span></span>

 <span data-ttu-id="14ad9-156">**Office, предварительно установленный на компьютере** Если у вас больше нет диска или ключа продукта (если Office поставляется вместе с одним), его невозможно будет переустановить.</span><span class="sxs-lookup"><span data-stu-id="14ad9-156">**Office pre-installed on your computer** If you no longer have a disc or product key (if Office came with one) you won't be able to reinstall it.</span></span>

 <span data-ttu-id="14ad9-157">**Неподдерживаемые подписки на Office 365** Если ваша копия Office была получена по прекращенным подпискам, например Office 365 Small Business Premium или Office 365 для среднего бизнеса, вы не сможете установить более старую версию Office, если у вас нет ключа продукта, прилагаемого к вашей подписке.</span><span class="sxs-lookup"><span data-stu-id="14ad9-157">**Non-supported Office 365 subscriptions** If your copy of Office was obtained through discontinued subscriptions, such as Office 365 Small Business Premium or Office 365 Mid-size Business, you won't be able to install an older version of Office unless you have the product key that came with your subscription.</span></span>

<span data-ttu-id="14ad9-p112">Если вы хотите установить старую версию Office параллельно с новой, просмотрите список версий, для которых поддерживается эта возможность, в статье [Установка и использование разных версий Office на одном компьютере](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx). Параллельная установка может быть хорошим выбором, например, если вы используете в текущей версии Office надстройки сторонних разработчиков и не уверены в их совместимости с новой версией.</span><span class="sxs-lookup"><span data-stu-id="14ad9-p112">If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.</span></span>

## <a name="step-4---assign-office-licenses-to-users"></a><span data-ttu-id="14ad9-160">Шаг 4. Назначение лицензий на Office пользователям</span><span class="sxs-lookup"><span data-stu-id="14ad9-160">Step 4 - Assign Office licenses to users</span></span>

<span data-ttu-id="14ad9-161">Если вы еще не сделали это, назначьте лицензии всем пользователям в вашей организации, которым требуется установить Office, ознакомьтесь с [разрешениями Назначение лицензий пользователям в office 365 для бизнеса](../manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="14ad9-161">If you haven't already done so, assign licenses to any users in your organization who need to install Office, see [Assign licenses to users in Office 365 for business](../manage/assign-licenses-to-users.md).</span></span>
  
## <a name="step-5---install-office"></a><span data-ttu-id="14ad9-162">Шаг 5. Установка Office</span><span class="sxs-lookup"><span data-stu-id="14ad9-162">Step 5 - Install Office</span></span>

<span data-ttu-id="14ad9-163">Если вы проверили, что у всех пользователей есть лицензии, на последнем этапе необходимо установить Office, ознакомиться в статье [Загрузка и установка или повторная установка Office на компьютере или Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).</span><span class="sxs-lookup"><span data-stu-id="14ad9-163">After you've verified the users you want to upgrade all have licenses, the final step is to have them install Office, see [Download and install or reinstall Office on your PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).</span></span>
  
> [!TIP]
> <span data-ttu-id="14ad9-164">Если вы не хотите, чтобы пользователи установили Office самостоятельно, ознакомьтесь со статьей [Управление параметрами загрузки программ в office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span><span class="sxs-lookup"><span data-stu-id="14ad9-164">If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365).</span></span> <span data-ttu-id="14ad9-165">[Средство развертывания Office](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) можно использовать для загрузки программного обеспечения Office в локальную сеть и последующего развертывания Office с помощью метода развертывания программного обеспечения, который обычно используется.</span><span class="sxs-lookup"><span data-stu-id="14ad9-165">You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.</span></span>