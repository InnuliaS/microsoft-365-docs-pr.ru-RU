---
title: Общие сведения о неограниченном архивировании в Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Сведения об автоматическом развертывании архивации в Office 365, которая обеспечивает неограниченное хранение архивных почтовых ящиков Exchange Online.
ms.openlocfilehash: 475bf53304be55bbac085693788cff4b5522bb14
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091346"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="8adaa-103">Общие сведения о неограниченном архивировании в Office 365</span><span class="sxs-lookup"><span data-stu-id="8adaa-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="8adaa-104">В Office 365 архивные почтовые ящики предоставляют пользователям дополнительное место для хранения почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="8adaa-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="8adaa-105">После включения архивного почтового ящика пользователя доступно до 100 ГБ дополнительного хранилища.</span><span class="sxs-lookup"><span data-stu-id="8adaa-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="8adaa-106">В прошлое при достижении квоты хранилища 100-GB организациям пришлось обратиться в корпорацию Майкрософт, чтобы запросить дополнительное место для архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8adaa-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="8adaa-107">Это больше не так.</span><span class="sxs-lookup"><span data-stu-id="8adaa-107">That's no longer the case.</span></span>

<span data-ttu-id="8adaa-108">Функция неограниченной архивации в Office 365 (называемая *автоматически развертываемым архивом*) предоставляет до 1 ТБ дополнительного хранилища в архивных почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="8adaa-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides up to 1 TB of additional storage in archive mailboxes.</span></span> <span data-ttu-id="8adaa-109">Если достигнута квота хранилища в архивном почтовом ящике, Office 365 автоматически увеличит размер архива, что означает, что пользователи не смогут использовать место для хранения почтовых ящиков, а администраторам не придется запрашивать дополнительное хранилище для архивных почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="8adaa-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="8adaa-110">Пошаговые инструкции по включению автоматического развертывания архивации приведены [в статье Включение неограниченного архивирования в Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="8adaa-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8adaa-111">Автоматически расширяющиеся архивы также доступны для общих почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="8adaa-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="8adaa-112">Для включения архива для общего почтового ящика требуется лицензия на Exchange Online (план 2) или лицензию на Exchange Online (план 1) с лицензией на архивацию на базе Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8adaa-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="8adaa-113">Как работает автоматическое расширение архивации</span><span class="sxs-lookup"><span data-stu-id="8adaa-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="8adaa-114">Как описывалось ранее, дополнительное дисковое пространство для хранилища почтовых ящиков создается при включении архивного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="8adaa-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="8adaa-115">Если включено автоматическое расширение архивации, Office 365 периодически проверяет размер архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8adaa-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="8adaa-116">Когда архивный почтовый ящик становится близок к максимальному объему хранилища, Office 365 автоматически создает дополнительное дисковое пространство для архивного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8adaa-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive mailbox.</span></span> <span data-ttu-id="8adaa-117">Это дополнительное пространство называется *вспомогательным архивом*.</span><span class="sxs-lookup"><span data-stu-id="8adaa-117">This additional space is called an *auxiliary archive*.</span></span> <span data-ttu-id="8adaa-118">Если пользователю не хватает места для хранения в вспомогательном архиве, Office 365 автоматически добавит новый вспомогательный Архив.</span><span class="sxs-lookup"><span data-stu-id="8adaa-118">If the user runs out of storage space in an auxiliary archive, Office 365 will automatically add a new auxiliary archive.</span></span> <span data-ttu-id="8adaa-119">В Office 365 добавляется не более 20 дополнительных архивов, что всего составляет 1 ТБ дополнительного хранилища.</span><span class="sxs-lookup"><span data-stu-id="8adaa-119">Office 365 adds a maximum of 20 auxiliary archives for a total of 1 TB of additional storage.</span></span> <span data-ttu-id="8adaa-120">Этот процесс выполняется автоматически, что означает, что администраторам не требуется управлять автоматическим развертыванием архивации.</span><span class="sxs-lookup"><span data-stu-id="8adaa-120">This process happens automatically, which means administrators don't have to manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="8adaa-121">Ниже приведен краткий обзор процесса.</span><span class="sxs-lookup"><span data-stu-id="8adaa-121">Here's a quick overview of the process.</span></span>
  
![Обзор автоматического развертывания процесса архивации](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="8adaa-123">Архивация включена для почтового ящика пользователя или общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8adaa-123">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="8adaa-124">Создается архивный почтовый ящик с размером 100 ГБ дискового пространства, а квота предупреждения для архивного почтового ящика равна 90 ГБ.</span><span class="sxs-lookup"><span data-stu-id="8adaa-124">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="8adaa-125">Администратор включает автоматическое расширение архивации для почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="8adaa-125">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="8adaa-126">Когда архивный почтовый ящик (включая папку "элементы с возможностью восстановления") достигнет размера 90 ГБ, он преобразуется в автоматически расширяемый Архив, а Office 365 добавляет место для хранения в архив.</span><span class="sxs-lookup"><span data-stu-id="8adaa-126">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="8adaa-127">Для подготовки дополнительного дискового пространства может потребоваться до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8adaa-127">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8adaa-128">Если почтовый ящик размещается на удержании или назначенной политике хранения Office 365, квота хранилища для архива маибокс увеличивается до 110 ГБ при включенном автоматическом развертывании архивации.</span><span class="sxs-lookup"><span data-stu-id="8adaa-128">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="8adaa-129">Аналогично, квота предупреждения о архиве увеличивается до 100 ГБ.</span><span class="sxs-lookup"><span data-stu-id="8adaa-129">Similarly, the archive warning quota is increased to 100 GB.</span></span>
    
3. <span data-ttu-id="8adaa-130">Office 365 автоматически добавляет дополнительное дисковое пространство при необходимости.</span><span class="sxs-lookup"><span data-stu-id="8adaa-130">Office 365 automatically adds more storage space when necessary.</span></span> <span data-ttu-id="8adaa-131">Как отмечалось ранее, Office 365 добавляет до 20 вспомогательных архивов в течение не более 1 ТБ дополнительного дискового пространства для хранения архива.</span><span class="sxs-lookup"><span data-stu-id="8adaa-131">As previously stated, Office 365 adds up to 20 auxiliary archives, for a maximum of 1 TB of additional archive storage space.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8adaa-132">Автоматическое расширение архива поддерживается только для почтовых ящиков, используемых для отдельных пользователей (или общих почтовых ящиков), при этом скорость роста не превышает 1 ГБ в день.</span><span class="sxs-lookup"><span data-stu-id="8adaa-132">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="8adaa-133">Архивный почтовый ящик пользователя предназначен только для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8adaa-133">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="8adaa-134">Использование ведения журнала, правил транспорта или правил автоматической пересылки для копирования сообщений в архивный почтовый ящик не разрешено.</span><span class="sxs-lookup"><span data-stu-id="8adaa-134">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="8adaa-135">Майкрософт оставляет за собой право отказать в неограниченном архивировании, если архивный почтовый ящик пользователя используется для хранения архивных данных других пользователей.</span><span class="sxs-lookup"><span data-stu-id="8adaa-135">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="8adaa-136">Что перемещается в дополнительное место для хранения архива?</span><span class="sxs-lookup"><span data-stu-id="8adaa-136">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="8adaa-137">Для эффективного использования автоматически развертываемого архивного хранилища папки могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="8adaa-137">To make efficient use of auto-expanding archive storage, folders might get moved.</span></span> <span data-ttu-id="8adaa-138">Office 365 определяет, какие папки перемещаются, когда в архив добавляется дополнительное хранилище.</span><span class="sxs-lookup"><span data-stu-id="8adaa-138">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="8adaa-139">При перемещении папки она автоматически создается под исходной папкой в части "Архив" в списке папок в Outlook.</span><span class="sxs-lookup"><span data-stu-id="8adaa-139">When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook.</span></span> <span data-ttu-id="8adaa-140">Эта новая вложенная папка указывает на перемещенные элементы.</span><span class="sxs-lookup"><span data-stu-id="8adaa-140">This new subfolder points to the items that were moved.</span></span> <span data-ttu-id="8adaa-141">В соответствии с соглашением об именовании, которое Office 365 использует для имени папки, указывается \*\* \<имя\>папки _yyyy (создан в MMM DD, гггг h_mm)\*\*, где:</span><span class="sxs-lookup"><span data-stu-id="8adaa-141">The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="8adaa-142">**гггг** — это год получения сообщений в папке.</span><span class="sxs-lookup"><span data-stu-id="8adaa-142">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="8adaa-143">**MMM DD, гггг h_m** — это дата и время создания вложенной папки в Office 365 в формате UTC, основанной на часовом поясе пользователя и региональных параметрах в Outlook.</span><span class="sxs-lookup"><span data-stu-id="8adaa-143">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="8adaa-144">На следующих снимках экрана показан список папок до и после перемещения сообщений в автоматически развернутом архиве.</span><span class="sxs-lookup"><span data-stu-id="8adaa-144">The following screenshots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="8adaa-145">**Перед добавлением дополнительного хранилища**</span><span class="sxs-lookup"><span data-stu-id="8adaa-145">**Before additional storage is added**</span></span>
  
![Список папок архивного почтового ящика перед подготовкой автоматически развертываемого архива](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="8adaa-147">**После добавления дополнительного хранилища**</span><span class="sxs-lookup"><span data-stu-id="8adaa-147">**After additional storage is added**</span></span>
  
![Список папок архивного почтового ящика после подготовки автоматически развертываемого архива](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="8adaa-149">Требования Outlook для доступа к элементам в автоматически развертываемом архиве</span><span class="sxs-lookup"><span data-stu-id="8adaa-149">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="8adaa-150">Чтобы получить доступ к сообщениям, хранящимся в автоматически развертываемом архиве, пользователи должны использовать один из следующих клиентов Outlook:</span><span class="sxs-lookup"><span data-stu-id="8adaa-150">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="8adaa-151">Outlook 2016 или Outlook 2019 для Windows</span><span class="sxs-lookup"><span data-stu-id="8adaa-151">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="8adaa-152">Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="8adaa-152">Outlook on the web</span></span> 
    
- <span data-ttu-id="8adaa-153">Outlook 2016 или Outlook 2019 для Mac</span><span class="sxs-lookup"><span data-stu-id="8adaa-153">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8adaa-154">Пользователи Outlook 2013 могут получать доступ только к тем элементам, которые были изначально сохранены в архивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="8adaa-154">Outlook 2013 users can only access items that were originally stored in their archive mailbox.</span></span> <span data-ttu-id="8adaa-155">Они не смогут получать доступ к элементам, перемещенным в дополнительное хранилище архива.</span><span class="sxs-lookup"><span data-stu-id="8adaa-155">They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="8adaa-156">Ниже приведено несколько моментов, которые следует учитывать при использовании Outlook или Outlook в Интернете для доступа к сообщениям, хранящимся в автоматически развертываемом архиве.</span><span class="sxs-lookup"><span data-stu-id="8adaa-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="8adaa-157">Можно получить доступ к любой папке в архивном почтовом ящике, включая те, которые были перемещены в автоматически развернутую область хранения.</span><span class="sxs-lookup"><span data-stu-id="8adaa-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="8adaa-158">Поиск элементов, перемещенных в дополнительную область хранения, возможен только путем поиска в самой папке.</span><span class="sxs-lookup"><span data-stu-id="8adaa-158">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="8adaa-159">Это означает, что необходимо выбрать папку Архив в списке папок, чтобы выбрать параметр **Текущая папка** в качестве области поиска.</span><span class="sxs-lookup"><span data-stu-id="8adaa-159">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="8adaa-160">Аналогичным образом, если папка в автоматически расширенной области хранения содержит вложенные папки, необходимо выполнять поиск каждой подпапки отдельно.</span><span class="sxs-lookup"><span data-stu-id="8adaa-160">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="8adaa-161">Количество элементов в Outlook и счетчики чтения и непрочтений (в Outlook и Outlook в Интернете) в автоматически развернутом архиве могут быть неточными.</span><span class="sxs-lookup"><span data-stu-id="8adaa-161">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="8adaa-162">Можно удалить элементы во вложенной папке, указывающие на автоматически развернутую область хранения, но саму папку невозможно удалить.</span><span class="sxs-lookup"><span data-stu-id="8adaa-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="8adaa-163">Вы не можете использовать функцию восстановления удаленных элементов для восстановления элемента, который был удален из автоматически расширенной области хранения.</span><span class="sxs-lookup"><span data-stu-id="8adaa-163">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="8adaa-164">Автоматическое расширение архивации и другие функции соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="8adaa-164">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="8adaa-165">В этом разделе объясняются функции автоматического расширения архивации и других функций управления данными и обеспечения соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="8adaa-165">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="8adaa-166">**Обнаружение электронных данных:** При использовании средства обнаружения электронных данных Office 365, такого как поиск контента или обнаружение электронных данных на месте, также выполняется поиск дополнительных областей хранения в автоматически развертываемом архиве.</span><span class="sxs-lookup"><span data-stu-id="8adaa-166">**eDiscovery:** When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="8adaa-167">:\* **Хранения**\* при помещении почтового ящика на удержание с помощью таких средств, как хранение для судебного разбирательства в Exchange Online или удержания электронных данных в центре безопасности и соответствия требованиям, содержимое, расположенное в автоматическо развертываемом архиве, также размещается на удержании.</span><span class="sxs-lookup"><span data-stu-id="8adaa-167">**Retention**:\*\* When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="8adaa-168">**Управление записями сообщений (управления записями сообщений):** Если вы используете политики удаления управления ЗАПИСЯМИ сообщений в Exchange Online для окончательного удаления просроченных элементов почтовых ящиков, элементы с истекшим сроком действия, расположенные в автоматическом развернутом архиве, также будут удалены.</span><span class="sxs-lookup"><span data-stu-id="8adaa-168">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="8adaa-169">**Импорт:* служб*\*\* вы можете использовать службу импорта Office 365, чтобы импортировать PST-файлы в автоматически развертываемый архив пользователя.</span><span class="sxs-lookup"><span data-stu-id="8adaa-169">**Import service**:\*\* You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="8adaa-170">Вы можете импортировать до 100 ГБ данных из PST-файлов в архивный почтовый ящик пользователя.</span><span class="sxs-lookup"><span data-stu-id="8adaa-170">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="8adaa-171">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8adaa-171">More information</span></span>

<span data-ttu-id="8adaa-172">Более подробную техническую информацию об автоматическом развертывании архивации можно узнать в статье [Office 365: автоматическое расширение архивных вопросов](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span><span class="sxs-lookup"><span data-stu-id="8adaa-172">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>