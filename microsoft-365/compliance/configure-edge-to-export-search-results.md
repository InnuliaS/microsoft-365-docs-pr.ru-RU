---
title: Использование средства экспорта eDiscovery Office 365 в Microsoft Edge
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Необходимо включить поддержку ClickOnce, чтобы использовать Microsoft Edge для экспорта результатов поиска из поиска контента и обнаружения электронных данных в центре безопасности и соответствия требованиям.
ms.openlocfilehash: 75595f45a1369eb732c2249258af21edced86890
ms.sourcegitcommit: 062be618f0b18611001552273bb175020420e463
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "39676892"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="9e5c9-103">Использование средства экспорта eDiscovery Office 365 в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e5c9-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="9e5c9-104">В результате последних изменений в Microsoft EDGE поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="9e5c9-105">Чтобы продолжить использование средства экспорта обнаружения электронных данных Microsoft Office 365 для загрузки результатов поиска и обнаружения электронных данных, необходимо использовать [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) или включить поддержку ClickOnce в Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="9e5c9-106">Включение поддержки ClickOnce в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e5c9-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="9e5c9-107">В Microsoft Edge перейдите в **раздел edge://flags/#edge — один раз**.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="9e5c9-108">Если в раскрывающемся списке существующее значение установлено **по умолчанию** или **отключено** , измените его на **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](media/ClickOnceimage1.png)

3. <span data-ttu-id="9e5c9-109">Прокрутите окно вниз до конца окна браузера и выберите команду **перезапустить** , чтобы перезапустить пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](media/ClickOnceimage2.png)

<span data-ttu-id="9e5c9-110">**Примечание:** Для отключения поддержки ClickOnce в организациях можно использовать групповую политику.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="9e5c9-111">Чтобы проверить, существует ли политика Организации для поддержки ClickOnce, перейдите в раздел **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="9e5c9-112">На следующем снимке экрана показано, что технология ClickOnce включена во всей Организации.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="9e5c9-113">Если для этого параметра политики задано значение **false**, необходимо обратиться к администратору в Организации.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="9e5c9-114">Установка и запуск средства экспорта eDiscovery для Office 365</span><span class="sxs-lookup"><span data-stu-id="9e5c9-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="9e5c9-115">Нажмите кнопку **скачать результаты** на всплывающей странице экспорта в поиске контента или в случае обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Нажмите кнопку Скачать результаты на всплывающей странице, чтобы скачать результаты поиска.](media/ClickOnceExport1.png)

2. <span data-ttu-id="9e5c9-117">Появится запрос на подтверждение запуска средства, нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта eDiscovery](media/ClickOnceimage4.png)

   <span data-ttu-id="9e5c9-119">Если средство экспорта обнаружения электронных данных Microsoft Office 365 не установлено, появится предупреждение системы безопасности,</span><span class="sxs-lookup"><span data-stu-id="9e5c9-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Нажмите кнопку установить, чтобы установить средство экспорта обнаружения электронных данных](media/ClickOnceimage5.png)

3. <span data-ttu-id="9e5c9-121">Нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-121">Click **Install**.</span></span> <span data-ttu-id="9e5c9-122">После установки средство экспорта будет запущено автоматически.</span><span class="sxs-lookup"><span data-stu-id="9e5c9-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="9e5c9-123">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="9e5c9-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="9e5c9-124">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="9e5c9-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="9e5c9-125">Включение поэкспериментических флагов в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e5c9-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)