---
title: Поток обработки почты в службе EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Поскольку вы являетесь пользователем Exchange Online Protection (EOP), все сообщения, отправляемые в организацию, проходят через службу EOP перед доставкой сотрудникам. Если все ваши почтовые ящики находятся в облаке с Exchange Online или хранятся локально (т. е. используется изолированный сценарий), возможно, для дальнейшего использования текущей инфраструктуры у вас есть возможности направлять сообщения, проходящие через службу EOP, для обработки, прежде чем они будут доставлены в папки "Входящие" ваших сотрудников.
ms.openlocfilehash: 2d377e2cd7f6ce2856deda55052b4535649ef8b5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089416"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="43e84-104">Поток обработки почты в службе EOP</span><span class="sxs-lookup"><span data-stu-id="43e84-104">Mail flow in EOP</span></span>

<span data-ttu-id="43e84-p102">Поскольку вы являетесь пользователем Exchange Online Protection (EOP), все сообщения, отправляемые в организацию, проходят через службу EOP перед доставкой сотрудникам. Если все ваши почтовые ящики находятся в облаке с Exchange Online или хранятся локально (т. е. используется изолированный сценарий), возможно, для дальнейшего использования текущей инфраструктуры у вас есть возможности направлять сообщения, проходящие через службу EOP, для обработки, прежде чем они будут доставлены в папки "Входящие" ваших сотрудников.</span><span class="sxs-lookup"><span data-stu-id="43e84-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>
  
<span data-ttu-id="43e84-p103">Возможно, следует настроить пользовательскую маршрутизацию почты, чтобы привести обмен сообщениями в соответствие с вашими бизнес-требованиями. Например, вы можете задать прохождение всей исходящей почты через устройство фильтрации политики.</span><span class="sxs-lookup"><span data-stu-id="43e84-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>
  
## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="43e84-109">Возможности для работы с сообщениями и доступа к ним</span><span class="sxs-lookup"><span data-stu-id="43e84-109">Working with messages and message access options</span></span>

<span data-ttu-id="43e84-p104">Служба EOP позволяет гибко маршрутизировать сообщения. В указанных ниже разделах описаны шаги процесса потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="43e84-p104">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>
  
<span data-ttu-id="43e84-112">[Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию пограничной блокировки на основе каталогов, которая позволяет отклонять сообщения для недопустимых получателей в сети периметра службы.</span><span class="sxs-lookup"><span data-stu-id="43e84-112">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span> 
  
<span data-ttu-id="43e84-113">В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.</span><span class="sxs-lookup"><span data-stu-id="43e84-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>
  
<span data-ttu-id="43e84-114">Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими.</span><span class="sxs-lookup"><span data-stu-id="43e84-114">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="43e84-115">Дополнительные сведения о поддоменах [позволяют включить почтовые потоки для поддоменов в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="43e84-115">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>
  
<span data-ttu-id="43e84-p106">В разделе [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) описываются соединители и их использование для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.</span><span class="sxs-lookup"><span data-stu-id="43e84-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>
  
<span data-ttu-id="43e84-118">Чтобы убедиться, что нежелательная почта правильно направляется в папку нежелательной почты каждого пользователя, необходимо выполнить несколько действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="43e84-118">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="43e84-119">Это подробное описание [того, что спам направляется в папку нежелательной почты каждого пользователя](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="43e84-119">These are detailed in [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="43e84-120">Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, отредактировав политики фильтрации содержимого в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="43e84-120">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="43e84-121">Дополнительные сведения см. в статье [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43e84-121">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
## <a name="verify-mail-flow"></a><span data-ttu-id="43e84-122">Проверка потока почты</span><span class="sxs-lookup"><span data-stu-id="43e84-122">Verify mail flow</span></span>

<span data-ttu-id="43e84-p108">Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="43e84-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
<span data-ttu-id="43e84-125">[Протестируйте почтовые потоки, проверив свои соединители Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) , и пошаговые инструкции по проверке правильности настройки почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="43e84-125">[Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>