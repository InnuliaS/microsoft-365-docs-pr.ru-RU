---
title: Управление инцидентом переноса данных в Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: В этой статье описывается использование нового средства расследования данных (Предварительная версия) в центре безопасности & соответствия требованиям для управления инцидентом с продолжением данных.
ms.openlocfilehash: 53193d3bd915562037a6409766e9be9d42d272c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090423"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="b9a3b-103">Управление инцидентом переноса данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9a3b-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="b9a3b-104">Почтовые данные зависят от того, что в ненадежной среде размещается документ, содержащий конфиденциальную, конфиденциальную или вредоносную информацию.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-104">Data spillage is when a document containing confidential, sensitive, or malicious information is released in an untrusted environment.</span></span> <span data-ttu-id="b9a3b-105">При обнаружении инцидента с продолжением прохождения данных важно быстро включить среду, оценить размер и расположение удаляемого, проанализировать действия пользователей, а затем удалить перенесенные данные из службы.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="b9a3b-106">С помощью средства расследования данных (Preview) можно искать конфиденциальные, опасные или перемещенные данные в Office 365, проверить, что произошло, а затем предпринять соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious, or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="b9a3b-107">Область действия этой статьи</span><span class="sxs-lookup"><span data-stu-id="b9a3b-107">Scope of this article</span></span>

<span data-ttu-id="b9a3b-108">В этой статье представлен список инструкций по удалению элементов из почтовых ящиков Office 365, чтобы они были недоступны пользователям и администраторам.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9a3b-109">При удалении элементов, расположенных на сайте SharePoint или OneDrive для бизнеса, они сохраняются в течение 93 дней с момента их удаления из исходной папки.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="b9a3b-110">Сценарий</span><span class="sxs-lookup"><span data-stu-id="b9a3b-110">Scenario</span></span>

<span data-ttu-id="b9a3b-111">Вы сообщаете об инциденте прокрутки данных, когда сотрудник неизвестен строго конфиденциальному документу с несколькими людьми через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-111">You're informed of a data spillage incident where an employee unknowingly shared a highly confidential document with multiple people through email.</span></span> <span data-ttu-id="b9a3b-112">Вы хотите быстро оценить, кто получил этот документ как внутри организации, так и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="b9a3b-113">После изучения инцидента вы планируете поделиться своими сведениями с другими исследованиями, чтобы проверить, а затем окончательно удалить перенесенные данные из вашей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="b9a3b-114">После завершения расследования необходимо удалить все доказательства.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b9a3b-115">Несмотря на то, что вы сможете окончательно удалить перенесенные данные в своей организации, все данные, проходящие за пределы организации, невозможно удалить с помощью этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="b9a3b-116">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="b9a3b-116">Workflow</span></span>

<span data-ttu-id="b9a3b-117">Ниже показан рабочий процесс для использования расследования данных (Предварительная версия) для управления инцидентом продолженности данных:</span><span class="sxs-lookup"><span data-stu-id="b9a3b-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="b9a3b-118">Создание расследования данных.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="b9a3b-119">Поиск конфиденциальных, вредоносных или перемещенных данных и их сбор в качестве свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="b9a3b-120">Просмотрите и изучите свидетельство.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="b9a3b-121">Удаление перенесенных данных без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="b9a3b-122">Закройте или удалите расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="b9a3b-123">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b9a3b-123">Before you begin</span></span>

- <span data-ttu-id="b9a3b-124">Чтобы создать анализ данных, искать контент и удалять перенесенные данные, необходимо быть членом группы ролей Data Инвестигатор в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-124">To create a data investigation, search for content, and delete spilled data, you have to be a member of the Data Investigator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="b9a3b-125">Чтобы определить, какие почтовые ящики пользователей и учетные записи OneDrive могут выполнять поиск в инвестигатор, ваша организация может настроить границы соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-125">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="b9a3b-126">Для получения дополнительных сведений [Настройте границы соответствия требованиям для исследований обнаружения электронных](tagging-and-assessment-in-advanced-ediscovery.md)данных.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-126">For more information, [Set up compliance boundaries for eDiscovery investigations](tagging-and-assessment-in-advanced-ediscovery.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="b9a3b-127">Шаг 1: создание расследования данных</span><span class="sxs-lookup"><span data-stu-id="b9a3b-127">Step 1: Create a data investigation</span></span>

