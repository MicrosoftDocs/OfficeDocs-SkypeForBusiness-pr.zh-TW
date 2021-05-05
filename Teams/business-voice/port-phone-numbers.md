---
title: 將電話號碼移轉至商務語音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何將現有的電話號碼從目前的服務提供者移至 Microsoft 365 商務語音。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e950e9e3bf18664a6a877c31e253ce66753a6076
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130262"
---
# <a name="move-port-phone-numbers-to-business-voice"></a><span data-ttu-id="2f0b8-103">移動 (移植) 電話號碼至商務語音</span><span class="sxs-lookup"><span data-stu-id="2f0b8-103">Move (port) phone numbers to Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f0b8-104">本文中的資訊僅適用於 **含** 通話方案的商務語音。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-104">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="2f0b8-105">含通話方案的商務語音只有在選取的國家和地區才能使用。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-105">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="2f0b8-106">閱讀本文之前，請參閱[商務語音的適用國家與地區](country-region-availability.md)，以查看您的國家或地區是否支援含通話方案的商務語音。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-106">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="2f0b8-107">如果您的租用戶所在國家或地區不支援含通話方案的商務語音，請參閱[從 Microsoft 轉銷商或合作夥伴取得協助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-107">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="2f0b8-108">當您初次設定商務語音時，您將為主要公司線路以及任何您指派商務語音授權的使用者取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-108">When you first set up Business Voice, you will acquire phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="2f0b8-109">如果您已經有想要在移至商務語音時保留的電話號碼，您可以使用稱為電話號碼移轉的程序，將電話號碼帶至商務語音。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-109">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="2f0b8-110">在您將電話號碼移轉至商務語音後，您可以將電話號碼指派給使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-110">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="2f0b8-111">舊號碼會取代您設定商務語音時所取得的暫時性號碼。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-111">The old numbers replace the temporary numbers that you acquired when setting up Business Voice.</span></span>

<span data-ttu-id="2f0b8-112">在您將號碼移至商務語音前，請參閱[移轉電話號碼的常見問題](../phone-number-calling-plans/port-order-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-112">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="2f0b8-113">本文章包含問題的解答，包括：支援哪些國家和地區、可以和無法移轉的號碼，以及您需要的資訊。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-113">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="2f0b8-114">當您準備好將電話號碼移至商務語音時，請按照[將電話號碼移轉至 Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的步驟進行，以建立移植順序。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-114">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="2f0b8-115">順序包括將號碼從目前的電話服務電信業者移至商務語音所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-115">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="2f0b8-116">將電話號碼移至商務語音之後，您必須將其指派給人員。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-116">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="2f0b8-117">若要這麼做，請按照 [變更使用者的電話號碼](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-117">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="2f0b8-118">當您依照這些步驟操作時，您將會以您移轉過來的使用者的原始電話號碼取代暫時指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-118">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="2f0b8-119">如果您需要協助，請告訴我們！</span><span class="sxs-lookup"><span data-stu-id="2f0b8-119">If you need help, let us know!</span></span> <span data-ttu-id="2f0b8-120">我們會協助您盡可能輕鬆地將您的電話號碼移至商務語音。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-120">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="2f0b8-121">請務必包括下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2f0b8-121">Be sure to include the following information:</span></span>

- <span data-ttu-id="2f0b8-122">您的組織識別碼 (例如 ***contoso***.onmicrosoft.com)</span><span class="sxs-lookup"><span data-stu-id="2f0b8-122">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="2f0b8-123">您需要協助的類型和數量</span><span class="sxs-lookup"><span data-stu-id="2f0b8-123">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="2f0b8-124">您帳戶的授權人員</span><span class="sxs-lookup"><span data-stu-id="2f0b8-124">The authorizing person on your account</span></span>
- <span data-ttu-id="2f0b8-125">您所擁有的問題或疑問的描述</span><span class="sxs-lookup"><span data-stu-id="2f0b8-125">A description of the issue or question that you have</span></span>

<span data-ttu-id="2f0b8-126">如需有關加拿大和美國電話號碼的說明，請傳送您的要求至 [ptn@microsoft.com](mailto:ptn@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-126">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="2f0b8-127">如需歐洲電話號碼的說明，請將您的要求傳送至 [ptneu@microsoft.com](mailto:ptneu@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2f0b8-127">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>
