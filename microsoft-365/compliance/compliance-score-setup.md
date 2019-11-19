---
title: Настройка оценки соответствия требованиям корпорации Майкрософт
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Сведения о том, как выполнить вход, настроить разрешения и понять вашу информационную панель для оценки соответствия требованиям корпорации Майкрософт, которая упрощает и автоматизирует оценку риска.
ms.openlocfilehash: 8c9bc7d1605bad66228bb47de8f86042839ac5be
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "38687315"
---
# <a name="microsoft-compliance-score-setup-preview"></a><span data-ttu-id="4fe95-103">Настройка оценки соответствия требованиям Майкрософт (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="4fe95-103">Microsoft Compliance Score setup (Preview)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4fe95-104">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="4fe95-104">Before you begin</span></span>

<span data-ttu-id="4fe95-105">Глобальный администратор Microsoft 365 для Организации, скорее всего, будет первым пользователем для доступа к рейтингу соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="4fe95-106">Мы рекомендуем глобальному администратору войти и настроить разрешения пользователей, как описано ниже, при первом посещении оценки соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="4fe95-107">Вход</span><span class="sxs-lookup"><span data-stu-id="4fe95-107">Sign in</span></span>

1. <span data-ttu-id="4fe95-108">Перейдите в [центр соответствия требованиям microsoft 365](https://compliance.microsoft.com/) и **Войдите в** систему с помощью учетной записи глобального администратора Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="4fe95-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="4fe95-109">Выберите **оценку соответствия** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="4fe95-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="4fe95-110">После этого вы увидите [панель мониторинга оценки соответствия требованиям](#understand-the-compliance-score-dashboard).</span><span class="sxs-lookup"><span data-stu-id="4fe95-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="4fe95-111">Настройка разрешений пользователей и назначение ролей</span><span class="sxs-lookup"><span data-stu-id="4fe95-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="4fe95-112">Оценка соответствия использует модель разрешений управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4fe95-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="4fe95-113">Только пользователи, которым назначена роль, могут получить доступ к показателю соответствия требованиям, а действия, разрешенные каждым пользователем, ограничиваются типом роли.</span><span class="sxs-lookup"><span data-stu-id="4fe95-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="4fe95-114">Место для задания разрешений</span><span class="sxs-lookup"><span data-stu-id="4fe95-114">Where to set permissions</span></span>

<span data-ttu-id="4fe95-115">Глобальный администратор организации может устанавливать разрешения пользователей в центре соответствия требованиям Microsoft 365 или Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4fe95-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="4fe95-116">После настройки ролей в любом из этих расположений пользователи смогут получить доступ к показателю соответствия требованиям (а также к диспетчеру соответствия требованиям).</span><span class="sxs-lookup"><span data-stu-id="4fe95-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="4fe95-117">Обратите внимание, что существующие роли диспетчера соответствия требованиям **не** переносятся на уровень соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="4fe95-118">Это означает, что если вы ранее назначили роль в диспетчере соответствия требованиям, эта роль не предоставит вам доступ к показателю соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="4fe95-119">Глобальному администратору потребуется задать разрешения и роль для вас в центре соответствия требованиям Microsoft 365 или Azure AD, чтобы получить доступ к рейтингу соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="4fe95-120">Типы ролей</span><span class="sxs-lookup"><span data-stu-id="4fe95-120">Role types</span></span>

<span data-ttu-id="4fe95-121">В приведенной ниже таблице показано, как каждая роль центра соответствия требованиям Microsoft 365 соответствует существующим ролям диспетчера соответствия требованиям и функциям, допускаемым каждой ролью.</span><span class="sxs-lookup"><span data-stu-id="4fe95-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="4fe95-122">Пользователь может:</span><span class="sxs-lookup"><span data-stu-id="4fe95-122">User can:</span></span> | <span data-ttu-id="4fe95-123">Роль центра соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4fe95-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="4fe95-124">Роль диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="4fe95-125">**Чтение, но не изменение данных**</span><span class="sxs-lookup"><span data-stu-id="4fe95-125">**Read but not edit data**</span></span>| <span data-ttu-id="4fe95-126">Глобальный читатель Azure AD</span><span class="sxs-lookup"><span data-stu-id="4fe95-126">Azure AD global reader</span></span>  | <span data-ttu-id="4fe95-127">Глобальный читатель Azure AD</span><span class="sxs-lookup"><span data-stu-id="4fe95-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="4fe95-128">**Чтение, но не изменение данных**</span><span class="sxs-lookup"><span data-stu-id="4fe95-128">**Read but not edit data**</span></span>| <span data-ttu-id="4fe95-129">Читатель безопасности</span><span class="sxs-lookup"><span data-stu-id="4fe95-129">Security reader</span></span> | <span data-ttu-id="4fe95-130">Средство чтения диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="4fe95-131">**Изменение данных**</span><span class="sxs-lookup"><span data-stu-id="4fe95-131">**Edit data**</span></span>| <span data-ttu-id="4fe95-132">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-132">Compliance administrator</span></span> | <span data-ttu-id="4fe95-133">Участник диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="4fe95-134">**Изменение результатов теста**</span><span class="sxs-lookup"><span data-stu-id="4fe95-134">**Edit test results**</span></span>| <span data-ttu-id="4fe95-135">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-135">Compliance administrator</span></span> | <span data-ttu-id="4fe95-136">Оценка диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="4fe95-137">**Управление оценками и данными шаблонов и клиентов**</span><span class="sxs-lookup"><span data-stu-id="4fe95-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="4fe95-138">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-138">Compliance administrator</span></span><br><span data-ttu-id="4fe95-139">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-139">Compliance data administrator</span></span><br><span data-ttu-id="4fe95-140">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="4fe95-140">Security administrator</span></span> | <span data-ttu-id="4fe95-141">Администратор диспетчера соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="4fe95-142">**Назначение пользователей**</span><span class="sxs-lookup"><span data-stu-id="4fe95-142">**Assign users**</span></span>| <span data-ttu-id="4fe95-143">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="4fe95-143">Global administrator</span></span> | <span data-ttu-id="4fe95-144">Администратор портала</span><span class="sxs-lookup"><span data-stu-id="4fe95-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="4fe95-145">При переходе от оценки соответствия требованиям к диспетчеру соответствия требованиям для выполнения задачи (например, для управления оценкой) браузер открывает новую вкладку и откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="4fe95-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="4fe95-146">В верхнем разделе с заголовком "уже есть клиент облачных служб Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="4fe95-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="4fe95-147">Войдите в свою учетную запись "выберите **Вход** в систему для доступа к диспетчеру соответствия требованиям; Вам не нужно будет повторно вводить свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="4fe95-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4fe95-148">Настройка разрешений и ролей в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4fe95-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="4fe95-149">Чтобы задать разрешения в центре соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4fe95-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="4fe95-150">Перейдите в [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com) и войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="4fe95-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="4fe95-151">Выберите **разрешения** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="4fe95-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="4fe95-152">Отсюда вы можете просматривать роли и назначать разрешения.</span><span class="sxs-lookup"><span data-stu-id="4fe95-152">From here, you can view roles and assign permissions.</span></span>

<span data-ttu-id="4fe95-153">Сведения о том, как читать [роли и разрешения в центре соответствия требованиям Microsoft 365](../security/office-365-security/microsoft-security-and-compliance.md#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="4fe95-153">For details, read [roles and permissions in the Microsoft 365 compliance center](../security/office-365-security/microsoft-security-and-compliance.md#required-licenses-and-permissions).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="4fe95-154">Общие сведения о панели мониторинга оценки соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-154">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="4fe95-155">Панель мониторинга "Оценка соответствия требованиям" предназначена для того, чтобы предоставить вам наглядный вид текущей оценки соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-155">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="4fe95-156">![Оценка соответствия требованиям — панель мониторинга](media/compliance-score-dashboard.png "Панель мониторинга оценки соответствия требованиям")</span><span class="sxs-lookup"><span data-stu-id="4fe95-156">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="4fe95-157">Общий показатель соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-157">Overall compliance score</span></span>

<span data-ttu-id="4fe95-158">Ваш рейтинг соответствия требованиям, который, как видно вверху, показывает процентное отношение на основе баллов, достижимых для выполнения действий по улучшению. стандарты и нормативы по защите данных.</span><span class="sxs-lookup"><span data-stu-id="4fe95-158">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span> 

<span data-ttu-id="4fe95-159">Когда вы впервые переходите к показателю соответствия требованиям, Исходная оценка основана на встроенном базовом стандарте защиты данных Microsoft 365 — наборе элементов управления, которые включают в себя распространенные отраслевые нормы и стандарты.</span><span class="sxs-lookup"><span data-stu-id="4fe95-159">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="4fe95-160">Так как оценка соответствия требованиям сканирует систему существующих решений Microsoft 365, она предоставляет начальную оценку уровня соответствия требованиям, основанную на параметрах конфиденциальности и безопасности, которые в настоящее время включены вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="4fe95-160">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="4fe95-161">При добавлении оценок, относящихся к вашей организации, баллы становятся еще более осмысленными.</span><span class="sxs-lookup"><span data-stu-id="4fe95-161">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="4fe95-162">Узнайте больше о [способе вычисления оценки](compliance-score-methodology.md).</span><span class="sxs-lookup"><span data-stu-id="4fe95-162">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="4fe95-163">Основные действия по улучшению</span><span class="sxs-lookup"><span data-stu-id="4fe95-163">Key improvement actions</span></span>

<span data-ttu-id="4fe95-164">В этом разделе перечислены основные действия по улучшению, которые можно выполнить прямо сейчас, чтобы получить наибольшее положительное воздействие на общий рейтинг соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4fe95-164">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="4fe95-165">В нем перечислены действия, которые не завершены или не прошли оценку с высокими рисками.</span><span class="sxs-lookup"><span data-stu-id="4fe95-165">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="4fe95-166">Решения, влияющие на оценку</span><span class="sxs-lookup"><span data-stu-id="4fe95-166">Solutions that affect your score</span></span>

<span data-ttu-id="4fe95-167">В этом разделе показано, какие решения содержат действия с наибольшим влиянием на результаты оценки, а также сколько незаконченных действий по улучшению у каждого решения.</span><span class="sxs-lookup"><span data-stu-id="4fe95-167">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="4fe95-168">Детализация оценки соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4fe95-168">Compliance Score breakdown</span></span>

<span data-ttu-id="4fe95-169">В этом разделе представлены более подробные сведения о рейтинге двумя различными способами:</span><span class="sxs-lookup"><span data-stu-id="4fe95-169">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="4fe95-170">**Categories**: показывает процент общей оценки в категориях защиты данных, например "Защита данных" или "Управление устройствами".</span><span class="sxs-lookup"><span data-stu-id="4fe95-170">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="4fe95-171">**Оценки**: показывает процентное отношение процесса управления оценкой для определенных требований и стандартов защиты данных, нормативов или законов, таких как GDPR или NIST 800-53.</span><span class="sxs-lookup"><span data-stu-id="4fe95-171">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="4fe95-172">Фильтрация представления панели мониторинга</span><span class="sxs-lookup"><span data-stu-id="4fe95-172">Filtering your dashboard view</span></span>

<span data-ttu-id="4fe95-173">Вы можете отфильтровать представление панели мониторинга, чтобы увидеть только элементы, относящиеся к определенным нормативам и стандартам, решениям, типам действий, группам или категориям защиты данных.</span><span class="sxs-lookup"><span data-stu-id="4fe95-173">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, groups, or data protection categories.</span></span> <span data-ttu-id="4fe95-174">Таким образом, Фильтрация представления позволяет отфильтровать оценку на панели мониторинга, отображая количество баллов, которые вы получили из всех возможных точек на основе условий фильтрации.</span><span class="sxs-lookup"><span data-stu-id="4fe95-174">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="4fe95-175">Чтобы применить фильтры:</span><span class="sxs-lookup"><span data-stu-id="4fe95-175">To apply filters:</span></span>

1. <span data-ttu-id="4fe95-176">Выберите **Фильтр** в верхней правой части панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4fe95-176">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="4fe95-177">Выберите критерии фильтрации в области "всплывающие **фильтры** ", а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="4fe95-177">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="4fe95-178">Вы увидите рейтинг, скорректированный в режиме реального времени, и вы увидите только те действия, которые помогут усовершенствовать, решения и сведения о разбиении оценок, соответствующие условиям фильтра.</span><span class="sxs-lookup"><span data-stu-id="4fe95-178">You will see your score adjusted in real-time, and you will only see improvement actions, solutions, and score breakdown information that correspond to your filter criteria.</span></span> <span data-ttu-id="4fe95-179">Если вы выйдете из оценки соответствия требованиям, отфильтрованное представление останется при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="4fe95-179">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="4fe95-180">Чтобы удалить фильтры:</span><span class="sxs-lookup"><span data-stu-id="4fe95-180">To remove filters:</span></span>

- <span data-ttu-id="4fe95-181">В заголовке **Примененные фильтры** нажмите кнопку **X** рядом с нужным фильтром, чтобы удалить его. также</span><span class="sxs-lookup"><span data-stu-id="4fe95-181">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="4fe95-182">Выберите **Фильтр** в верхней правой части панели мониторинга, а затем выберите пункт **Очистить фильтры**.</span><span class="sxs-lookup"><span data-stu-id="4fe95-182">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="4fe95-183">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4fe95-183">Next step</span></span>

<span data-ttu-id="4fe95-184">Посетите страницу [Работа с показателем соответствия требованиям](working-with-compliance-score.md) , чтобы понять, как выполнять действия для оптимизации оценки.</span><span class="sxs-lookup"><span data-stu-id="4fe95-184">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>