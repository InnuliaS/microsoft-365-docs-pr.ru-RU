---
title: Подготовка сопоставленных дисков для настольных компьютеров, управляемых Майкрософт
description: Важные действия, которые необходимо проверить
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079277"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="66112-104">Подготовка сопоставленных дисков для настольных компьютеров, управляемых Майкрософт</span><span class="sxs-lookup"><span data-stu-id="66112-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="66112-105">Во многих корпоративных средах существуют устаревшие требования к сопоставленным дискам, позволяющие пользователям или рабочим группам совместно использовать и хранить файлы, а также для локальных приложений.</span><span class="sxs-lookup"><span data-stu-id="66112-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="66112-106">Корпорация Майкрософт не рекомендует использовать сопоставленные диски с компьютером, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="66112-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="66112-107">Вместо этого рекомендуется модернизация решениям для доступа к файлам Йор следующим образом:</span><span class="sxs-lookup"><span data-stu-id="66112-107">Instead, we recommend that you modernize yor file access solutions as follows:</span></span>
  
- <span data-ttu-id="66112-108">Перенос подключенных дисков, используемых отдельными пользователями, в OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="66112-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="66112-109">Перенос подключенных дисков, используемых Teams, для предоставления общего доступа к файлам в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="66112-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="66112-110">Модернизация или замените все приложения, использующие локальные файловые ресурсы, для удаления этого требования.</span><span class="sxs-lookup"><span data-stu-id="66112-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="66112-111">Модернизации эти службы обеспечивают наилучшее взаимодействие с пользователями, управляемыми корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="66112-111">Modernizing these services will allow the best end-user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="66112-112">Службы Microsoft FastTrack могут помочь вам в модернизации вашей среды с помощью облачных служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="66112-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="66112-113">Вы можете проверить, есть ли у вас права для служб FastTrack, в [соответствующих службах и планах](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) , а затем напрямую обратиться к ним, чтобы подготовиться к работе с Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="66112-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="66112-114">Общие сведения о миграции [данных](https://docs.microsoft.com/fasttrack/o365-data-migration)в FastTrack OneDrive для бизнеса или SharePoint Online см.</span><span class="sxs-lookup"><span data-stu-id="66112-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="66112-115">Подключенные диски на настольном компьютере, управляемом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="66112-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="66112-116">Если вы не можете удалять или заменять сопоставленные диски в некоторых случаях использования, необходимо отправить запрос в службу поддержки на портале настольных компьютеров Майкрософт, чтобы они были развернуты на компьютерах, управляемых пользователями.</span><span class="sxs-lookup"><span data-stu-id="66112-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="66112-117">Для такого запроса необходимо предоставить следующие сведения в запросе поддержки:</span><span class="sxs-lookup"><span data-stu-id="66112-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="66112-118">Все пути UNC к расположениям общего файлового ресурса, которые необходимо сопоставить с управляемыми устройствами для настольных компьютеров Майкрософт</span><span class="sxs-lookup"><span data-stu-id="66112-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="66112-119">Группы пользователей, которым требуется доступ к этим расположениям общих папок</span><span class="sxs-lookup"><span data-stu-id="66112-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="66112-120">Любая буква диска, которая должна быть назначена (при необходимости);</span><span class="sxs-lookup"><span data-stu-id="66112-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="66112-121">Примеры:</span><span class="sxs-lookup"><span data-stu-id="66112-121">For example:</span></span>

| <span data-ttu-id="66112-122">Буква диска</span><span class="sxs-lookup"><span data-stu-id="66112-122">Drive letter</span></span> | <span data-ttu-id="66112-123">UNC-путь</span><span class="sxs-lookup"><span data-stu-id="66112-123">UNC path</span></span> | <span data-ttu-id="66112-124">Группа пользователей</span><span class="sxs-lookup"><span data-stu-id="66112-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="66112-125">X</span><span class="sxs-lookup"><span data-stu-id="66112-125">X:</span></span>  | <span data-ttu-id="66112-126">\\\Сервер\шаре\маркетинг</span><span class="sxs-lookup"><span data-stu-id="66112-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="66112-127">Контосомаркетинг</span><span class="sxs-lookup"><span data-stu-id="66112-127">ContosoMarketing</span></span> |

<span data-ttu-id="66112-128">Она полностью отвечает за обеспечение наличия у пользователей и групп разрешений на доступ к общим папкам, а также в том, что локальные файловые службы останутся доступными.</span><span class="sxs-lookup"><span data-stu-id="66112-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="66112-129">Кроме того, необходимо как можно скорее удалить свои требования для таких файловых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="66112-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="66112-130">Для отображения подключенных дисков, развернутых в Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="66112-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="66112-131">Убедитесь, что не удается устранить сопоставленные диски, и внимательно проанализируйте требования перед отправкой запроса на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="66112-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="66112-132">Затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="66112-132">Then follow these steps:</span></span>

1. <span data-ttu-id="66112-133">Перейдите на [портал настольных компьютеров, управляемых Майкрософт](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="66112-133">Navigate to the [Microsoft Managed Desktop portal](https://aka.ms/mmdportal).</span></span>  
2. <span data-ttu-id="66112-134">Отправьте запрос в службу поддержки под названием "развертывание сопоставленных дисков" в разделе **Поддержка _Гт_ поддержки** , а затем предоставьте все необходимые сведения о файловом ресурсе.</span><span class="sxs-lookup"><span data-stu-id="66112-134">Submit a support request titled “Mapped drives deployment” through the **Support > Support requests** section and provide all the required file share details.</span></span>  
3. <span data-ttu-id="66112-135">Операции с управляемыми рабочими столами Майкрософт будут рекомендовать, используя обновления запроса поддержки, когда запрос будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="66112-135">Microsoft Managed Desktop Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="66112-136">Изначально эта конфигурация будет развернута только на устройствах в группе тестового развертывания.</span><span class="sxs-lookup"><span data-stu-id="66112-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="66112-137">Необходимо протестировать и проверить, работает ли конфигурация, развернутая группой операций, управляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="66112-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop Operations team works as you expect.</span></span> <span data-ttu-id="66112-138">Используйте запрос в службу поддержки, чтобы обновить операционные системы, управляемые корпорацией Майкрософт по завершении тестирования.</span><span class="sxs-lookup"><span data-stu-id="66112-138">Use the support request to update Microsoft Managed Desktop Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="66112-139">После этого Группа "управляемые операции для настольных систем Майкрософт" будет развертывать конфигурацию в других группах развертывания.</span><span class="sxs-lookup"><span data-stu-id="66112-139">Microsoft Managed Desktop Operations team will then deploy the configuration to the other deployment groups.</span></span> 