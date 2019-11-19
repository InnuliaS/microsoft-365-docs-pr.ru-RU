---
title: Защита файлов в командах с помощью меток хранения и политики защиты от потери данных
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: Сводка. Применяйте метки хранения и политики защиты от потери данных для файлов в командах с различными уровнями защиты информации.
ms.openlocfilehash: 89320a074d5d52062268a7585081849ac42d2025
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925865"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="7f6d2-103">Защита файлов в командах с помощью меток хранения и политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="7f6d2-103">Protect SharePoint Online files with retention labels and DLP</span></span>

 
<span data-ttu-id="7f6d2-104">В этой статье приводятся инструкции по разработке и развертыванию меток хранения и политик защиты от потери данных для команд с базовым, конфиденциальным и строго конфиденциальным уровнями защиты, а также их базовых сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="7f6d2-105">Дополнительные сведения об этих трех уровнях защиты см. в статье [Защита файлов в Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7f6d2-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="7f6d2-106">Как это работает</span><span class="sxs-lookup"><span data-stu-id="7f6d2-106">How this works</span></span>

1. <span data-ttu-id="7f6d2-107">Создайте нужные метки хранения и опубликуйте их.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="7f6d2-108">Для их публикации может потребоваться до 12 часов.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="7f6d2-109">Для нужных базовых сайтов SharePoint измените параметры библиотеки документов, чтобы присвоить желаемые метки хранения элементам в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="7f6d2-110">Создайте политики защиты от потери данных, чтобы выполнять действия на основе меток хранения.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="7f6d2-111">Когда пользователи добавляют документ в библиотеку базового сайта SharePoint команды, этот документ получает назначенную метку хранения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="7f6d2-112">При необходимости пользователи могут изменить метку.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-112">Users can change the label, if needed.</span></span> <span data-ttu-id="7f6d2-113">Если пользователь делится документом за пределами организации, служба защиты от потери данных проверяет, назначена ли метка, и выполняет действия, если политика защиты от потери данных соответствует метке.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="7f6d2-114">Служба защиты от потери данных также проверяет соответствие другим политикам, таким как защита файлов с номерами кредитных карт, если этот тип политики настроен.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7f6d2-115">Метки хранения для базовых сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="7f6d2-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="7f6d2-116">Существует три этапа создания и назначения меток хранения для базовых сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="7f6d2-117">Этап 1. Определение имен меток хранения</span><span class="sxs-lookup"><span data-stu-id="7f6d2-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="7f6d2-118">На этом этапе нужно определить имена меток хранения для четырех уровней защиты информации, применяемых к базовым сайтам SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="7f6d2-119">В следующей таблице перечислены рекомендуемые имена для каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="7f6d2-120">**Уровень защиты базовых сайтов SharePoint**</span><span class="sxs-lookup"><span data-stu-id="7f6d2-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="7f6d2-121">**Имя метки**</span><span class="sxs-lookup"><span data-stu-id="7f6d2-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f6d2-122">Базовый общедоступный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="7f6d2-123">Внутренний общедоступный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="7f6d2-124">Базовый частный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="7f6d2-125">Частный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-125">Private</span></span>  <br/> |
|<span data-ttu-id="7f6d2-126">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-126">Sensitive</span></span>  <br/> |<span data-ttu-id="7f6d2-127">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="7f6d2-128">Строго конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="7f6d2-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="7f6d2-129">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="7f6d2-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="7f6d2-130">Этап 2. Создание меток хранения</span><span class="sxs-lookup"><span data-stu-id="7f6d2-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="7f6d2-131">На этом этапе нужно создать и опубликовать определенные метки для разных уровней защиты информации.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="7f6d2-132">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7f6d2-133">На вкладке **Главная — соответствие требованиям Microsoft 365** в браузере выберите пункты **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7f6d2-134">Щелкните **Метки хранения > Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7f6d2-135">В области **Назовите метку** введите название метки и описание для администраторов и пользователей, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="7f6d2-136">В области **Дескрипторы плана хранения** введите необходимые параметры и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f6d2-137">В области **Параметры метки** при необходимости установите параметр **Хранение** в положение **Вкл.** и настройте параметры хранения.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="7f6d2-138">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="7f6d2-139">В области **Проверьте параметры** нажмите кнопку **Создать эту метку**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7f6d2-140">Для создания дополнительных меток нажмите кнопку **Создать метку** и повторите нужные действия с 3 по 7, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="7f6d2-141">Публикация новых меток</span><span class="sxs-lookup"><span data-stu-id="7f6d2-141">Publish your new labels</span></span>

<span data-ttu-id="7f6d2-142">Для публикации новых меток хранения выполните действия, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="7f6d2-143">В области **Метки** щелкните вкладку **Метки хранения** и нажмите кнопку **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="7f6d2-144">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="7f6d2-145">В области **Выбор меток** нажмите кнопку **Добавить**, выберите все четыре метки и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="7f6d2-146">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="7f6d2-147">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7f6d2-148">В области **Выбор расположений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="7f6d2-149">В области **Назовите политику** введите название для своего набора меток в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7f6d2-150">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="7f6d2-151">Этап 3. Применение меток хранения к базовым сайтам SharePoint</span><span class="sxs-lookup"><span data-stu-id="7f6d2-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="7f6d2-152">Ниже приведены инструкции по применению меток хранения к папкам документов, размещенным на базовых сайтах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1.  <span data-ttu-id="7f6d2-153">В интерфейсе команды нажмите **Файлы**, а затем **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="7f6d2-154">На новой вкладке SharePoint в браузере щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="7f6d2-155">Щелкните значок параметров, а затем **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="7f6d2-156">В разделе **Разрешения и управление** нажмите **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="7f6d2-157">В разделе **Параметры — применение метки** выберите соответствующую метку хранения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="7f6d2-158">Закройте вкладку сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-158">Close the tab for the SharePoint Online site.</span></span>
    
7. <span data-ttu-id="7f6d2-159">Повторите шаги со 1 по 6, чтобы назначить метки хранения для дополнительных базовых сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-159">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="7f6d2-160">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-160">Here is your resulting configuration.</span></span>
  
![Метки хранения для четырех типов базовых сайтов SharePoint.](../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7f6d2-162">Политики защиты от потери данных для базовых сайтов SharePoint</span><span class="sxs-lookup"><span data-stu-id="7f6d2-162">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="7f6d2-163">Выполните указанные ниже действия, чтобы настроить политику защиты от потери данных, которая уведомляет пользователей, когда они предоставляют доступ к документу с базового сайта SharePoint пользователям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-163">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="7f6d2-164">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com/), используя учетную запись с ролью администратора компании или администратора безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7f6d2-165">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="7f6d2-166">В области **Главная > Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="7f6d2-167">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7f6d2-168">В области **Назовите политику** введите название для политики защиты от потери конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f6d2-169">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7f6d2-170">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7f6d2-171">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="7f6d2-172">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="7f6d2-173">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="7f6d2-174">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7f6d2-175">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="7f6d2-176">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7f6d2-177">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7f6d2-178">В текстовом поле введите или вставьте один из советов, приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-178">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="7f6d2-p106">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="7f6d2-p107">Строго конфиденциальные файлы защищены с помощью шифрования. Их могут просматривать только те внешние пользователи, которым ваш ИТ-отдел предоставил разрешения для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="7f6d2-184">Вы также можете ввести или вставить собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7f6d2-185">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="7f6d2-186">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="7f6d2-187">В области **Вы хотите включить политику или сначала проверить, как все работает?** выберите пункт **Да, включить сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7f6d2-188">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7f6d2-189">Здесь показана итоговая конфигурация для конфиденциальных команд.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-189">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для конфиденциальной команды с использованием метки хранения "Конфиденциальный"](../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="7f6d2-191">После этого выполните указанные ниже действия, чтобы настроить политику защиты от потери данных, которая блокирует пользователей, когда они предоставляют доступ к документу с базового сайта SharePoint пользователям за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="7f6d2-192">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="7f6d2-193">В области **Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="7f6d2-194">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="7f6d2-195">В области **Назовите политику** введите название для политики защиты от потери строго конфиденциальных данных в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7f6d2-196">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7f6d2-197">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7f6d2-198">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="7f6d2-199">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="7f6d2-200">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Строго конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="7f6d2-201">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7f6d2-202">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="7f6d2-203">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7f6d2-204">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7f6d2-205">В текстовом поле введите или вставьте следующее:</span><span class="sxs-lookup"><span data-stu-id="7f6d2-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="7f6d2-p108">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="7f6d2-209">Вы также можете ввести или вставить, скопировав, собственную подсказку политики, которая укажет пользователям, как делиться файлом с людьми за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7f6d2-210">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="7f6d2-211">В разделе **Обнаружение случаев разовой отправки определенного объема конфиденциальных данных** области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Ограничение доступа или шифрование содержимого** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="7f6d2-212">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7f6d2-213">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7f6d2-214">Ниже показана итоговая конфигурация для команд со строго конфиденциальным уровнем защиты.</span><span class="sxs-lookup"><span data-stu-id="7f6d2-214">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Политика защиты от потери данных для строго конфиденциальной команды с использованием метки хранения "Строго конфиденциальный"](../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="7f6d2-216">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7f6d2-216">Next step</span></span>

[<span data-ttu-id="7f6d2-217">Защита файлов в командах с помощью меток конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="7f6d2-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="7f6d2-218">См. также</span><span class="sxs-lookup"><span data-stu-id="7f6d2-218">See Also</span></span>

[<span data-ttu-id="7f6d2-219">Защита файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f6d2-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="7f6d2-220">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="7f6d2-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)

