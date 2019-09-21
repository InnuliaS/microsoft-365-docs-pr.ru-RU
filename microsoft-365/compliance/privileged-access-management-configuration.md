---
title: Настройка управления привилегированным доступом в Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: В этом разделе вы найдете дополнительные сведения о настройке привилегированного управления доступом в Office 365
ms.openlocfilehash: 46bfeaf0c73c4598fcdaa65d654201620396600c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091035"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="6f86f-103">Настройка управления привилегированным доступом в Office 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f86f-104">В этом разделе рассматривается руководство по развертыванию и настройке для функций, доступных в Office 365 и расширенных конфигураций соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6f86f-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="6f86f-105">В этом разделе описывается включение и Настройка управления привилегированным доступом в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f86f-105">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="6f86f-106">Для управления привилегированным доступом можно использовать центр администрирования Microsoft 365 или PowerShell управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f86f-106">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="6f86f-107">Включение и Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="6f86f-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="6f86f-108">Выполните следующие действия, чтобы настроить и использовать привилегированный доступ в организации Office 365:</span><span class="sxs-lookup"><span data-stu-id="6f86f-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="6f86f-109">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="6f86f-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="6f86f-110">Прежде чем приступить к работе с правами на доступ к данным, определите, кому требуется центр утверждений для входящих запросов на доступ к привилегированным и привилегированным задачам.</span><span class="sxs-lookup"><span data-stu-id="6f86f-110">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="6f86f-111">Любой пользователь, являющийся участником группы утверждающих, может утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="6f86f-111">Any user who is part of the Approvers’ group is able to approve access requests.</span></span> <span data-ttu-id="6f86f-112">Эта возможность включена путем создания группы безопасности с включенной поддержкой почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f86f-112">This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="6f86f-113">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="6f86f-114">Привилегированный доступ должен быть явно включен в Office 365 с группой утверждающих по умолчанию, в том числе набором системных учетных записей, которые необходимо исключить из управления доступом для привилегированного управления доступом.</span><span class="sxs-lookup"><span data-stu-id="6f86f-114">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="6f86f-115">Шаг 3: Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="6f86f-116">Создание политики утверждения позволяет определять конкретные требования к утверждению в рамках отдельных задач.</span><span class="sxs-lookup"><span data-stu-id="6f86f-116">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="6f86f-117">Возможные варианты типа утверждения: **Auto** или **вручную**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-117">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="6f86f-118">Шаг 4: передача и утверждение привилегированных запросов доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="6f86f-119">После включения привилегированный доступ требует утверждения для любой задачи, для которой определена соответствующая политика утверждения.</span><span class="sxs-lookup"><span data-stu-id="6f86f-119">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="6f86f-120">Для задач, включенных в политику утверждения, пользователям необходимо запросить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="6f86f-120">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="6f86f-121">После предоставления утверждения пользователь, выполняющий запрос, может выполнить предполагаемую задачу, а привилегированный доступ будет авторизовать и выполнить задачу от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f86f-121">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="6f86f-122">Утверждение остается действительным в течение запрошенного периода (длительность по умолчанию составляет 4 часа), в течение которого инициатор запроса может выполнить нужную задачу несколько раз.</span><span class="sxs-lookup"><span data-stu-id="6f86f-122">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="6f86f-123">Все подобные выполнения записываются в журнал и становятся доступны для аудита безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6f86f-123">All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f86f-124">Чтобы включить и настроить привилегированный доступ с помощью PowerShell для Exchange Management PowerShell, выполните действия, описанные в статье [Подключение к Exchange Online PowerShell с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) для подключения к Exchange Online PowerShell с помощью Office 365 записей.</span><span class="sxs-lookup"><span data-stu-id="6f86f-124">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="6f86f-125">В организации Office 365 не требуется включать многофакторную проверку подлинности для включения привилегированного доступа при подключении к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f86f-125">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="6f86f-126">При подключении с многофакторной проверкой подлинности создается маркер OAuth, используемый привилегированным доступом для подписи запросов.</span><span class="sxs-lookup"><span data-stu-id="6f86f-126">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="6f86f-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="6f86f-127"></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="6f86f-128">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="6f86f-128">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="6f86f-129">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-129">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6f86f-130">В центре администрирования последовательно выберите пункты **группы** > **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="6f86f-131">Выберите пункт **Группа безопасности с включенной поддержкой почты** и заполните поля **имя**, **адрес электронной почты группы**и **Описание** для новой группы.</span><span class="sxs-lookup"><span data-stu-id="6f86f-131">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="6f86f-132">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="6f86f-132">Save the group.</span></span> <span data-ttu-id="6f86f-133">Для полной настройки группы и ее отображения в центре администрирования Microsoft 365 может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6f86f-133">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="6f86f-134">Выберите новую группу утверждающего и нажмите кнопку **изменить** , чтобы добавить пользователей в группу.</span><span class="sxs-lookup"><span data-stu-id="6f86f-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="6f86f-135">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="6f86f-135">Save the group.</span></span>

