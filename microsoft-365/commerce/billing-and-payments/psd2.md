---
title: Директива служб оплаты 2 и надежная проверка подлинности клиентов для коммерческих клиентов
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Начиная с 14 сентября 2019 банки в 31 странах Европейской экономической области необходимы для проверки идентификации сотрудника, осуществляющего покупку в сети, прежде чем оплата может быть обработана.
keywords: Директива служб оплаты 2, надежная проверка подлинности клиентов, многофакторная проверка подлинности
ms.openlocfilehash: 1e9272803fd592062676e3324d172560b6b2219b
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646454"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="ba22c-104">Директива служб оплаты 2 и надежная проверка подлинности клиентов для коммерческих клиентов</span><span class="sxs-lookup"><span data-stu-id="ba22c-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="ba22c-105">Начиная с 14 сентября 2019 банки в 31 странах Европейской экономической области необходимы для проверки идентификации сотрудника, осуществляющего покупку в сети, прежде чем оплата может быть обработана.</span><span class="sxs-lookup"><span data-stu-id="ba22c-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="ba22c-106">Для этой проверки требуется многофакторная проверка подлинности, обеспечивающая безопасность и защиту Интернет-покупок.</span><span class="sxs-lookup"><span data-stu-id="ba22c-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="ba22c-107">Дата этого требования проверки будет задержана для некоторых стран.</span><span class="sxs-lookup"><span data-stu-id="ba22c-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="ba22c-108">Дополнительные сведения см в [статье вопросы и ответы о службах оплаты 2 и надежная проверка подлинности клиентов](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="ba22c-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="ba22c-109">Когда необходима многофакторная проверка подлинности?</span><span class="sxs-lookup"><span data-stu-id="ba22c-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="ba22c-110">В настоящее время требования к проверке этой директивы с использованием многофакторной проверки подлинности применяются только к клиентам с использованием кредитных карт из банков в 31 странах Европейской экономической экономической области.</span><span class="sxs-lookup"><span data-stu-id="ba22c-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="ba22c-111">Иногда клиентам выдается приглашение из-за выполняемого действия, и иногда они запрашиваются из-за событий с имеющимися подписками или службами.</span><span class="sxs-lookup"><span data-stu-id="ba22c-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="ba22c-112">Действия клиентов</span><span class="sxs-lookup"><span data-stu-id="ba22c-112">Customer Actions</span></span>

<span data-ttu-id="ba22c-113">В банке может требоваться проверка с использованием многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ba22c-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="ba22c-114">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="ba22c-114">Some examples include:</span></span>
- <span data-ttu-id="ba22c-115">Регистрация новой подписки</span><span class="sxs-lookup"><span data-stu-id="ba22c-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="ba22c-116">Добавление лицензий в подписку</span><span class="sxs-lookup"><span data-stu-id="ba22c-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="ba22c-117">Добавление или замена кредитной карты, используемой для оплаты за подписку или услугу</span><span class="sxs-lookup"><span data-stu-id="ba22c-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="ba22c-118">Добавление или замена кредитной карты в профиле выставления счетов</span><span class="sxs-lookup"><span data-stu-id="ba22c-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="ba22c-119">Приобретение приложений</span><span class="sxs-lookup"><span data-stu-id="ba22c-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="ba22c-120">События жизненного цикла подписки</span><span class="sxs-lookup"><span data-stu-id="ba22c-120">Subscription lifecycle events</span></span>

<span data-ttu-id="ba22c-121">Начисления расходов на повторяющиеся платежи могут быть не выполнены.</span><span class="sxs-lookup"><span data-stu-id="ba22c-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="ba22c-122">В противном случае вы получите электронное письмо с инструкциями, которые нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="ba22c-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="ba22c-123">Вам будет предложено ответить на запрос на подтверждение и выполнить текущий платеж.</span><span class="sxs-lookup"><span data-stu-id="ba22c-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="ba22c-124">Нужна дополнительная помощь?</span><span class="sxs-lookup"><span data-stu-id="ba22c-124">Need more help?</span></span>

<span data-ttu-id="ba22c-125">Ваше финансовое учреждение — Лучший контакт для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="ba22c-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="ba22c-126">Вы не получили код проверки.</span><span class="sxs-lookup"><span data-stu-id="ba22c-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="ba22c-127">Процесс проверки не сработал после отправки проверочного кода.</span><span class="sxs-lookup"><span data-stu-id="ba22c-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="ba22c-128">Вы не знаете, правильно ли указаны контактные данные для вашей кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="ba22c-128">You're not sure if the contact info for your credit card is correct.</span></span>