<span data-ttu-id="b9a3b-128">Чтобы создать расследования в средстве расследования данных (Preview), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-128">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="b9a3b-129">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-129">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="b9a3b-130">Войдите в Office 365 с помощью учетной записи, которая является членом группы ролей Data Инвестигатор.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-130">Sign in to Office 365 using an account that is a member of the Data Investigator role group.</span></span>
    
3. <span data-ttu-id="b9a3b-131">В центре безопасности и соответствия требованиям выберите **расследования данных**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-131">In the security and compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="b9a3b-132">На странице **расследования данных (Предварительная версия)** нажмите кнопку **создать новое исследование**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-132">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="b9a3b-133">В раскрывающейся окне **Новое исследование данных** укажите имя (обязательно), а затем введите дополнительный номер исследования и описание.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-133">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="b9a3b-134">Имя должно быть уникальным в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-134">The name must be unique in your organization.</span></span>

6. <span data-ttu-id="b9a3b-135">В разделе **вы хотите настроить дополнительные параметры после создания этого расследования?** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-135">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="b9a3b-136">Нажмите кнопку **Да** , чтобы создать расследования, и отобразите страницу **Параметры** в новом случае.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-136">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="b9a3b-137">Это позволяет добавлять участников в исследование.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-137">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="b9a3b-138">Нажмите кнопку **нет** , чтобы создать исследование и отобразить его в списке обращений на странице **расследования данных (Предварительная версия)** .</span><span class="sxs-lookup"><span data-stu-id="b9a3b-138">Click **No** to create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="b9a3b-139">Если выбран этот параметр, вы будете добавлены только в качестве единственного участника расследования и будут использоваться параметры поиска и аналитики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-139">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="b9a3b-140">Вы можете добавлять участников или изменять параметры в любое время после создания расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-140">You can add members or change settings anytime after the investigation is created.</span></span>

