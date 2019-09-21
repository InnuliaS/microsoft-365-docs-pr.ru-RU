---
title: Поддержка проверки сообщений, подписанных с помощью DKIM
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Сведения о проверке подлинности подписанных сообщений DKIM в Exchange Online Protection и Exchange Online
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091438"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="c6bb8-103">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="c6bb8-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="c6bb8-104">Exchange Online Protection (EOP) и Exchange Online поддерживают входящую проверку входящих сообщений электронной почты ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) в ключах домена.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="c6bb8-105">DKIM позволяет проверить, отправлено ли сообщение из заявленного домена и не подделали ли его.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="c6bb8-106">Сообщение электронной почты связывается с организацией, ответственной за его отправку.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="c6bb8-107">Проверка DKIM используется автоматически для всех сообщений, отправленных через подключения по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="c6bb8-108">Кроме того, Office 365 поддерживает DKIM при отправке почты по протоколу IPv4.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="c6bb8-109">(Дополнительные сведения о поддержке протокола IPv6 см. в разделе [Поддержка анонимных входящих сообщений электронной почты по протоколу IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span><span class="sxs-lookup"><span data-stu-id="c6bb8-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="c6bb8-p102">DKIM проверяет сообщение с цифровой подписью, которое отображается в заголовке DKIM-Signature в заголовках сообщения. Результаты проверки заголовка DKIM-Signature помечаются в заголовке Authentication-Results, который соответствует спецификации RFC 7001 ([Поле заголовка сообщения для указания состояния проверки подлинности сообщения](https://www.rfc-editor.org/rfc/rfc7001.txt)). Текст заголовка сообщения имеет указанные ниже формат (где contoso.com  отправитель).</span><span class="sxs-lookup"><span data-stu-id="c6bb8-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="c6bb8-113">Администраторы могут создавать правила для [почтовых ящиков](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) Exchange (которые также называются правилами транспорта) на результаты проверки DKIM для фильтрации и маршрутизации сообщений по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="c6bb8-113">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  
