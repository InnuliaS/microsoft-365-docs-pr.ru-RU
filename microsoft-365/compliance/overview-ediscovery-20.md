---
title: Обзор расширенного решения обнаружения электронных данных в Microsoft 365
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
description: В этой статье описывается новая версия расширенного обнаружения электронных данных в Microsoft 365.
ms.openlocfilehash: e63fe05cf9a2e236247da3c45674b53cc830546d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090801"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a><span data-ttu-id="f8ac9-103">Обзор расширенного решения обнаружения электронных данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8ac9-103">Overview of the Advanced eDiscovery solution in Microsoft 365</span></span>

<span data-ttu-id="f8ac9-104">Расширенное решение обнаружения электронных данных в Microsoft 365 построено на существующих возможностях обнаружения электронных данных и аналитики в Office 365.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-104">The Advanced eDiscovery solution in Microsoft 365 builds on the existing eDiscovery and analytics capabilities in Office 365.</span></span> <span data-ttu-id="f8ac9-105">Это новое решение, именуемое *Advanced eDiscovery*, предоставляет сквозной рабочий процесс для сохранения, сбора, проверки, анализа и экспорта контента, который отвечает на внутренние и внешние расследования вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-105">This new solution, called *Advanced eDiscovery*, provides an end-to-end workflow to preserve, collect, review, analyze, and export content that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="f8ac9-106">Кроме того, он позволяет юридическим командам управлять всем рабочим процессом уведомления об удержаниях на удержание, чтобы общаться с custodians, вовлеченным в дело.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-106">It also lets legal teams manage the entire legal hold notification workflow to communicate with custodians involved in a case.</span></span> 

## <a name="alignment-with-edrm"></a><span data-ttu-id="f8ac9-107">Выравнивание с EDRM</span><span class="sxs-lookup"><span data-stu-id="f8ac9-107">Alignment with EDRM</span></span>

<span data-ttu-id="f8ac9-108">Встроенный бизнес-процесс с расширенным обнаружением электронных данных выравнивается по процессу обнаружения электронных данных, описанному в справочной модели электронного обнаружения (EDRM).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-108">The built-in workflow of Advanced eDiscovery aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span> 

![Справочная модель электронного обнаружения (EDRM)](media/EDRMv1.png)

