---
title: Microsoft 團隊中的通話方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: '[通話方案] 登陸頁面'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83e2516ac9fd142c6cb965539ff22c4900811888
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237165"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="856d4-103">哪一種通話方案最適合您？</span><span class="sxs-lookup"><span data-stu-id="856d4-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="856d4-104">您已完成[快速入門](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="856d4-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="856d4-105">您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。</span><span class="sxs-lookup"><span data-stu-id="856d4-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="856d4-106">也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。</span><span class="sxs-lookup"><span data-stu-id="856d4-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="856d4-107">現在您已經準備好要新增雲端語音工作負載, 而您決定使用 Microsoft 手機系統搭配通話方案來連線至公用的交換電話網絡 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="856d4-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="856d4-108">本文說明通話方案的核心部署決定, 以及您可能想要根據貴組織的需求設定的其他考慮。</span><span class="sxs-lookup"><span data-stu-id="856d4-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="856d4-109">您也應該閱讀[Microsoft 團隊中的雲端語音](cloud-voice-landing-page.md), 以取得關於 Microsoft 雲端語音服務的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="856d4-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="856d4-110">深入瞭解通話方案</span><span class="sxs-lookup"><span data-stu-id="856d4-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="856d4-111">下列文章提供有關部署和使用 Microsoft 通話方案的詳細資訊:</span><span class="sxs-lookup"><span data-stu-id="856d4-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="856d4-112">Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="856d4-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="856d4-113">Office 365 的通話方案</span><span class="sxs-lookup"><span data-stu-id="856d4-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="856d4-114">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="856d4-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="856d4-115">核心部署決定</span><span class="sxs-lookup"><span data-stu-id="856d4-115">Core deployment decisions</span></span>

<span data-ttu-id="856d4-116">若要使用 Microsoft 作為您的電話語音運營商, 您必須取得通話方案授權, 並將其指派給您的電話系統使用者。</span><span class="sxs-lookup"><span data-stu-id="856d4-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="856d4-117">提供兩種通話方案類型:</span><span class="sxs-lookup"><span data-stu-id="856d4-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="856d4-118">國內通話方案</span><span class="sxs-lookup"><span data-stu-id="856d4-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="856d4-119">國內和國際通話方案</span><span class="sxs-lookup"><span data-stu-id="856d4-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="856d4-120">問自己</span><span class="sxs-lookup"><span data-stu-id="856d4-120">Ask yourself</span></span>|<span data-ttu-id="856d4-121">執行</span><span class="sxs-lookup"><span data-stu-id="856d4-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="856d4-122">我的區域是否提供通話方案？</span><span class="sxs-lookup"><span data-stu-id="856d4-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="856d4-123">哪些使用者位置將會有通話計畫服務？</span><span class="sxs-lookup"><span data-stu-id="856d4-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="856d4-124">如需詳細資訊, 請參閱[音訊會議與通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="856d4-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="856d4-125">我的使用者需要國際通話嗎？</span><span class="sxs-lookup"><span data-stu-id="856d4-125">Do my users need international calling?</span></span> | <span data-ttu-id="856d4-126">如需詳細資訊, 請參閱[Office 365 的通話方案](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="856d4-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="856d4-127">我的使用者是否有通話方案授權？</span><span class="sxs-lookup"><span data-stu-id="856d4-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="856d4-128">若要購買並指派授權, 請參閱[步驟 2: 購買並指派授權](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="856d4-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="856d4-129">我的使用者每個都有直向撥打電話號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="856d4-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="856d4-130">若要取得電話號碼, 請參閱[步驟 3: 取得電話號碼](set-up-calling-plans.md#step-3-get-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="856d4-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="856d4-131">將電話號碼傳送至 Office 365</span><span class="sxs-lookup"><span data-stu-id="856d4-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="856d4-132">您可以輕鬆地將您的電話號碼從目前的服務提供者轉接至團隊。</span><span class="sxs-lookup"><span data-stu-id="856d4-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="856d4-133">在您將電話號碼移植至團隊後, Microsoft 就會成為您的服務提供者, 並將您的電話號碼帳單。</span><span class="sxs-lookup"><span data-stu-id="856d4-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="856d4-134">如需詳細資訊, 請參閱[將電話號碼轉移至 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="856d4-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="856d4-135">電話號碼和緊急位置</span><span class="sxs-lookup"><span data-stu-id="856d4-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="856d4-136">使用 Office 365 中的通話方案, 貴組織中的每位使用者都必須有一個唯一的直接撥出電話號碼, 以及對應的驗證緊急位址。</span><span class="sxs-lookup"><span data-stu-id="856d4-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="856d4-137">您也可以在緊急位址內指定緊急地點 (例如, 辦公室號碼或底價編號)。</span><span class="sxs-lookup"><span data-stu-id="856d4-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="856d4-138">問自己</span><span class="sxs-lookup"><span data-stu-id="856d4-138">Ask yourself</span></span>|<span data-ttu-id="856d4-139">執行</span><span class="sxs-lookup"><span data-stu-id="856d4-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="856d4-140">我要如何詳細說明緊急位址和位置資訊？</span><span class="sxs-lookup"><span data-stu-id="856d4-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="856d4-141">如需詳細資訊, 請參閱[什麼是緊急位置、位址及呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。</span><span class="sxs-lookup"><span data-stu-id="856d4-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="856d4-142">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="856d4-142">Calling identity</span></span>

<span data-ttu-id="856d4-143">根據預設, 所有出站通話都會將指派的電話號碼做為呼叫身分識別 (來電者識別碼)。</span><span class="sxs-lookup"><span data-stu-id="856d4-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="856d4-144">通話的收件者可以快速識別來電者, 決定是否要接受或拒絕通話。</span><span class="sxs-lookup"><span data-stu-id="856d4-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="856d4-145">問自己</span><span class="sxs-lookup"><span data-stu-id="856d4-145">Ask yourself</span></span>|<span data-ttu-id="856d4-146">執行</span><span class="sxs-lookup"><span data-stu-id="856d4-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="856d4-147">我想要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="856d4-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="856d4-148">若要變更或封鎖本機號碼, 請參閱[設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="856d4-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




