---
title: Вращение или поворот ключа клиента или ключа доступности
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Сведения о том, как выполнить сведение корневых ключей клиентов, хранящихся в Azure Key Vault, которые используются с ключом клиента Office 365. Службы включают в себя Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и файлы Teams.
ms.openlocfilehash: 9699960666eaa9aa62bb027d3a4549cb50cd52e3
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804854"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="9c34b-104">Вращение или поворот ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="9c34b-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="9c34b-105">Изменяйте только ключ шифрования, который вы используете с ключом клиента, если требования к безопасности или соответствия требованиям заключаются в том, что необходимо выполнить эту проверку.</span><span class="sxs-lookup"><span data-stu-id="9c34b-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="9c34b-106">Кроме того, не удаляйте ключи, которые не были связаны с политиками.</span><span class="sxs-lookup"><span data-stu-id="9c34b-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="9c34b-107">При откате ключей будет использоваться содержимое, зашифрованное с помощью предыдущих ключей.</span><span class="sxs-lookup"><span data-stu-id="9c34b-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="9c34b-108">Например, несмотря на то, что активные почтовые ящики будут повторно зашифрованы, неактивные, отключенные и отключенные почтовые ящики, могут быть зашифрованы с помощью предыдущих ключей.</span><span class="sxs-lookup"><span data-stu-id="9c34b-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="9c34b-109">SharePoint Online выполняет резервное копирование контента для восстановления и восстановления, поэтому по-прежнему можно заархивировать содержимое, используя старые ключи.</span><span class="sxs-lookup"><span data-stu-id="9c34b-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="9c34b-110">Сведения о том, как поменять ключ доступности</span><span class="sxs-lookup"><span data-stu-id="9c34b-110">About rolling the availability key</span></span>

<span data-ttu-id="9c34b-111">Корпорация Майкрософт не предоставляет клиентам прямой контроль над ключом доступности.</span><span class="sxs-lookup"><span data-stu-id="9c34b-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="9c34b-112">Например, можно выполнить только сведение (поворот) ключей, которыми вы владеете в Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="9c34b-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="9c34b-113">Office 365 выполняет откат ключей доступности по внутреннему расписанию.</span><span class="sxs-lookup"><span data-stu-id="9c34b-113">Office 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="9c34b-114">Для этих полных этапов не существует соглашения об уровне обслуживания (SLA).</span><span class="sxs-lookup"><span data-stu-id="9c34b-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="9c34b-115">Office 365 поворачивает ключ доступности с помощью кода службы Office 365 в автоматическом, не выполняемом вручную процессе.</span><span class="sxs-lookup"><span data-stu-id="9c34b-115">Office 365 rotates the availability key using Office 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="9c34b-116">Администраторы Майкрософт могут инициировать процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="9c34b-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="9c34b-117">Этот ключ выполняет откат с помощью автоматизированных механизмов без прямого доступа к хранилищу ключей.</span><span class="sxs-lookup"><span data-stu-id="9c34b-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="9c34b-118">Доступ к защищенному хранилищу ключа доступности не предоставлены администраторам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9c34b-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="9c34b-119">С помощью ключа доступности можно использовать тот же механизм, что и для первоначального создания ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="9c34b-120">Дополнительные сведения о ключе доступности приведены в разделе [сведения о ключе доступности](customer-key-availability-key-understand.md).</span><span class="sxs-lookup"><span data-stu-id="9c34b-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c34b-121">Ключи доступности Exchange Online и Skype для бизнеса могут быть эффективно собраны клиентами, создающими новую функцию DEP, так как для каждой создаваемой функции DEP создается уникальный ключ доступности.</span><span class="sxs-lookup"><span data-stu-id="9c34b-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="9c34b-122">Ключи доступности для SharePoint Online, OneDrive для бизнеса и файлов Teams существуют на уровне леса и совместно используются в ДЕПС и клиентах, что означает, что развертывание выполняется только в определенном по внутреннем расписании Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9c34b-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="9c34b-123">Чтобы уменьшить риск невозможности переносить ключ доступности при каждом создании новой функции DEP, SharePoint, OneDrive и Teams выявляют промежуточный ключ клиента (тик), ключ, заключенный в корневые ключи клиента и ключ доступности, каждый раз, когда создается новая функция DEP.</span><span class="sxs-lookup"><span data-stu-id="9c34b-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="9c34b-124">Запросите новую версию каждого существующего корневого ключа, который необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="9c34b-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="9c34b-125">При выполнении отката ключа вы запрашиваете новую версию существующего ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="9c34b-126">Чтобы запросить новую версию существующего ключа, используйте тот же командлет [Add – азкэйваулткэй](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)с тем же синтаксисом, который использовался для создания ключа в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="9c34b-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="9c34b-127">После того, как вы закончите все ключи, связанные с политикой шифрования данных (DEP), запустите другой командлет, чтобы убедиться, что ключ клиента начинает использовать новый ключ.</span><span class="sxs-lookup"><span data-stu-id="9c34b-127">After you’ve finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="9c34b-128">Выполните это действие в каждом хранилище ключей Azure (АКВ).</span><span class="sxs-lookup"><span data-stu-id="9c34b-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="9c34b-129">Например:</span><span class="sxs-lookup"><span data-stu-id="9c34b-129">For example:</span></span>

