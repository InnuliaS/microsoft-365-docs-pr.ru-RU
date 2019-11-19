---
title: Использование меток конфиденциальности при работе с Microsoft Teams, группами Office 365 и сайтами SharePoint (общедоступная Предварительная версия)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Вы можете применять метки к Microsoft Teams, группам Office 365 и сайтам SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687492"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="ef81b-103">Использование меток конфиденциальности при работе с Microsoft Teams, группами Office 365 и сайтами SharePoint (общедоступная Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ef81b-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="ef81b-104">Когда вы создаете метки конфиденциальности в [центре соответствия требованиям microsoft 365](https://protection.office.com/), вы можете применить их к Microsoft Teams, группам Office 365 и сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef81b-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="ef81b-105">Вы можете связать политики с метками для управления:</span><span class="sxs-lookup"><span data-stu-id="ef81b-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="ef81b-106">Общедоступные и закрытые параметры</span><span class="sxs-lookup"><span data-stu-id="ef81b-106">Public/private settings</span></span>
- <span data-ttu-id="ef81b-107">Гостевой доступ</span><span class="sxs-lookup"><span data-stu-id="ef81b-107">Guest access</span></span>
- <span data-ttu-id="ef81b-108">Доступ с неуправляемых устройств</span><span class="sxs-lookup"><span data-stu-id="ef81b-108">Access from unmanaged devices</span></span>

