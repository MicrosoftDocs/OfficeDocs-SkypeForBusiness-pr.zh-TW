---
title: Microsoft Teams 中的通話方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 決定哪一個 Microsoft Phone 系統通話方案最適合在 Teams 中的雲端語音上為貴組織服務。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102729"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="4b11a-103">哪一個通話方案適合您？</span><span class="sxs-lookup"><span data-stu-id="4b11a-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="4b11a-104">您已完成開始使用[。](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="4b11a-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="4b11a-105">您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="4b11a-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="4b11a-106">您可能已經部署會議 [&會議](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="4b11a-107">現在，您已準備好新增雲端語音工作負載，而且您決定使用 Microsoft Phone System 與通話方案，以連接到公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="4b11a-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="4b11a-108">本文將說明通話方案的核心部署決策，以及您可能要根據貴組織的需求設定的其他考慮。</span><span class="sxs-lookup"><span data-stu-id="4b11a-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="4b11a-109">您也應該閱讀 [Microsoft Teams 中的雲端語音](cloud-voice-landing-page.md) ，以瞭解更多關於 Microsoft 雲端語音產品的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b11a-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="4b11a-110">深入瞭解通話方案</span><span class="sxs-lookup"><span data-stu-id="4b11a-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="4b11a-111">下列文章提供有關部署及使用 Microsoft 通話方案之詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="4b11a-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="4b11a-112">Microsoft 365 或 Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="4b11a-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="4b11a-113">Microsoft 365 或 Office 365 的通話方案</span><span class="sxs-lookup"><span data-stu-id="4b11a-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="4b11a-114">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="4b11a-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="4b11a-115">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="4b11a-115">Core deployment decisions</span></span>

<span data-ttu-id="4b11a-116">若要使用 Microsoft 做為電話電信業者，您必須取得通話方案授權，並將授權指派給電話系統使用者。</span><span class="sxs-lookup"><span data-stu-id="4b11a-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="4b11a-117">有兩種類型的通話方案可用：</span><span class="sxs-lookup"><span data-stu-id="4b11a-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="4b11a-118">國內通話方案</span><span class="sxs-lookup"><span data-stu-id="4b11a-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="4b11a-119">國內和國際通話方案</span><span class="sxs-lookup"><span data-stu-id="4b11a-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="4b11a-120">問問自己</span><span class="sxs-lookup"><span data-stu-id="4b11a-120">Ask yourself</span></span>|<span data-ttu-id="4b11a-121">動作</span><span class="sxs-lookup"><span data-stu-id="4b11a-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="4b11a-122">我的地區是否提供通話方案？</span><span class="sxs-lookup"><span data-stu-id="4b11a-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="4b11a-123">哪些使用者位置會提供通話方案服務？</span><span class="sxs-lookup"><span data-stu-id="4b11a-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="4b11a-124">詳細資訊，請參閱音訊會議與通話方案的國家 [/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="4b11a-125">我的使用者是否需要國際電話？</span><span class="sxs-lookup"><span data-stu-id="4b11a-125">Do my users need international calling?</span></span> | <span data-ttu-id="4b11a-126">詳細資訊，請參閱 [Microsoft 365 或 Office 365 的通話方案](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="4b11a-127">我的使用者是否擁有通話方案授權？</span><span class="sxs-lookup"><span data-stu-id="4b11a-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="4b11a-128">若要購買及指派授權，請參閱 [步驟 2：購買及指派授權](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="4b11a-129">我的使用者是否都有直接撥入 (號碼) 電話號碼？</span><span class="sxs-lookup"><span data-stu-id="4b11a-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="4b11a-130">若要取得電話號碼，請參閱 [步驟 3：取得電話號碼](set-up-calling-plans.md#step-3-get-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="4b11a-131">將電話號碼轉接至 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="4b11a-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="4b11a-132">您可輕鬆將目前服務提供者的電話號碼移轉至 Teams。</span><span class="sxs-lookup"><span data-stu-id="4b11a-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="4b11a-133">將電話號碼移植到 Teams 之後，Microsoft 會成為您的服務提供者，並且會針對這些電話號碼向您計費。</span><span class="sxs-lookup"><span data-stu-id="4b11a-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="4b11a-134">詳細資訊，請參閱將 [電話號碼轉接至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="4b11a-135">電話號碼和緊急位置</span><span class="sxs-lookup"><span data-stu-id="4b11a-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="4b11a-136">使用 Microsoft 365 或 Office 365 中的通話方案，貴組織的每個使用者必須擁有唯一的直撥 (DID) 電話號碼和對應的已驗證緊急位址。</span><span class="sxs-lookup"><span data-stu-id="4b11a-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="4b11a-137">您也可以在緊急位址內指定緊急 (例如辦公室號碼或樓面號碼) 。</span><span class="sxs-lookup"><span data-stu-id="4b11a-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="4b11a-138">問問自己</span><span class="sxs-lookup"><span data-stu-id="4b11a-138">Ask yourself</span></span>|<span data-ttu-id="4b11a-139">動作</span><span class="sxs-lookup"><span data-stu-id="4b11a-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="4b11a-140">我想要緊急位址和位置資訊的詳細資料如何？</span><span class="sxs-lookup"><span data-stu-id="4b11a-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="4b11a-141">詳細資訊，請參閱 [什麼是緊急位置、位址和通話路由？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。</span><span class="sxs-lookup"><span data-stu-id="4b11a-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="4b11a-142">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="4b11a-142">Calling identity</span></span>

<span data-ttu-id="4b11a-143">根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。</span><span class="sxs-lookup"><span data-stu-id="4b11a-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="4b11a-144">來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。</span><span class="sxs-lookup"><span data-stu-id="4b11a-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="4b11a-145">問問自己</span><span class="sxs-lookup"><span data-stu-id="4b11a-145">Ask yourself</span></span>|<span data-ttu-id="4b11a-146">動作</span><span class="sxs-lookup"><span data-stu-id="4b11a-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="4b11a-147">我要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="4b11a-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="4b11a-148">若要變更或封鎖本機號碼，請參閱[設定使用者的本機號碼。](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="4b11a-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||