7. <span data-ttu-id="b9a3b-141">Нажмите кнопку **сохранить** , чтобы создать расследование.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-141">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="b9a3b-142">Новое исследование отображается в списке на странице **расследования данных (Предварительная версия)** .</span><span class="sxs-lookup"><span data-stu-id="b9a3b-142">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="b9a3b-143">Чтобы открыть исследование, щелкните имя расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-143">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="b9a3b-144">Отображается вкладка **Главная** для расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-144">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="b9a3b-145">Рекомендуется установить соглашение об именовании для расследования и предоставить как можно больше сведений, как в имени и описании, чтобы вы могли найти их в будущем, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-145">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to them in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="b9a3b-146">Шаг 2: Поиск перенесенных данных</span><span class="sxs-lookup"><span data-stu-id="b9a3b-146">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="b9a3b-147">Если вы знаете, какие пользователи будут искать перенесенные данные, вы можете добавить их в качестве интересующих пользователей, чтобы сопоставить их источники данных с расследованиями и быстро найти их почтовые ящики и учетную запись OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-147">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="b9a3b-148">Чтобы добавить людей, интересующих расследования, выберите **интересующих**людей, а затем нажмите кнопку **добавить людей**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-148">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="b9a3b-149">Дополнительные сведения можно найти в разделе [Manage People People](manage-people-of-interest.md).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-149">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="b9a3b-150">На вкладке **поиски** можно создать поиск, чтобы найти перенесенные данные.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-150">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="b9a3b-151">Дополнительные сведения о создании поисковых данных можно найти [в статье Поиск данных при расследовании](search-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-151">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="b9a3b-152">После выполнения поиска вы можете просмотреть образцы результатов поиска и просмотреть статистику поиска, чтобы оценить Эффективность поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-152">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="b9a3b-153">После определения элементов, которые требуется удалить из Office 365, можно добавить результаты поиска в набор свидетельств.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-153">After you identify the items that you want to delete from Office 365, you can add the search results to an evidence set.</span></span> <span data-ttu-id="b9a3b-154">Для этого щелкните Поиск, который нужно исследовать.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-154">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="b9a3b-155">На всплывающей странице щелкните **Добавить результаты в доказательства** и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-155">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="b9a3b-156">Затем в наборе свидетельств можно просмотреть отдельные документы, выяснить, кто имел доступ к документам, и экспортировать документы.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-156">Then in the evidence set, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="b9a3b-157">Чтобы удалить документы (или подмножество документов), а не просматривать их, перейдите к [шагу 4](#step-4-delete-the-spilled-data).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-157">To delete the documents (or a subset of documents) instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b9a3b-158">Ключевые слова, которые вы используете в поисковом запросе, могут содержать данные, которые вы ищете.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-158">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="b9a3b-159">Например, если вы ищете документы, содержащие номер социального страхования, и хотите использовать его в качестве ключевого слова в поисковых запросах, необходимо удалить запрос, чтобы избежать появления дополнительной системы.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-159">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="b9a3b-160">Вы можете удалить Поиск или удалить весь процесс расследования на [шаге 5](#step-5-close-or-delete-the-investigation).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-160">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="b9a3b-161">Шаг 3: Проверка и исследование</span><span class="sxs-lookup"><span data-stu-id="b9a3b-161">Step 3: Review and investigate</span></span> 

<span data-ttu-id="b9a3b-162">При расследовании перейдите на вкладку **свидетельство** и щелкните набор свидетельств, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-162">In the investigation, go to the **Evidence** tab and click the evidence set that you created in the previous step.</span></span> <span data-ttu-id="b9a3b-163">После завершения задания обработки и добавления результатов поиска к свидетельству можно просмотреть отдельные документы в собственном формате, в текстовом формате или в близком формате.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-163">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="b9a3b-164">Вы можете создавать дополнительные запросы для сужения списка документов и тегов документов, чтобы обозначить результаты расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-164">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="b9a3b-165">Дополнительные сведения см в разделе [Просмотр данных в доказательстве](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="b9a3b-165">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="b9a3b-166">Для группировки документов и получения дополнительной помощи по проверке нажмите кнопку **Управление доказательствами**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-166">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="b9a3b-167">В плитке **аналитика** щелкните **анализ**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-167">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="b9a3b-168">При этом запускается Расширенная аналитика, например поиск повторяющихся данных, почтовые потоки и анализ темы.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-168">This runs advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="b9a3b-169">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b9a3b-169">For more information, see:</span></span>

- [<span data-ttu-id="b9a3b-170">Запуск аналитики для ускорения исследования</span><span class="sxs-lookup"><span data-stu-id="b9a3b-170">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="b9a3b-171">Обнаружение схожих документов (почти дубликатов)</span><span class="sxs-lookup"><span data-stu-id="b9a3b-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="b9a3b-172">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="b9a3b-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="b9a3b-173">Темы</span><span class="sxs-lookup"><span data-stu-id="b9a3b-173">Themes</span></span>](themes.md)

<span data-ttu-id="b9a3b-174">Чтобы определить, какие пользователи участвуют в проводе данных, можно создать запрос в наборе свидетельств, а затем использовать условия отправителя/автора и получателей.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-174">To determine which users are involved in the data spillage, you can create a query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="b9a3b-175">При этом будет создан список всех отправителей, получателей и авторов, обнаруженных в собранных данных, которые были добавлены в свидетельство.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-175">This creates a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="b9a3b-176">Обязательно изучите список, чтобы определить, есть ли у вас внешние пользователи.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-176">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="b9a3b-177">Более подробную информацию об использовании условий для сужения результатов поиска можно узнать в статье [условия поиска](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-177">For more information about using conditions to narrow search results, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="b9a3b-178">Шаг 4: удаление перенесенных данных</span><span class="sxs-lookup"><span data-stu-id="b9a3b-178">Step 4: Delete the spilled data</span></span>

<span data-ttu-id="b9a3b-179">С помощью средства анализа данных можно удалять элементы из их исходных расположений.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-179">Using the data investigations tool, you can delete items from their original locations.</span></span> <span data-ttu-id="b9a3b-180">Например, вы можете удалять элементы из почтовых ящиков, сайтов SharePoint и учетных записей OneDrive в Организации.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-180">For example, you can delete items from mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="b9a3b-181">Имейте в виду, что если вы собрали элементы в качестве свидетельства (добавив результаты поиска в набор свидетельств на шаге 2), у вас есть копии элементов в наборе свидетельств для дальнейшего анализа или сохранения.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-181">Keep in mind that because you collected items as evidence (by adding the search results to the evidence set in Step 2), you have copies of the items in the evidence set to further investigate or preserve them.</span></span>

<span data-ttu-id="b9a3b-182">Чтобы удалить элементы из их исходных расположений:</span><span class="sxs-lookup"><span data-stu-id="b9a3b-182">To delete items from their original locations:</span></span>

1. <span data-ttu-id="b9a3b-183">В наборе свидетельств выберите элементы, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-183">In the evidence set, select the items that you want to delete.</span></span> <span data-ttu-id="b9a3b-184">При выборе элементов, вложенных в сообщение электронной почты, родительское электронное сообщение также будет выбрано и удалено.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-184">If you select items that are attached to an email message, the parent email message will also be selected and deleted.</span></span> 
 
2. <span data-ttu-id="b9a3b-185">Щелкните **действие** , а затем щелкните **удалить элементы из исходных расположений**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-185">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![Щелкните действие, а затем выберите команду Удалить элементы из исходных расположений.](media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="b9a3b-187">На всплывающей странице проверьте количество элементов и связанных дочерних документов, которые будут удалены, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-187">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

<span data-ttu-id="b9a3b-188">В настоящее время при удалении элементов из исходного расположения элементы будут обратимо удалены.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-188">At this time, when you delete items from their original location, the items are soft-deleted.</span></span> <span data-ttu-id="b9a3b-189">Это означает, что удаленные элементы будут храниться до тех пор, пока не истечет срок действия элемента для восстановления удаленного элемента.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-189">This means that the deleted items will be retained until the deleted item recovery period for the item expires.</span></span> <span data-ttu-id="b9a3b-190">Это также означает, что пользователи могут восстановить эти элементы.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-190">This also means it's possible for users to recover these items.</span></span> <span data-ttu-id="b9a3b-191">Дополнительные сведения о том, что происходит при удалении элементов из почтовых ящиков и сайтов, можно узнать [в статье Удаление элементов из исходного расположения](delete-items-from-original-locations.md).</span><span class="sxs-lookup"><span data-stu-id="b9a3b-191">For more information about what happens when items are deleted from mailboxes and sites, see [Delete items from their original location](delete-items-from-original-locations.md).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="b9a3b-192">Шаг 5: закрытие или удаление расследования</span><span class="sxs-lookup"><span data-stu-id="b9a3b-192">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="b9a3b-193">После удаления документов из исходных расположений содержимого (почтовые ящики или сайты) в действующей службе все равно будут по-прежнему иметь копии этих документов, добавленные к доказательствам в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-193">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="b9a3b-194">Чтобы избежать появления дополнительной информации, рекомендуется удалить само исследование.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-194">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="b9a3b-195">Удаление расследования:</span><span class="sxs-lookup"><span data-stu-id="b9a3b-195">To delete an investigation:</span></span>

1. <span data-ttu-id="b9a3b-196">На вкладке **Параметры** выберите **сведения об исследовании**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-196">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="b9a3b-197">Нажмите кнопку **Удалить расследования**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-197">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="b9a3b-198">Если вы не хотите удалять расследования или вы хотите сохранить данные, собранные в ходе расследования, нажмите кнопку **Закрыть сценарий**.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-198">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="b9a3b-199">Затем вы можете повторно открыть закрытое расследование.</span><span class="sxs-lookup"><span data-stu-id="b9a3b-199">Then later, you can reopen closed investigations.</span></span>