1. <span data-ttu-id="9c34b-130">Войдите в свою подписку на Azure с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c34b-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="9c34b-131">Инструкции можно найти [в разделе Вход с помощью Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="9c34b-131">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="9c34b-132">Запустите командлет Add – Азкэйваулткэй, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9c34b-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="9c34b-133">В этом примере, так как ключ с именем **contoso – O365EX — Na – VaultA1 – Key001** существует в хранилище **contoso — O365EX, Na/VaultA1** , командлет создает новую версию ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="9c34b-134">Эта операция сохраняет предыдущие основные версии в журнале версий для ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="9c34b-135">Для расшифровки данных, которые по-прежнему шифруются, необходима предыдущая версия ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="9c34b-136">После выполнения всех ключей, связанных с функцией DEP, выполните дополнительный командлет, чтобы убедиться, что ключ клиента начинает использовать новый ключ.</span><span class="sxs-lookup"><span data-stu-id="9c34b-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="9c34b-137">В следующих разделах более подробно описаны командлеты.</span><span class="sxs-lookup"><span data-stu-id="9c34b-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="9c34b-138">Обновление ключа клиента для Exchange Online и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9c34b-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="9c34b-139">При выполнении одного из ключей Azure Key Vault, связанных с DEP, используемым в Exchange Online и Skype для бизнеса, необходимо обновить DEP, чтобы указать на новый ключ.</span><span class="sxs-lookup"><span data-stu-id="9c34b-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="9c34b-140">При этом ключ доступности не поворачивается.</span><span class="sxs-lookup"><span data-stu-id="9c34b-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="9c34b-141">Чтобы назначить ключ клиента для шифрования почтовых ящиков в Office 365, выполните командлет Set – Dataencryptionpolicy используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c34b-141">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="9c34b-142">Выполните командлет Set – Dataencryptionpolicy используется в Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9c34b-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="9c34b-143">В течение 72 часов активные почтовые ящики, связанные с этой функцией DEP, будут зашифрованы с помощью нового ключа.</span><span class="sxs-lookup"><span data-stu-id="9c34b-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="9c34b-144">Чтобы проверить значение свойства Датаенкриптионполициид почтового ящика, выполните действия, описанные в статье [Определение функции DEP, назначенного почтовому ящику](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9c34b-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="9c34b-145">Значение этого свойства изменяется, когда служба применяет обновленный ключ.</span><span class="sxs-lookup"><span data-stu-id="9c34b-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="9c34b-146">Обновление ключа клиента для SharePoint Online, OneDrive для бизнеса и файлов Teams</span><span class="sxs-lookup"><span data-stu-id="9c34b-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="9c34b-147">SharePoint Online позволяет выполнять только один ключ за раз.</span><span class="sxs-lookup"><span data-stu-id="9c34b-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="9c34b-148">Если вы хотите выполнить накат обоих ключей в хранилище ключей, дождитесь завершения первой операции.</span><span class="sxs-lookup"><span data-stu-id="9c34b-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="9c34b-149">Корпорация Майкрософт рекомендует по мере необходимости отключать операции, чтобы избежать этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="9c34b-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="9c34b-150">При выполнении одного из ключей Azure Key Vault, связанных с DEP, используемым в SharePoint Online и OneDrive для бизнеса, необходимо обновить DEP, чтобы указать на новый ключ.</span><span class="sxs-lookup"><span data-stu-id="9c34b-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="9c34b-151">При этом ключ доступности не поворачивается.</span><span class="sxs-lookup"><span data-stu-id="9c34b-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="9c34b-152">Выполните командлет Update – Сподатаенкриптионполици следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c34b-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="9c34b-153">Несмотря на то, что этот командлет запускает операцию key для SharePoint Online и OneDrive для бизнеса, действие не завершается немедленно.</span><span class="sxs-lookup"><span data-stu-id="9c34b-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="9c34b-154">Чтобы просмотреть ход выполнения операции с ключом, выполните командлет Get – Сподатаенкриптионполици следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9c34b-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="9c34b-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9c34b-155">Related articles</span></span>

- [<span data-ttu-id="9c34b-156">Шифрование службы с помощью ключа клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="9c34b-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="9c34b-157">Настройка ключа клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="9c34b-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="9c34b-158">Управление ключом клиента для Office 365</span><span class="sxs-lookup"><span data-stu-id="9c34b-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="9c34b-159">Сведения о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="9c34b-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)