<span data-ttu-id="f8ac9-110">(Источник изображения с edrm.net.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-110">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="f8ac9-111">Исходное изображение было доступно в разделе неперенесенная лицензия Creative Commons со соотнесением 3,0.)</span><span class="sxs-lookup"><span data-stu-id="f8ac9-111">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="f8ac9-112">На высоком уровне ниже показано, как Расширенное обнаружение электронных данных поддерживает рабочий процесс EDRM:</span><span class="sxs-lookup"><span data-stu-id="f8ac9-112">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="f8ac9-113">**Идентификация** — после определения потенциальных людей, которые будут полезны в расследовании, вы можете добавить их как custodians (также называемые *custodians данных*, так как они могут хранить информацию, относящуюся к расследованию) на расширенный вариант обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-113">**Identification** – After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="f8ac9-114">После добавления пользователей в качестве custodians можно легко сохранить, собрать и проверить документы хранитель.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-114">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="f8ac9-115">**Сохранение** — для сохранения и защиты данных, относящихся к расследованию, Расширенное обнаружение электронных данных позволяет разместить удержание на источниках данных, связанных с custodians, в случае.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-115">**Preservation** – To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="f8ac9-116">Вы также можете размещать данные, не относящиеся к кустодиал, на удержании.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-116">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="f8ac9-117">Расширенное обнаружение электронных данных также имеет встроенный рабочий процесс связи, который позволяет отправлять уведомления о юридических удержаниях в custodians и отслеживать их подтверждения.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-117">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="f8ac9-118">**Collection** — после определения (и сохранения) источников данных, относящихся к расследованию, вы можете использовать встроенное средство поиска в разделе Advanced обнаружения электронных данных для и сбора данных из источников данных кустодиал (и источников данных, отличных от кустодиал (если применимо), которые могут быть релевантны для случая.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-118">**Collection** – After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="f8ac9-119">**Обработка** — после сбора всех данных, относящихся к этому случаю, следующий шаг обрабатывает его для дальнейшего анализа и анализа.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-119">**Processing** – After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="f8ac9-120">В расширенном режиме обнаружения электронных данных данные на месте копируются в место хранения Azure (называемое *набором проверки*), что обеспечивает статическое представление данных вариантов.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 
 
- <span data-ttu-id="f8ac9-121">**Проверка** – после добавления данных в набор проверки можно просматривать определенные документы и выполнять другие запросы, чтобы уменьшить количество данных до наиболее релевантного варианта.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-121">**Review** – After data has been added to a review set, you can view specific documents and run another queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="f8ac9-122">Кроме того, можно закомментировать и пометить документы определенными тегами.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-122">Also, can annotate and tag specific documents.</span></span>
 
- <span data-ttu-id="f8ac9-123">**Анализ** — Расширенное обнаружение электронных данных предоставляет интегрированное средство аналитики, которое помогает дополнительному изучению данных из набора проверки, которые вы определили, не важны для расследования.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-123">**Analysis** – Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="f8ac9-124">Кроме уменьшения объема релевантных данных, предварительное обнаружение электронных данных также помогает сэкономить затраты на проверку, позволяя организовывать процесс проверки и более простой и эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-124">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="f8ac9-125">**Рабочая среда** и **Презентация** — когда вы будете готовы, вы можете экспортировать документы из набора рецензирования для юридической проверки.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-125">**Production** and **Presentation** – When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="f8ac9-126">Документы можно экспортировать в исходном формате или в формате EDRM, чтобы их можно было импортировать в сторонние приложения проверки.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-126">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="advanced-ediscovery-workflow"></a><span data-ttu-id="f8ac9-127">Расширенный рабочий процесс обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="f8ac9-127">Advanced eDiscovery workflow</span></span>

<span data-ttu-id="f8ac9-128">В следующих разделах описывается каждый этап встроенного рабочего процесса в Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-128">The following sections describe each step in the built-in workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="f8ac9-129">На следующем снимке экрана показана вкладка " **Главная** " для случая с названием " *ответственность за продукт 2019002*".</span><span class="sxs-lookup"><span data-stu-id="f8ac9-129">The following screenshot shows the **Home** tab of a case named *Product Liability 2019002*.</span></span> <span data-ttu-id="f8ac9-130">Обратите внимание, что вкладки рабочих процессов, расположенные в верхней части страницы, упорядочены в соответствии с процессом EDRM.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-130">Note the workflow tabs at the top of the page are sequenced to align with the EDRM process.</span></span> 

<span data-ttu-id="f8ac9-131">Для получения дополнительных сведений о сквозном рабочем процессе в Advanced eDiscovery посетите этот [видеоролик Microsoft механики](https://go.microsoft.com/fwlink/?linkid=2066133).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-131">For more information about the end-to-end workflow in Advanced eDiscovery, see this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133).</span></span> 

![Вкладки расширенного обнаружения электронных данных следуют в рабочем процессе EDRM](media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a><span data-ttu-id="f8ac9-133">Управление custodians</span><span class="sxs-lookup"><span data-stu-id="f8ac9-133">Managing custodians</span></span>

<span data-ttu-id="f8ac9-134">Используйте вкладку **custodians** для добавления людей, которые вы указали в качестве интересующих людей, и управления ими.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-134">Use the **Custodians** tab to add and manage the people that you've identified as persons of interest in the case.</span></span> <span data-ttu-id="f8ac9-135">При добавлении custodians можно быстро выполнять действия, связанные с хранитель, такие как помещение судебного удержания на источники данных хранитель, связь с custodians и поиск в источниках данных хранитель, чтобы собрать содержимое, которое относится к этому случаю.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-135">When you add custodians, you can quickly perform custodian-related actions like placing a legal hold on custodian data sources, communicating with custodians, and searching custodian data sources to collect content that's relevant to the case.</span></span> <span data-ttu-id="f8ac9-136">По мере того, как выполняется ситуация, легко добавлять новые custodians или выпускать custodians из этого случая.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-136">As the case progresses, it's easy to add new custodians or release custodians from the case.</span></span> <span data-ttu-id="f8ac9-137">Дополнительные сведения см. [в статье Working with custodians in Advanced eDiscovery](managing-custodians.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-137">For more information, see [Work with custodians in Advanced eDiscovery](managing-custodians.md).</span></span>

## <a name="managing-legal-hold-notifications"></a><span data-ttu-id="f8ac9-138">Управление уведомлениями о юридических удержаниях</span><span class="sxs-lookup"><span data-stu-id="f8ac9-138">Managing legal hold notifications</span></span>

<span data-ttu-id="f8ac9-139">Вкладка **связи** используется для управления процессом связи с custodians в случае.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-139">Use the **Communications** tab to manage the process of communicating with the custodians in the case.</span></span> <span data-ttu-id="f8ac9-140">Уведомление о юридическом удержании указывает, что custodians сохраняет все содержимое, которое относится к этому случаю.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-140">A legal hold notice instructs custodians to preserve any content that's relevant to the case.</span></span> <span data-ttu-id="f8ac9-141">Юридические команды должны иметь возможность отслеживать полученные уведомления о получении, чтении и подтверждении custodians.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-141">Legal teams must be able to track the notices that have been received, read, and acknowledged by custodians.</span></span> <span data-ttu-id="f8ac9-142">Рабочий процесс связи в Advanced eDiscovery позволяет создавать и отправлять исходные уведомления, напоминания, уведомления о выпусках и эскалации, если custodians не удается подтвердить уведомление об удержании.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-142">The communications workflow in Advanced eDiscovery allows you to create and send initial notifications, reminders, release notices, and escalations if custodians fail to acknowledge a hold notification.</span></span> <span data-ttu-id="f8ac9-143">Дополнительные сведения см в статье [Working with Communications In Advanced eDiscovery](managing-custodian-communications.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-143">For more information, see [Work with communications in Advanced eDiscovery](managing-custodian-communications.md).</span></span>

## <a name="managing-content-preservation"></a><span data-ttu-id="f8ac9-144">Управление сохранением содержимого</span><span class="sxs-lookup"><span data-stu-id="f8ac9-144">Managing content preservation</span></span>

<span data-ttu-id="f8ac9-145">При добавлении хранитель к случаю можно поместить удержание на данные кустодиал.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-145">When you add a custodian to a case, you can place a hold on custodial data.</span></span> <span data-ttu-id="f8ac9-146">Используйте вкладку **удержания** для управления удержанием, созданным при добавлении custodians, и управления другими юридическими удержаниями, связанными с обращением; Например, вы можете определить и разместить удержание на источниках данных, не являющихся кустодиал.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-146">Use the **Holds** tab to manage the hold created when you add custodians, and to manage other legal holds associated with the case; for example, you can identify and place a hold on non-custodial data sources.</span></span> <span data-ttu-id="f8ac9-147">Кроме того, можно изменить удержание в случае, чтобы сохранить только содержимое, которое соответствует запросу, с удержанием на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-147">You can also edit any hold in the case and make it a query-based hold to preserve only the content that matches the query.</span></span> <span data-ttu-id="f8ac9-148">Например, вы можете добавить диапазон дат в удержание, чтобы только содержимое, созданное в пределах указанной даты, в сохраненном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-148">For example, you could add a date range to the hold so that only content created within a specific date ranged in preserved.</span></span> <span data-ttu-id="f8ac9-149">Вы также можете получить статистику по контенту, который находится на удержании, удалить удержание после того, как оно больше не соответствует регистру, или удалить его.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-149">You can also get statistics on content that's on hold, remove the hold after it's no longer relevant to the case, or delete it.</span></span> <span data-ttu-id="f8ac9-150">Дополнительные сведения см в разделе [Manage удержания в Advanced eDiscovery](managing-holds.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-150">For more information, see [Manage holds in Advanced eDiscovery](managing-holds.md).</span></span>

## <a name="indexing-custodian-data"></a><span data-ttu-id="f8ac9-151">Индексирование данных хранитель</span><span class="sxs-lookup"><span data-stu-id="f8ac9-151">Indexing custodian data</span></span>

<span data-ttu-id="f8ac9-152">При добавлении хранитель и соответствующих источников данных кустодиал в случае все частично индексированные элементы из источника данных хранитель повторно индексируются процессом, который называется *расширенной индексацией*.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-152">When you add a custodian and the corresponding custodial data sources to a case, any partially indexed item from a custodian data source is re-indexed by a process called *Advanced indexing*.</span></span> <span data-ttu-id="f8ac9-153">Это позволяет полностью поддерживать поиск контента кустодиал, например изображений, неподдерживаемых типов файлов и другого потенциально неиндексированного контента, при выполнении поиска для сбора данных для обращения.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-153">This allows custodial content such as images, unsupported file types, and other potentially unindexed content to be fully searchable when you run searches to collect data for the case.</span></span> <span data-ttu-id="f8ac9-154">Используйте вкладку **Обработка** для отслеживания состояния расширенных ошибок индексирования и исправления с помощью процесса, который называется *исправлением ошибок*.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-154">Use the **Processing** tab to monitor the status of Advanced indexing and fix processing errors by using a process called *error remediation*.</span></span> <span data-ttu-id="f8ac9-155">Дополнительные сведения можно найти [в статье Устранение ошибок обработки в Advanced eDiscovery](processing-data-for-case.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-155">For more information, see [Fix processing errors in Advanced eDiscovery](processing-data-for-case.md).</span></span>

## <a name="collecting-case-data"></a><span data-ttu-id="f8ac9-156">Сбор данных дела</span><span class="sxs-lookup"><span data-stu-id="f8ac9-156">Collecting case data</span></span>

<span data-ttu-id="f8ac9-157">С помощью вкладки **поиски** можно создавать Поиск для поиска в кустодиал и других источниках данных, отличных от кустодиал, в Office 365 для контента, относящегося к этому случаю.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-157">Use the **Searches** tab to create searches to search the in-place custodial and non-custodial data sources in Office 365 for content relevant to the case.</span></span> <span data-ttu-id="f8ac9-158">Вы можете создавать и выполнять поиск на основе запросов (с помощью ключевых слов и условий), чтобы определить набор сообщений электронной почты и документов, которые соответствуют этому случаю, и что вы хотите проанализировать и проанализировать в ходе последующих шагов рабочего процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-158">You can create and run query-based searches (using keywords and conditions) to identify a set of email messages and documents that are relevant to the case and that you want to further review and analyze in subsequent steps in the eDiscovery workflow.</span></span> <span data-ttu-id="f8ac9-159">Можно создать один или несколько операций поиска, связанных с обращением.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-159">You can create one or more searches associated with the case.</span></span> <span data-ttu-id="f8ac9-160">Кроме того, вы можете использовать средство поиска для предварительного просмотра образцов документов и просмотра статистики поиска, чтобы упростить и улучшить результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-160">You can also use the search tool to preview sample documents and view search statistics to help you refine and improve the search results.</span></span> <span data-ttu-id="f8ac9-161">Когда вы удовлетворены результатами поиска, содержащие все данные, связанные с обращением, вы добавляете результаты поиска в набор проверки для дальнейшей проверки, анализа и отбора.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-161">After you're satisfied the search results contain the all data relevant to the case, you add the search results to a review set for further review, analysis, and culling.</span></span> <span data-ttu-id="f8ac9-162">Дополнительные сведения: [сбор данных для обращения в разделе Advanced eDiscovery](collecting-data-for-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-162">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

## <a name="reviewing-and-analyzing-case-data"></a><span data-ttu-id="f8ac9-163">Просмотр и анализ данных обращений</span><span class="sxs-lookup"><span data-stu-id="f8ac9-163">Reviewing and analyzing case data</span></span>

<span data-ttu-id="f8ac9-164">Вкладка " **Рецензирование** " используется для просмотра и анализа содержимого, собранного из системы Live и добавленного в набор рецензирования.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-164">Use the **Review sets** tab to review and analyze the content that you've collected from the live system and added to a review set.</span></span> <span data-ttu-id="f8ac9-165">*Набор проверки* представляет собой статическую коллекцию данных (другими словами, автономную копию данных) данных кустодиал (и, если это возможно, данные, не связанные с кустодиал), собранные на предыдущем этапе рабочего процесса обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-165">A *review set* is a static collection of that data (in other words, an offline copy of data) of custodial data (and if applicable, non-custodial data) that you collected in the previous phase of the eDiscovery workflow.</span></span> <span data-ttu-id="f8ac9-166">При добавлении результатов поиска в набор проверки запускается процесс, который извлекает файлы из контейнеров, извлекает метаданные и извлекает текст.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-166">When you add search results to a review set, a process is triggered that extracts files from containers, extracts metadata, and extracts text.</span></span> <span data-ttu-id="f8ac9-167">По завершении этого процесса система создает новый индекс всех данных, собранных из custodians, и добавляет их в набор проверки.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-167">When this process is complete, the system builds a new index of all the data collected from custodians and adds it to the review set.</span></span> <span data-ttu-id="f8ac9-168">После добавления данных в набор проверки можно выполнить дополнительные запросы для сужения данных регистра, просмотра данных в виде текста или в собственном формате файлов, а также для документов аннотирования, исправления и тегов в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-168">After the data is added to the review set, you can run more queries to narrow the case data, view data as text or in the native file format, and annotate, redact, and tag documents in the review set.</span></span> <span data-ttu-id="f8ac9-169">Кроме того, можно выполнить расширенную аналитику, например определить дублирование документов, почтовые потоки и темы.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-169">You can also perform advanced analytics such as identify document duplication, email threading, and themes.</span></span> <span data-ttu-id="f8ac9-170">После того как вы выдаете данные только о том, что относится к регистру, вы можете либо загрузить документы напрямую, либо экспортировать их вместе с метаданными файлов, примечаниями и любыми тегами.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-170">After you've culled the data to only what is relevant to the case, you can either download documents directly or export them along with file metadata, annotations, and any tags.</span></span> <span data-ttu-id="f8ac9-171">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="f8ac9-171">For more information, see:</span></span>

- [<span data-ttu-id="f8ac9-172">Просмотр данных обращения в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f8ac9-172">Review case data in Advanced eDiscovery</span></span>](reviewing-data-in-review-set.md)
- [<span data-ttu-id="f8ac9-173">Анализ данных в наборе анализа в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f8ac9-173">Analyze data in a review set in Advanced eDiscovery</span></span>](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a><span data-ttu-id="f8ac9-174">Экспорт данных для проверки и представления</span><span class="sxs-lookup"><span data-stu-id="f8ac9-174">Exporting data for review and presentation</span></span>

<span data-ttu-id="f8ac9-175">После экспорта данных из набора проверки используйте вкладку **экспорты** для управления заданием экспорта и загрузки данных из набора рецензирования.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-175">After you export the data from a review set, use the **Exports** tab to manage an export job and download data from a review set.</span></span> <span data-ttu-id="f8ac9-176">При экспорте набора проверки данные передаются в место хранения Azure и доступны для загрузки на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-176">When you export a review set, the data is uploaded to an Azure storage location and then is available to download to a local computer.</span></span> <span data-ttu-id="f8ac9-177">Вы можете получить ключ оценки хранения, необходимый для скачивания экспортированных данных на вкладке " **Экспорт** ". Дополнительные сведения см в разделе [Export Data Case in Advanced eDiscovery](exporting-data-ediscover20.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-177">You can obtain the storage assess key necessary to download the exported data on the **Exports** tab. For more information, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>

## <a name="managing-jobs"></a><span data-ttu-id="f8ac9-178">Управление заданиями</span><span class="sxs-lookup"><span data-stu-id="f8ac9-178">Managing jobs</span></span>

<span data-ttu-id="f8ac9-179">Используйте вкладку **задания** для отслеживания длительно выполняемых процессов для задач, связанных с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-179">Use the **Jobs** tab to monitor long-running processes for case-related tasks that you've initiated.</span></span> <span data-ttu-id="f8ac9-180">Примеры заданий включают задачи, связанные с переиндексацией, поиском и экспортом данных о делах.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-180">Examples of jobs include ones related to reindexing, searching, and exporting case data.</span></span> <span data-ttu-id="f8ac9-181">Например, если вы создадите Поиск на вкладке **поиски** , содержащую множество источников данных, состояние этого процесса поиска будет отображаться на вкладке **задания** . Дополнительные сведения см в разделе [Управление заданиями в Advanced eDiscovery](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="f8ac9-181">For example, if you create a search on the **Searches** tab that includes many data sources, the status of this search process will be displayed on the **Jobs** tab. For more information, see [Manage jobs in Advanced eDiscovery](managing-jobs-ediscovery20.md).</span></span>

## <a name="configuring-case-settings"></a><span data-ttu-id="f8ac9-182">Настройка параметров регистра</span><span class="sxs-lookup"><span data-stu-id="f8ac9-182">Configuring case settings</span></span>

<span data-ttu-id="f8ac9-183">С помощью вкладки **Параметры** можно настроить параметры на уровне всего в наличии.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-183">Use the **Settings** tab to configure case-wide settings.</span></span> <span data-ttu-id="f8ac9-184">Это включает в себя добавление элементов к случаю, закрытие или удаление обращения, а также настройку параметров поиска и аналитики.</span><span class="sxs-lookup"><span data-stu-id="f8ac9-184">This includes adding members to a case, closing or deleting a case, and configuring search and analytics settings.</span></span>