<span data-ttu-id="ef81b-109">Когда вы применяете метку к группе или группе, метка автоматически применяется к подключенному сайту группы SharePoint и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ef81b-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="ef81b-110">Теперь вы также можете включить метки конфиденциальности для файлов Office в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ef81b-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="ef81b-111">[Подробнее](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="ef81b-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="ef81b-112">Общие сведения об общедоступной предварительной версии для Microsoft Teams, Office 365 Groups и сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef81b-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="ef81b-113">Метки конфиденциальности для Microsoft Teams, групп Office 365 и сайтов SharePoint постепенно выходят на клиентов и могут быть изменены до окончательного выпуска.</span><span class="sxs-lookup"><span data-stu-id="ef81b-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

## <a name="overview"></a><span data-ttu-id="ef81b-114">Обзор</span><span class="sxs-lookup"><span data-stu-id="ef81b-114">Overview</span></span>

<span data-ttu-id="ef81b-115">При публикации меток конфиденциальности пользователи в Office 365 имеют доступ к одному и тому же списку меток.</span><span class="sxs-lookup"><span data-stu-id="ef81b-115">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="ef81b-116">На этих изображениях показаны:</span><span class="sxs-lookup"><span data-stu-id="ef81b-116">These images show:</span></span>

- <span data-ttu-id="ef81b-117">Способ отображения списка при создании нового сайта группы из SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef81b-117">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="ef81b-118">При просмотре списка в Word</span><span class="sxs-lookup"><span data-stu-id="ef81b-118">When you view the list in Word</span></span>

![Метка чувствительности при создании сайта группы из SharePoint](media/sensitivity-label-new-team-site.png)

![Метка конфиденциальности, отображаемая в классическом приложении Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="ef81b-121">Включение этого предварительного просмотра с помощью Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef81b-121">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="ef81b-122">Войдите в Azure как глобальный администратор с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef81b-122">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="ef81b-123">Инструкции можно найти [в разделе Вход с помощью Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="ef81b-123">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="ef81b-124">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ef81b-124">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="ef81b-125">Office 365 больше не использует старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ef81b-125">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="ef81b-126">Если вы использовали [классификацию сайтов Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["классификатионлист"]), существующие группы и сайты по-прежнему будут отображать старые классификации.</span><span class="sxs-lookup"><span data-stu-id="ef81b-126">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="ef81b-127">Чтобы отобразить новые классификации, преобразуйте их.</span><span class="sxs-lookup"><span data-stu-id="ef81b-127">To display the new classifications, convert them.</span></span> <span data-ttu-id="ef81b-128">Сведения о том, как их преобразовать, можно узнать в статье [использование классического класса классификации сайта Azure AD](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="ef81b-128">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span>

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a><span data-ttu-id="ef81b-129">Настройка параметров сайтов и групп при создании меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="ef81b-129">Set site and group settings when you create sensitivity labels</span></span>

<span data-ttu-id="ef81b-130">После включения предварительной версии выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ef81b-130">After you enable the preview, follow these steps:</span></span>

1. <span data-ttu-id="ef81b-131">В центре соответствия требованиям Microsoft 365 выберите**метки чувствительности** **классификации** > .</span><span class="sxs-lookup"><span data-stu-id="ef81b-131">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="ef81b-132">Выберите **создать метку**.</span><span class="sxs-lookup"><span data-stu-id="ef81b-132">Select **Create a label**.</span></span>

3. <span data-ttu-id="ef81b-133">Выберите нужные параметры, а затем на вкладке **Параметры сайта и группы** выберите:</span><span class="sxs-lookup"><span data-stu-id="ef81b-133">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="ef81b-134">Конфиденциальность (общедоступная или частная): Частная означает, что в группе могут видеть только утвержденные участники.</span><span class="sxs-lookup"><span data-stu-id="ef81b-134">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="ef81b-135">Все остальные пользователи в вашей организации не могут видеть содержимое группы.</span><span class="sxs-lookup"><span data-stu-id="ef81b-135">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="ef81b-136">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ef81b-136">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="ef81b-137">Гостевой доступ: вы можете указать, можно ли добавлять гостей в группу.</span><span class="sxs-lookup"><span data-stu-id="ef81b-137">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="ef81b-138">Сведения об управлении гостевым доступом в группах Office 365</span><span class="sxs-lookup"><span data-stu-id="ef81b-138">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="ef81b-139">Неуправляемые устройства: этот параметр позволяет заблокировать или ограничить доступ к контенту SharePoint с устройств, не являющихся гибридными или не связанными с Intune в Intune.</span><span class="sxs-lookup"><span data-stu-id="ef81b-139">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="ef81b-140">Если вы выбрали неуправляемые устройства, вам нужно перейти в Azure AD, чтобы завершить настройку политики.</span><span class="sxs-lookup"><span data-stu-id="ef81b-140">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="ef81b-141">Сведения см. [в статье Управление доступом с неуправляемых устройств](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="ef81b-141">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![Вкладка "Параметры сайта и групп"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="ef81b-143">Только параметры сайта и групп вступают в силу при применении метки к команде, группе или сайту.</span><span class="sxs-lookup"><span data-stu-id="ef81b-143">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="ef81b-144">Другие параметры, такие как шифрование и маркировка содержимого, не применяются ко всему контенту в группе, группе или на сайте.</span><span class="sxs-lookup"><span data-stu-id="ef81b-144">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="ef81b-145">Аналогичным образом, если вы создаете метку и не включаете параметры сайта и группы, метка будет доступна, когда пользователи создают команды, группы и сайты, но не будут ничего делать при его применении пользователями.</span><span class="sxs-lookup"><span data-stu-id="ef81b-145">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="ef81b-146">Сведения о публикации метки чувствительности</span><span class="sxs-lookup"><span data-stu-id="ef81b-146">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="ef81b-147">Применение метки конфиденциальности к новой команде</span><span class="sxs-lookup"><span data-stu-id="ef81b-147">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="ef81b-148">Пользователи могут выбирать метки конфиденциальности при создании новых команд в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ef81b-148">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="ef81b-149">При выборе уровня чувствительности параметры конфиденциальности изменяются по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="ef81b-149">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="ef81b-150">В зависимости от параметров гостевого доступа, выбранных для метки, пользователи могут или не могут добавлять людей, не входящих в организацию, в команду.</span><span class="sxs-lookup"><span data-stu-id="ef81b-150">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![Параметр конфиденциальности при создании новой команды](media/privacy-setting-new-team.png)

<span data-ttu-id="ef81b-152">После создания команды метка чувствительности отображается в правом верхнем углу всех каналов.</span><span class="sxs-lookup"><span data-stu-id="ef81b-152">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![Метка чувствительности отображается в команде](media/privacy-setting-teams.png)

<span data-ttu-id="ef81b-154">Служба автоматически применяет ту же метку конфиденциальности к группе Office 365 и подключенному сайту группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef81b-154">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="ef81b-155">Применение метки конфиденциальности к новой группе</span><span class="sxs-lookup"><span data-stu-id="ef81b-155">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="ef81b-156">В Outlook в Интернете новое поле " **чувствительность** " содержит опубликованные метки.</span><span class="sxs-lookup"><span data-stu-id="ef81b-156">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="ef81b-157">Если пользователям нужна дополнительная информация, они могут щелкнуть значок Справка, чтобы прочитать сведения о доступных метках и связанных с ними политиках.</span><span class="sxs-lookup"><span data-stu-id="ef81b-157">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Создание группы и выбор параметра в разделе чувствительность](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="ef81b-159">Применение метки конфиденциальности к новому сайту</span><span class="sxs-lookup"><span data-stu-id="ef81b-159">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="ef81b-160">Администраторы и конечные пользователи могут выбирать метки конфиденциальности при создании современных сайтов группы и сайтов для общения.</span><span class="sxs-lookup"><span data-stu-id="ef81b-160">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="ef81b-161">Узнайте, как создать сайт в новом центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef81b-161">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="ef81b-162">Когда пользователи создают современные группы и сайты для общения, метка чувствительности уже выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef81b-162">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="ef81b-163">Пользователи могут выбрать значок справки, чтобы узнать больше о метках.</span><span class="sxs-lookup"><span data-stu-id="ef81b-163">Users can select the help icon to learn more about the labels.</span></span>

![Создание сайта и выбор параметра в соответствии с чувствительностью](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="ef81b-165">Когда пользователи просматривают сайт, они могут видеть имя метки и примененные политики.</span><span class="sxs-lookup"><span data-stu-id="ef81b-165">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Сайт, к которому применена метка чувствительности](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="ef81b-167">Управление метками конфиденциальности в центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef81b-167">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="ef81b-168">Для просмотра и редактирования меток используйте страницу "активные сайты" в новом центре администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef81b-168">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![Столбец "чувствительность" на странице активных сайтов](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="ef81b-170">[Узнайте больше об управлении сайтами в новом центре администрирования SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ef81b-170">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="ef81b-171">Изменение параметров сайта и группы для метки</span><span class="sxs-lookup"><span data-stu-id="ef81b-171">Change site and group settings for a label</span></span>

<span data-ttu-id="ef81b-172">Рекомендуется не изменять параметры после применения метки к нескольким командам, группам или сайтам.</span><span class="sxs-lookup"><span data-stu-id="ef81b-172">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="ef81b-173">Если необходимо внести изменения, необходимо использовать сценарий PowerShell для Azure AD для применения обновлений вручную.</span><span class="sxs-lookup"><span data-stu-id="ef81b-173">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="ef81b-174">Этот метод обеспечивает применение нового параметра ко всем существующим командам, сайтам и группам.</span><span class="sxs-lookup"><span data-stu-id="ef81b-174">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="ef81b-175">Поддержка новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="ef81b-175">Support for the new sensitivity labels</span></span>

<span data-ttu-id="ef81b-176">Следующие приложения и службы поддерживают метки конфиденциальности в данном предварительном просмотре:</span><span class="sxs-lookup"><span data-stu-id="ef81b-176">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="ef81b-177">Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef81b-177">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="ef81b-178">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef81b-178">SharePoint</span></span>
- <span data-ttu-id="ef81b-179">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="ef81b-179">Outlook on the web</span></span>
- <span data-ttu-id="ef81b-180">Teams</span><span class="sxs-lookup"><span data-stu-id="ef81b-180">Teams</span></span>
- <span data-ttu-id="ef81b-181">Центр администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef81b-181">SharePoint admin center</span></span>
- <span data-ttu-id="ef81b-182">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="ef81b-182">Azure AD admin center</span></span>

<span data-ttu-id="ef81b-183">Вы не можете использовать следующие приложения и службы для создания групп Office 365 с новыми метками конфиденциальности:</span><span class="sxs-lookup"><span data-stu-id="ef81b-183">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="ef81b-184">Outlook для Mac</span><span class="sxs-lookup"><span data-stu-id="ef81b-184">Outlook for the Mac</span></span>
- <span data-ttu-id="ef81b-185">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="ef81b-185">Outlook mobile</span></span>  
- <span data-ttu-id="ef81b-186">Настольный Outlook для Windows</span><span class="sxs-lookup"><span data-stu-id="ef81b-186">Outlook desktop for Windows</span></span>
- <span data-ttu-id="ef81b-187">формы;</span><span class="sxs-lookup"><span data-stu-id="ef81b-187">Forms</span></span>  
- <span data-ttu-id="ef81b-188">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ef81b-188">Dynamics 365</span></span>  
- <span data-ttu-id="ef81b-189">Yammer</span><span class="sxs-lookup"><span data-stu-id="ef81b-189">Yammer</span></span>  
- <span data-ttu-id="ef81b-190">Stream</span><span class="sxs-lookup"><span data-stu-id="ef81b-190">Stream</span></span>  
- <span data-ttu-id="ef81b-191">Планировщик</span><span class="sxs-lookup"><span data-stu-id="ef81b-191">Planner</span></span>  
- <span data-ttu-id="ef81b-192">Project</span><span class="sxs-lookup"><span data-stu-id="ef81b-192">Project</span></span>  
- <span data-ttu-id="ef81b-193">PowerBI</span><span class="sxs-lookup"><span data-stu-id="ef81b-193">PowerBI</span></span>  
- <span data-ttu-id="ef81b-194">Центр администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="ef81b-194">Teams admin center</span></span>  
- <span data-ttu-id="ef81b-195">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef81b-195">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="ef81b-196">Центр администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="ef81b-196">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="ef81b-197">Если вы использовали классическую классификацию сайтов Azure AD</span><span class="sxs-lookup"><span data-stu-id="ef81b-197">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="ef81b-198">Office 365 больше не поддерживает старые классификации для новых групп и сайтов SharePoint при включении этого предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ef81b-198">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="ef81b-199">Однако существующие группы и сайты по-прежнему отображают старые классификации, пока не будут преобразованы.</span><span class="sxs-lookup"><span data-stu-id="ef81b-199">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="ef81b-200">Старые классификации включают "современные классификации сайтов, которые вы настроили, возможно, с помощью Azure AD PowerShell или библиотеки ядра PnP, которые задают определенные `ClassificationList` значения параметра.</span><span class="sxs-lookup"><span data-stu-id="ef81b-200">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="ef81b-201">Например, в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ef81b-201">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="ef81b-202">Дополнительные сведения о старом методе классификации можно найти в разделе ["современные" классификации сайтов SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="ef81b-202">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="ef81b-203">В зависимости от текущего развертывания у вас есть два варианта преобразования старых классификаций в новые классификации.</span><span class="sxs-lookup"><span data-stu-id="ef81b-203">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="ef81b-204">Если вы никогда не использовали метки чувствительности (единой системы меток защиты информации Майкрософт) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="ef81b-204">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="ef81b-205">Мы рекомендуем вам:</span><span class="sxs-lookup"><span data-stu-id="ef81b-205">We recommend that you:</span></span>

1. <span data-ttu-id="ef81b-206">Создайте новые метки конфиденциальности в центре соответствия требованиям Microsoft 365, имена которых совпадают с именами существующих классификаций.</span><span class="sxs-lookup"><span data-stu-id="ef81b-206">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="ef81b-207">Используйте PowerShell, чтобы применить новые метки к существующим группам Office 365 и сайтам SharePoint с помощью сопоставления имен.</span><span class="sxs-lookup"><span data-stu-id="ef81b-207">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="ef81b-208">Удалите старые классификации.</span><span class="sxs-lookup"><span data-stu-id="ef81b-208">Delete the old classifications.</span></span>

<span data-ttu-id="ef81b-209">Приложения и службы, которые поддерживают новые метки конфиденциальности, отобразят их.</span><span class="sxs-lookup"><span data-stu-id="ef81b-209">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="ef81b-210">Новые метки создаются в новых командах, группах и сайтах.</span><span class="sxs-lookup"><span data-stu-id="ef81b-210">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="ef81b-211">Пользователи по-прежнему могут создавать группы из приложений и служб, которые не поддерживают новые метки.</span><span class="sxs-lookup"><span data-stu-id="ef81b-211">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="ef81b-212">Однако пользователи не могут применить метку к этим группам.</span><span class="sxs-lookup"><span data-stu-id="ef81b-212">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="ef81b-213">Используйте PowerShell, чтобы применить новые метки конфиденциальности для этих групп.</span><span class="sxs-lookup"><span data-stu-id="ef81b-213">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="ef81b-214">Вы можете хранить старые классификации; Однако настоятельно рекомендуется использовать PowerShell, чтобы применить новые метки конфиденциальности к этим группам.</span><span class="sxs-lookup"><span data-stu-id="ef81b-214">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="ef81b-215">Приложения и службы, которые поддерживают новые метки конфиденциальности, будут созданы с новыми метками.</span><span class="sxs-lookup"><span data-stu-id="ef81b-215">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="ef81b-216">Когда пользователи создают группы из приложений и служб, которые не поддерживают новые метки, они могут выбрать классификацию.</span><span class="sxs-lookup"><span data-stu-id="ef81b-216">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="ef81b-217">Если вы используете метки конфиденциальности (Объединенные метки информационной защиты Майкрософт) для файлов и электронной почты</span><span class="sxs-lookup"><span data-stu-id="ef81b-217">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="ef81b-218">После включения этого предварительного просмотра перейдите к каждой метке в центре соответствия требованиям Microsoft 365 и примените нужные политики для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="ef81b-218">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="ef81b-219">Пользователи начнут просматривать существующие метки, доступные для сайтов и групп.</span><span class="sxs-lookup"><span data-stu-id="ef81b-219">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="ef81b-220">Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365</span><span class="sxs-lookup"><span data-stu-id="ef81b-220">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="ef81b-221">Перед применением новых меток убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef81b-221">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="ef81b-222">Если у вас уже есть последняя версия, вы можете [переметить группы Office 365 с помощью новых меток конфиденциальности](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="ef81b-222">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="ef81b-223">Подготовка командной консоли SharePoint Online для предварительного просмотра:</span><span class="sxs-lookup"><span data-stu-id="ef81b-223">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="ef81b-224">Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу **Установка и удаление программ** и удаление "Командная консоль SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="ef81b-224">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="ef81b-225">В веб-браузере перейдите на страницу центра загрузки и [скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="ef81b-225">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="ef81b-226">Выберите язык и нажмите кнопку **скачать**.</span><span class="sxs-lookup"><span data-stu-id="ef81b-226">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="ef81b-227">Выберите файл в формате x64 и x86. msi.</span><span class="sxs-lookup"><span data-stu-id="ef81b-227">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="ef81b-228">Скачайте файл x64, если вы используете 64-разрядную версию Windows или файл x86, если вы запускаете 32-разрядную версию.</span><span class="sxs-lookup"><span data-stu-id="ef81b-228">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="ef81b-229">Если вы не знаете, посмотрите, [какая версия операционной системы Windows работает?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="ef81b-229">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="ef81b-230">После загрузки файла запустите его и следуйте указаниям мастера установки.</span><span class="sxs-lookup"><span data-stu-id="ef81b-230">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="ef81b-231">Переразметка групп Office 365 с помощью новых меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="ef81b-231">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="ef81b-232">Убедитесь, что вы используете последнюю версию командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef81b-232">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="ef81b-233">Инструкции можно найти [в статье Подготовка командной консоли SharePoint Online перед переразметкой групп Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="ef81b-233">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="ef81b-234">С помощью рабочей или учебной учетной записи, имеющей права глобального администратора или администратора SharePoint в Office 365, подключитесь к консоли управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef81b-234">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="ef81b-235">Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="ef81b-235">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="ef81b-236">Выполните следующую команду, чтобы получить список меток конфиденциальности и их идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="ef81b-236">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="ef81b-237">Запишите GUID для метки, которую требуется перезаписать.</span><span class="sxs-lookup"><span data-stu-id="ef81b-237">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="ef81b-238">Например, метка "Общие".</span><span class="sxs-lookup"><span data-stu-id="ef81b-238">For example, the "General" label.</span></span>

5. <span data-ttu-id="ef81b-239">Используйте следующую команду, чтобы получить список групп с классификацией "общий".</span><span class="sxs-lookup"><span data-stu-id="ef81b-239">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="ef81b-240">При выполнении этой команды вы будете подключаться к Exchange Online PowerShell и исполняем командлет Get-UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="ef81b-240">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="ef81b-241">Для каждой группы добавьте новый GUID метки чувствительности.</span><span class="sxs-lookup"><span data-stu-id="ef81b-241">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```