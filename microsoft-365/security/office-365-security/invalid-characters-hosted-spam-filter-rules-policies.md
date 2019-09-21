---
title: Предотвращение недопустимых символов в правилах фильтрации нежелательной почты и политики фильтрации нежелательной почты
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Предоставляет справочные сведения для администраторов, которые имеют недопустимые символы в конфигурации защиты от нежелательной почты и могут выполнять проблемы &amp; при попытке использовать центр обеспечения безопасности.
ms.openlocfilehash: 286a96814e0be5857499d7c54839d20142d0dd60
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090021"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="0881d-103">Предотвращение недопустимых символов в правилах фильтрации нежелательной почты и фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="0881d-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="0881d-104">Ранее администраторы Office 365 настроили и настроили правила фильтрации нежелательной почты и политики фильтрации нежелательной почты с помощью центра администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="0881d-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="0881d-105">Теперь вы используете центр соответствия требованиям &amp; безопасности для управления конфигурацией защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="0881d-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="0881d-106">В центре администрирования Exchange поддерживались следующие символы, но они не поддерживаются в центре безопасности &amp; и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0881d-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="0881d-107">**Недопустимые символы:**</span><span class="sxs-lookup"><span data-stu-id="0881d-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="0881d-108">Если правила фильтрации нежелательной почты или политика фильтрации нежелательной почты содержат какие – либо из недопустимых символов, могут возникнуть следующие проблемы:</span><span class="sxs-lookup"><span data-stu-id="0881d-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="0881d-109">Возможно, вы не сможете найти политику или правила в центре безопасности &amp; и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0881d-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="0881d-110">При попытке получить правила или политику с помощью Windows PowerShell могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="0881d-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="0881d-111">Возможно, политика или параметры не работают или не работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="0881d-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="0881d-112">Удаление недопустимых символов из политики и правил фильтрации нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="0881d-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="0881d-113">После определения политики и правил, содержащих недопустимые символы, их имена можно изменить с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0881d-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="0881d-114">[Подключитесь к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="0881d-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="0881d-115">Чтобы изменить имя политики фильтрации нежелательной почты, выполните командлет Set – HostedContentFilterPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0881d-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="0881d-116">Чтобы изменить имя правила фильтрации нежелательной почты, выполните командлет Set – Hostedcontentfilterrule используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0881d-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="0881d-117">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0881d-117">For more information</span></span>

[<span data-ttu-id="0881d-118">Управление угрозами в центре &amp; безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0881d-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="0881d-119">Set — HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="0881d-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="0881d-120">Set — Hostedcontentfilterrule используется</span><span class="sxs-lookup"><span data-stu-id="0881d-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)