<span data-ttu-id="6f86f-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="6f86f-136"></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="6f86f-137">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-137">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-138">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-138">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6f86f-139">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-139">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6f86f-140">В центре администрирования перейдите к разделу **Параметры > безопасность &** > **доступ к привилегированному доступу**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-141">Включите разрешение " **требовать утверждения для контроля привилегированного доступа** ".</span><span class="sxs-lookup"><span data-stu-id="6f86f-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="6f86f-142">Назначьте группу утверждающих, созданную на шаге 1, в качестве **группы утверждающих по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="6f86f-143">**Сохраните** и **закройте диалоговое окно**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-143">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-144">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-144">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-145">Чтобы включить привилегированный доступ и назначить группу утверждающего, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-145">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="6f86f-146">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="6f86f-147">Функция "системные учетные записи" доступна, чтобы гарантировать, что определенные автоматизации в организациях могут работать без зависимости от привилегированного доступа, однако рекомендуется, чтобы такие исключения были исключительными и были разрешены и проверены. менять.</span><span class="sxs-lookup"><span data-stu-id="6f86f-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="6f86f-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="6f86f-148"></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="6f86f-149">Шаг 3: Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-149">Step 3: Create an access policy</span></span>

<span data-ttu-id="6f86f-150">Вы можете создать и настроить до 30 политик доступа для организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f86f-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-151">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-151">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6f86f-152">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-152">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6f86f-153">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-154">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6f86f-155">Выберите пункт **Настройка политик** и нажмите кнопку **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="6f86f-156">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="6f86f-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="6f86f-157">**Тип политики**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="6f86f-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="6f86f-158">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-158">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="6f86f-159">**Имя политики**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="6f86f-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="6f86f-160">**Тип утверждения**: вручную или автоматически</span><span class="sxs-lookup"><span data-stu-id="6f86f-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="6f86f-161">**Группа утверждения**: выберите группу утверждающих, созданную на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="6f86f-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="6f86f-162">Выберите **создать** , а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-162">Select **Create** and then **Close**.</span></span> <span data-ttu-id="6f86f-163">Полная настройка и включение политики может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6f86f-163">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-164">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-164">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-165">Чтобы создать и определить политику утверждения, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-165">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="6f86f-166">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="6f86f-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="6f86f-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="6f86f-168">Шаг 4: передача и утверждение привилегированных запросов доступа</span><span class="sxs-lookup"><span data-stu-id="6f86f-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="6f86f-169">Запрос разрешения на повышение прав для выполнения привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="6f86f-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="6f86f-170">Запросы для привилегированного доступа действительны в течение 24 часов после отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="6f86f-170">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="6f86f-171">Если оно не утверждено или отклонено, срок действия запросов истечет и доступ не утверждается.</span><span class="sxs-lookup"><span data-stu-id="6f86f-171">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-172">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-172">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="6f86f-173">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6f86f-173">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="6f86f-174">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-175">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6f86f-176">Выберите пункт **создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-176">Select **New request**.</span></span> <span data-ttu-id="6f86f-177">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="6f86f-177">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="6f86f-178">**Тип запроса**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="6f86f-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="6f86f-179">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="6f86f-180">**Запрос для**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="6f86f-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="6f86f-181">**Продолжительность (часы)**: количество часов запрошенного доступа.</span><span class="sxs-lookup"><span data-stu-id="6f86f-181">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="6f86f-182">Количество часов, которые можно запросить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="6f86f-182">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="6f86f-183">**Comments**: текстовое поле для комментариев, связанных с вашим запросом на доступ</span><span class="sxs-lookup"><span data-stu-id="6f86f-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="6f86f-184">Нажмите кнопку **сохранить** , а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-184">Select **Save** and then **Close**.</span></span> <span data-ttu-id="6f86f-185">Ваш запрос будет отправлен в группу утверждающего через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="6f86f-185">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-186">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-186">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-187">Выполните следующую команду в Exchange Online PowerShell, чтобы создать и отправить запрос на утверждение группе утверждающего.</span><span class="sxs-lookup"><span data-stu-id="6f86f-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="6f86f-188">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="6f86f-189">Просмотр состояния запросов на повышение прав</span><span class="sxs-lookup"><span data-stu-id="6f86f-189">View status of elevation requests</span></span>
<span data-ttu-id="6f86f-190">После создания запроса на утверждение состояние запроса на повышение прав можно просмотреть в центре администрирования или в Exchange Management PowerShell с помощью соответствующего идентификатора запроса.</span><span class="sxs-lookup"><span data-stu-id="6f86f-190">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-191">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-191">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6f86f-192">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с вашими учетными данными.</span><span class="sxs-lookup"><span data-stu-id="6f86f-192">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="6f86f-193">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-193">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-194">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6f86f-195">Выберите **представление** , чтобы отфильтровать отправленные запросы по **очереди**, **утверждению**, **отклонению**или статусу **защищенного хранилища клиента** .</span><span class="sxs-lookup"><span data-stu-id="6f86f-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-196">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-196">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-197">Выполните следующую команду в Exchange Online PowerShell, чтобы просмотреть состояние запроса на утверждение для определенного идентификатора запроса:</span><span class="sxs-lookup"><span data-stu-id="6f86f-197">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="6f86f-198">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="6f86f-199">Утверждение запроса на повышение прав на авторизацию</span><span class="sxs-lookup"><span data-stu-id="6f86f-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="6f86f-200">При создании запроса на утверждение участники группы "Утверждающие" получают уведомления по электронной почте и могут утверждать запрос, связанный с ИДЕНТИФИКАТОРом запроса.</span><span class="sxs-lookup"><span data-stu-id="6f86f-200">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="6f86f-201">Запрашивающий уведомляет об утверждении или отказе от запроса через сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6f86f-201">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-202">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-202">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6f86f-203">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с вашими учетными данными.</span><span class="sxs-lookup"><span data-stu-id="6f86f-203">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="6f86f-204">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-204">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-205">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6f86f-206">Выберите указанный запрос для просмотра сведений и выполнения действий по запросу.</span><span class="sxs-lookup"><span data-stu-id="6f86f-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="6f86f-207">Выберите **утвердить** , чтобы утвердить запрос, или выберите **запретить** , чтобы отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="6f86f-207">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="6f86f-208">Чтобы получить доступ к ранее утвержденным запросам, нажмите кнопку **отозвать**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-208">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-209">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-209">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-210">Чтобы утвердить запрос на повышение прав на авторизацию, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-210">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="6f86f-211">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="6f86f-212">Чтобы запретить запрос на повышение прав на авторизацию, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-212">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="6f86f-213">Пример.</span><span class="sxs-lookup"><span data-stu-id="6f86f-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="6f86f-214">Удаление политики привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="6f86f-215">Если в вашей организации больше нет необходимости, можно удалить политику привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="6f86f-215">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-216">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6f86f-217">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6f86f-218">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-219">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6f86f-220">Выберите пункт **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="6f86f-221">Выберите политику, которую нужно удалить, а затем нажмите кнопку **удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="6f86f-222">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-222">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-223">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-224">Чтобы удалить политику привилегированного доступа, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-224">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="6f86f-225">Отключение привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="6f86f-226">При необходимости вы можете отключить управление привилегированным доступом для своей организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-226">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="6f86f-227">При отключении привилегированного доступа не удаляются все связанные с ним политики утверждения или группы утверждающих.</span><span class="sxs-lookup"><span data-stu-id="6f86f-227">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="6f86f-228">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f86f-228">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6f86f-229">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетные данные для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="6f86f-229">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="6f86f-230">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="6f86f-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6f86f-231">Включите разрешение " **требовать утверждения для контроля привилегированного доступа** ".</span><span class="sxs-lookup"><span data-stu-id="6f86f-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="6f86f-232">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="6f86f-232">In Exchange Management PowerShell</span></span>

<span data-ttu-id="6f86f-233">Чтобы отключить привилегированный доступ, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f86f-233">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```
Disable-ElevatedAccessControl
```