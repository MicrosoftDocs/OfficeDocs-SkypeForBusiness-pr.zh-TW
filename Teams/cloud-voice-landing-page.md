---
title: 規劃 Microsoft 團隊的語音方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 深入瞭解 Microsoft 團隊雲端語音功能，以及您將針對貴組織所做的部署決定。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16a2aea0d367c720cf36c8010670a34472ab43a
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701331"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="4cefc-103">規劃您的小組語音方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="4cefc-104">本文可協助您決定哪一種 Microsoft 語音解決方案適合您的組織。</span><span class="sxs-lookup"><span data-stu-id="4cefc-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="4cefc-105">決定之後，本文會提供內容的藍圖，讓您能夠實施您所選的方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="4cefc-106">如需規劃團隊語音方案的相關指導方針，以將其從商務用 Skype Server 升級至團隊的整體方案，請參閱 [從商務用 skype 內部部署升級至團隊的 PSTN 考慮](upgrade-to-Teams-on-prem-pstn-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="4cefc-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-Teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="4cefc-107">您可能想要最簡單的解決方案 &mdash; 電話系統使用通話方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="4cefc-108">這是 Microsoft 的雲端解決方案，可提供私人分支 Exchange (PBX) 功能，以及呼叫公用交換電話網絡 (PSTN) ，如下列圖表所示。</span><span class="sxs-lookup"><span data-stu-id="4cefc-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="4cefc-109">在這個方案中，Microsoft 是您 PSTN 運營商。</span><span class="sxs-lookup"><span data-stu-id="4cefc-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![圖表1顯示含有通話方案的電話系統](media/voice-solutions-simple.png)

<span data-ttu-id="4cefc-111">如果您對下列專案回答 [是]，就表示您可以使用 [電話撥入方案] 作為正確的方案：</span><span class="sxs-lookup"><span data-stu-id="4cefc-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="4cefc-112">您的地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="4cefc-113">您不需要保留目前的 PSTN 載波。</span><span class="sxs-lookup"><span data-stu-id="4cefc-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="4cefc-114">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="4cefc-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="4cefc-115">不過，您的情況可能會更複雜一些。</span><span class="sxs-lookup"><span data-stu-id="4cefc-115">However, your situation might be more complex.</span></span> <span data-ttu-id="4cefc-116">例如，您可能在無法使用通話方案的位置中有辦事處。</span><span class="sxs-lookup"><span data-stu-id="4cefc-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="4cefc-117">或者，您可能需要一個支援複雜的多國部署的組合解決方案，且不同地理位置的需求不同。</span><span class="sxs-lookup"><span data-stu-id="4cefc-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="4cefc-118">Microsoft 支援解決方案組合：</span><span class="sxs-lookup"><span data-stu-id="4cefc-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="4cefc-119">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="4cefc-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="4cefc-120">含直接佈線的電話系統與您自己的 PSTN 載波</span><span class="sxs-lookup"><span data-stu-id="4cefc-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="4cefc-121">結合直接佈線，搭配通話方案和電話系統使用電話系統的組合方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="4cefc-122">您需要閱讀什麼？</span><span class="sxs-lookup"><span data-stu-id="4cefc-122">What do you need to read?</span></span>

<span data-ttu-id="4cefc-123">**全是必要的。**</span><span class="sxs-lookup"><span data-stu-id="4cefc-123">**Required for all.**</span></span> <span data-ttu-id="4cefc-124">本文中的部分內容適用于所有組織。</span><span class="sxs-lookup"><span data-stu-id="4cefc-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="4cefc-125">例如，所有人都應該閱讀有關電話系統的資訊，並瞭解連線至公用交換電話網絡 (PSTN) 的選項。</span><span class="sxs-lookup"><span data-stu-id="4cefc-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="4cefc-126">全部需要</span><span class="sxs-lookup"><span data-stu-id="4cefc-126">Required for all</span></span> | <span data-ttu-id="4cefc-127">說明</span><span class="sxs-lookup"><span data-stu-id="4cefc-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="4cefc-128">**電話系統**</span><span class="sxs-lookup"><span data-stu-id="4cefc-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="4cefc-129">Microsoft 365 雲端與 Microsoft 團隊一起啟用呼叫控制和私人分支 Exchange (PBX) 功能的 Microsoft 技術。</span><span class="sxs-lookup"><span data-stu-id="4cefc-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="4cefc-130">**公用交換電話網絡 (PSTN) 連接選項**</span><span class="sxs-lookup"><span data-stu-id="4cefc-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="4cefc-131">您可以選擇使用 Microsoft 作為電話運營商，或使用直接路由將您自己的電話運營商連線至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="4cefc-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="4cefc-132">與電話系統搭配使用 PSTN 連線選項，讓您的使用者能夠撥打世界各地的電話。</span><span class="sxs-lookup"><span data-stu-id="4cefc-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="4cefc-133">**視您的需求而定。**</span><span class="sxs-lookup"><span data-stu-id="4cefc-133">**Depending on your requirements.**</span></span> <span data-ttu-id="4cefc-134">本文中的部分章節是根據您現有的部署與需求而相關。</span><span class="sxs-lookup"><span data-stu-id="4cefc-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="4cefc-135">例如，只有在地理位置不允許使用 [免付費旁路] 的直接路由客戶才需要 Location-Based 傳送。</span><span class="sxs-lookup"><span data-stu-id="4cefc-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="4cefc-136">考慮您可能需要下列哪些其他設定：</span><span class="sxs-lookup"><span data-stu-id="4cefc-136">Consider which of these additional configurations you might need:</span></span>

![圖2顯示其他語音元件，例如 Microsoft 的電話號碼、撥號方案和通話路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="4cefc-138">視您的需求而定</span><span class="sxs-lookup"><span data-stu-id="4cefc-138">Depending on your requirements</span></span> | <span data-ttu-id="4cefc-139">說明</span><span class="sxs-lookup"><span data-stu-id="4cefc-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="4cefc-140">**Microsoft 的電話號碼**</span><span class="sxs-lookup"><span data-stu-id="4cefc-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="4cefc-141">如何從 Microsoft 取得及管理電話號碼，以及如何將現有號碼轉移至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4cefc-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="4cefc-142">如果您需要取得 Microsoft 通話方案的電話號碼、轉移現有號碼、取得服務號碼等，請閱讀這種情況。</span><span class="sxs-lookup"><span data-stu-id="4cefc-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="4cefc-143">**撥號方案和呼叫路由**</span><span class="sxs-lookup"><span data-stu-id="4cefc-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="4cefc-144">如何設定和管理可將撥打的電話號碼轉換成替代格式的撥號方案 (通常是) 的撥號驗證及呼叫路由的 E. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="4cefc-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="4cefc-145">如果您需要瞭解什麼是撥號方案，以及是否需要指定貴組織的撥號方案，請閱讀此資訊。</span><span class="sxs-lookup"><span data-stu-id="4cefc-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="4cefc-146">**緊急通話**</span><span class="sxs-lookup"><span data-stu-id="4cefc-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="4cefc-147">如何管理和設定緊急呼叫， &mdash; 視 PSTN 連接選項而定。</span><span class="sxs-lookup"><span data-stu-id="4cefc-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="4cefc-148">如果您使用的是 Microsoft 通話方案或直接傳送，且需要瞭解如何管理組織的緊急通話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="4cefc-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="4cefc-149">**直接路由的以位置為基礎的路由**</span><span class="sxs-lookup"><span data-stu-id="4cefc-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="4cefc-150">如何使用 Location-Based 路由 (LBR) 根據其地理位置來限制 Microsoft 團隊使用者的付費略過。</span><span class="sxs-lookup"><span data-stu-id="4cefc-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="4cefc-151">如果您的組織在不允許使用 [免付費旁路] 的位置使用直接路由，請閱讀本節內容。</span><span class="sxs-lookup"><span data-stu-id="4cefc-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="4cefc-152">**雲端語音功能的網路拓撲**</span><span class="sxs-lookup"><span data-stu-id="4cefc-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="4cefc-153">如果您的組織是部署 Location-Based 路由 (LBR) 進行直接路由或動態緊急通話，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="4cefc-154">如果您要實現直接路由的 LBR，或者如果您是使用通話方案或直接路由來執行動態緊急通話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="4cefc-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="4cefc-155">**遷移現有的語音解決方案**</span><span class="sxs-lookup"><span data-stu-id="4cefc-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="4cefc-156">將您的語音解決方案遷移至小組時，需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="4cefc-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="4cefc-157">如果您是從現有的語音解決方案遷移至小組，請閱讀本節內容。</span><span class="sxs-lookup"><span data-stu-id="4cefc-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="4cefc-158">本文主要針對 Microsoft 團隊提供的語音方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="4cefc-159">雖然 [Microsoft 電話) 解決方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 中的商務用 Skype online 方案仍提供 (，但請務必瞭解2021年7月31日的商務用 skype online 將會停用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="4cefc-160">在該日期之後，商務用 Skype Online 服務將無法再存取。</span><span class="sxs-lookup"><span data-stu-id="4cefc-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="4cefc-161">此外， &mdash; 不論是透過商務用 Skype 伺服器或雲端連接器版本及商務用 Skype Online，您的內部部署環境之間的 PSTN &mdash; 連線都將不再受支援。</span><span class="sxs-lookup"><span data-stu-id="4cefc-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="4cefc-162">本文將說明團隊語音方案，以及如何使用直接路由將內部部署電話網絡（如有必要）連線至團隊。</span><span class="sxs-lookup"><span data-stu-id="4cefc-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="4cefc-163">電話系統</span><span class="sxs-lookup"><span data-stu-id="4cefc-163">Phone System</span></span>

<span data-ttu-id="4cefc-164">[電話系統] 是 Microsoft 的技術，可讓您在 Microsoft 365 或 Office 365 雲端中使用 microsoft 團隊來啟用呼叫控制和私人分支 Exchange (PBX) 功能。</span><span class="sxs-lookup"><span data-stu-id="4cefc-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="4cefc-165">[電話系統] 可與團隊或商務用 Skype 用戶端和認證的裝置搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="4cefc-166">[電話系統] 可讓您以從 Microsoft 365 或 Office 365 直接提供的一組功能取代現有的 PBX 系統。</span><span class="sxs-lookup"><span data-stu-id="4cefc-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="4cefc-167">貴組織中的使用者之間的呼叫是在手機系統內內部處理，而不會移至公用的交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="4cefc-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4cefc-168">這適用于您組織中位於不同地理區域的使用者之間的通話，並移除這些內部通話的長途成本。</span><span class="sxs-lookup"><span data-stu-id="4cefc-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="4cefc-169">本文將介紹下列電話系統金鑰功能與功能，以及您必須考慮的部署決定：</span><span class="sxs-lookup"><span data-stu-id="4cefc-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="4cefc-170">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="4cefc-171">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="4cefc-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="4cefc-172">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="4cefc-172">Calling identity</span></span>](#calling-identity)

![圖表3顯示手機系統包含自動語音應答及呼叫查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

<span data-ttu-id="4cefc-174">如需所有電話系統功能的相關資訊，以及如何設定電話系統，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-175">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="4cefc-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="4cefc-176">在組織中設定電話系統</span><span class="sxs-lookup"><span data-stu-id="4cefc-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="4cefc-177">說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費電話號碼的通訊點數。</span><span class="sxs-lookup"><span data-stu-id="4cefc-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="4cefc-178">如需管理支援的裝置的相關資訊，請參閱在 Microsoft 團隊和[小組 Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[中管理您的裝置](devices/device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="4cefc-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="4cefc-179">自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="4cefc-180">自動語音應答可讓您根據本機號碼來設定功能表選項，以路由通話。</span><span class="sxs-lookup"><span data-stu-id="4cefc-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="4cefc-181">通話佇列是呼叫者的等待區域。</span><span class="sxs-lookup"><span data-stu-id="4cefc-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="4cefc-182">[自動語音應答] 和 [呼叫佇列] 可搭配使用，輕鬆地將呼叫者路由至組織中的適當人員或部門。</span><span class="sxs-lookup"><span data-stu-id="4cefc-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="4cefc-183">如需自動語音應答和通話佇列的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-184">規劃小組自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="4cefc-185">設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="4cefc-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="4cefc-186">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="4cefc-187">Contoso 案例研究：自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="4cefc-188">說明虛構的多國企業（Contoso）如何針對其語音方案實施自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="4cefc-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="4cefc-189">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="4cefc-189">Cloud Voicemail</span></span>

<span data-ttu-id="4cefc-190">雲端語音信箱（由 Azure 語音信箱服務提供技術支援）只支援在 Exchange 信箱中存款語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4cefc-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="4cefc-191">它不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="4cefc-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="4cefc-192">雲端語音信箱包括語音信箱，預設會針對貴組織中的所有使用者啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="4cefc-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="4cefc-193">您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4cefc-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="4cefc-194">針對僅限線上使用者，在指派電話系統授權之後，系統會自動為使用者設定及設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4cefc-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="4cefc-195">針對有 Exchange 信箱的電話系統使用者，您需要執行額外的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="4cefc-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="4cefc-196">如需有關雲端語音信箱及其設定的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-197">設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="4cefc-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="4cefc-198">在組織中設定語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4cefc-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="4cefc-199">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="4cefc-199">Calling identity</span></span>

<span data-ttu-id="4cefc-200">根據預設，所有的呼出通話會使用指派的電話號碼來呼叫身分識別 (來電者識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="4cefc-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="4cefc-201">通話的收件者可以快速識別來電者，決定是否要接受或拒絕通話。</span><span class="sxs-lookup"><span data-stu-id="4cefc-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="4cefc-202">如需設定本機號碼或變更或封鎖本機號碼的相關資訊，請參閱 [設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4cefc-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="4cefc-203">公用交換電話網路連接選項</span><span class="sxs-lookup"><span data-stu-id="4cefc-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="4cefc-204">電話系統為您的組織提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="4cefc-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="4cefc-205">不過，若要讓使用者撥打貴組織外的通話，您必須將電話系統連線至公用的交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="4cefc-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4cefc-206">若要將電話系統連線至 PSTN，您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="4cefc-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="4cefc-207">[**含有通話方案的電話系統**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="4cefc-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="4cefc-208">以 Microsoft 作為 PSTN 運營商的一體式雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="4cefc-209">使用直接路由將內部部署環境連接至團隊的 [**電話系統（含您自己的 PSTN 載波）**](#phone-system-with-own-pstn-carrier-with-direct-routing) 。</span><span class="sxs-lookup"><span data-stu-id="4cefc-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="4cefc-210">您也可以選擇組合選項，讓您設計複雜環境的解決方案，或管理多重步驟的遷移 (稍後) 的其他遷移。</span><span class="sxs-lookup"><span data-stu-id="4cefc-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="4cefc-211">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="4cefc-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="4cefc-212">如本文先前所述，使用通話方案的電話系統是適用于團隊使用者的 Microsoft 的雲端語音方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="4cefc-213">這是最簡單的選項，可將 Microsoft 手機系統連線到公開交換的電話網絡 (PSTN) ，以讓世界各地的電話與行動裝置市話。</span><span class="sxs-lookup"><span data-stu-id="4cefc-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="4cefc-214">透過此選項，Microsoft 可為您的組織提供私人分支 Exchange (PBX) 功能，並充當 PSTN 運營商，如下列圖表所示：</span><span class="sxs-lookup"><span data-stu-id="4cefc-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![圖表4顯示含自動語音應答、通話佇列、本機號碼等等，以及 Microsoft 作為 PSTN 載波的電話系統](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="4cefc-216">如果您對下列專案回答 [是]，就表示您可以使用 [電話撥入方案] 作為正確的方案：</span><span class="sxs-lookup"><span data-stu-id="4cefc-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="4cefc-217">您的地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="4cefc-218">您不需要保留目前的 PSTN 載波。</span><span class="sxs-lookup"><span data-stu-id="4cefc-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="4cefc-219">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="4cefc-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="4cefc-220">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="4cefc-220">With this option:</span></span> 

- <span data-ttu-id="4cefc-221">您可以在 Microsoft 手機系統隨附新增國內或國際通話方案（可讓世界各地的電話撥打電話） (，視授權) 的服務等級而定。</span><span class="sxs-lookup"><span data-stu-id="4cefc-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="4cefc-222">您不需要部署或維護內部部署的部署， &mdash; 因為通話方案不會在 Microsoft 365 或 Office 365 上運作。</span><span class="sxs-lookup"><span data-stu-id="4cefc-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="4cefc-223">注意：如有必要，您可以選擇將受支援的會話邊界控制器 (SBC) ，透過直接路由取得與 SBC 所支援的協力廠商 Pbx、類比裝置及其他協力廠商電話裝置的互通性。</span><span class="sxs-lookup"><span data-stu-id="4cefc-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="4cefc-224">此選項需要不間斷地連線至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4cefc-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="4cefc-225">如需通話方案的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-226">哪一個通話方案適合您？</span><span class="sxs-lookup"><span data-stu-id="4cefc-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="4cefc-227">如何購買通話方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="4cefc-228">通話方案的適用國家與地區</span><span class="sxs-lookup"><span data-stu-id="4cefc-228">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="4cefc-229">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="4cefc-230">含直接佈線的有自己 PSTN 載波的電話系統</span><span class="sxs-lookup"><span data-stu-id="4cefc-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="4cefc-231">此選項使用直接路由將 Microsoft Phone 系統連線到電話網絡，如下列圖表所示：</span><span class="sxs-lookup"><span data-stu-id="4cefc-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![圖表5顯示含直接路由的電話系統](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="4cefc-233">如果您對下列問題回答 [是]，則使用直接路由的電話系統就是適合您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="4cefc-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="4cefc-234">您想要將團隊與電話系統搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="4cefc-235">您必須保留目前的 PSTN 載波。</span><span class="sxs-lookup"><span data-stu-id="4cefc-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="4cefc-236">您想要混合路由，有些呼叫是透過通話方案進行，有些是透過您的運營商進行。</span><span class="sxs-lookup"><span data-stu-id="4cefc-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="4cefc-237">您必須與協力廠商的 Pbx 和/或裝置進行交互操作，例如，我們的系統開銷呼叫器、類比裝置等。</span><span class="sxs-lookup"><span data-stu-id="4cefc-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="4cefc-238">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="4cefc-238">With this option:</span></span>

- <span data-ttu-id="4cefc-239">您可以將自己的支援 SBC 連接到 Microsoft Phone System，而不需要額外的內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="4cefc-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="4cefc-240">您幾乎可以在 Microsoft Phone 系統中使用任何電話運營商。</span><span class="sxs-lookup"><span data-stu-id="4cefc-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="4cefc-241">您可以選擇設定和管理此選項，或由您的運營商或合作夥伴 (詢問您的承運人或合作夥伴是否提供此選項) 。</span><span class="sxs-lookup"><span data-stu-id="4cefc-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="4cefc-242">您可以設定您的電話裝置 &mdash; （例如協力廠商 PBX 和模擬裝置 &mdash; 與 Microsoft Phone 系統）之間的互通性。</span><span class="sxs-lookup"><span data-stu-id="4cefc-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="4cefc-243">此選項需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="4cefc-243">This option requires the following:</span></span>

- <span data-ttu-id="4cefc-244">無法中斷連接至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4cefc-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="4cefc-245">部署及維護支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="4cefc-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="4cefc-246">含協力廠商承運人的合同。</span><span class="sxs-lookup"><span data-stu-id="4cefc-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="4cefc-247"> (除非部署為選項，才能為使用通話方案的電話系統上的使用者提供與協力廠商 PBX、類比裝置或其他電話裝置的連線。 ) </span><span class="sxs-lookup"><span data-stu-id="4cefc-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="4cefc-248">如需直接路由的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-249">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="4cefc-250">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="4cefc-251">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="4cefc-252">管理與直接路由搭配使用的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="4cefc-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="4cefc-253">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="4cefc-254">通過直接路由認證的工作階段邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="4cefc-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="4cefc-255">Microsoft 的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4cefc-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="4cefc-256">Microsoft 提供兩種電話號碼類型： *訂閱者* (使用者) 號碼，您可以將其指派給組織中的使用者，也可以指派 *服務* 號碼，提供付費和免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="4cefc-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="4cefc-257">服務號碼的併發通話容量高於訂閱者號碼，而且可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。</span><span class="sxs-lookup"><span data-stu-id="4cefc-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="4cefc-258">您將需要決定：</span><span class="sxs-lookup"><span data-stu-id="4cefc-258">You will need to decide:</span></span>

- <span data-ttu-id="4cefc-259">哪些使用者位置需要來自 Microsoft 的新電話號碼？</span><span class="sxs-lookup"><span data-stu-id="4cefc-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="4cefc-260"> (訂閱者或服務) 需要哪種電話號碼？</span><span class="sxs-lookup"><span data-stu-id="4cefc-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="4cefc-261">我要如何將現有的電話號碼移植至團隊？</span><span class="sxs-lookup"><span data-stu-id="4cefc-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="4cefc-262">如需在組織中管理電話號碼的詳細資訊，包括取得新號碼或轉接現有號碼，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-263">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4cefc-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="4cefc-264">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4cefc-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="4cefc-265">為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="4cefc-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="4cefc-266">將電話號碼轉移至 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="4cefc-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="4cefc-267">撥號方案和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-267">Dial plans and call routing</span></span>

<span data-ttu-id="4cefc-268">撥號方案是一組正常化規則，將撥打的電話號碼轉換成替換格式， (通常是) 的 E. 164 個格式，用於呼叫授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="4cefc-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="4cefc-269">您必須決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="4cefc-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="4cefc-270">我的組織需要自訂的撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="4cefc-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="4cefc-271">哪些使用者需要自訂的撥號方案？</span><span class="sxs-lookup"><span data-stu-id="4cefc-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="4cefc-272">應該將哪個租使用者撥號方案指派給每個使用者？</span><span class="sxs-lookup"><span data-stu-id="4cefc-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="4cefc-273">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="4cefc-274">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="4cefc-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="4cefc-275">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="4cefc-276">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4cefc-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="4cefc-277">緊急電話</span><span class="sxs-lookup"><span data-stu-id="4cefc-277">Emergency calling</span></span>

<span data-ttu-id="4cefc-278">您設定緊急呼叫的方式會根據 PSTN 連線選項而有所不同： Microsoft 通話方案或直接傳送。</span><span class="sxs-lookup"><span data-stu-id="4cefc-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="4cefc-279">Microsoft 通話方案和電話系統直連路由的動態緊急通話可提供設定及路由緊急通話的功能，並根據團隊用戶端的目前位置來通知安全人員。</span><span class="sxs-lookup"><span data-stu-id="4cefc-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="4cefc-280">如需緊急呼叫概念與術語的詳細資訊，以及如何設定動態緊急通話，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-281">管理緊急通話</span><span class="sxs-lookup"><span data-stu-id="4cefc-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4cefc-282">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="4cefc-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="4cefc-283">Contoso 案例研究：緊急通話</span><span class="sxs-lookup"><span data-stu-id="4cefc-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="4cefc-284">說明虛構的多國企業（Contoso）如何針對其組織實現緊急通話。</span><span class="sxs-lookup"><span data-stu-id="4cefc-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="4cefc-285">直接路由 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="4cefc-286">在某些國家和地區，不一定要略過公開交換的電話網絡 (PSTN) 提供者來減少長途通話成本。</span><span class="sxs-lookup"><span data-stu-id="4cefc-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="4cefc-287">[Location-Based 傳送直接路由功能] 可讓您根據地理位置限制 Microsoft 團隊使用者的付費略過。</span><span class="sxs-lookup"><span data-stu-id="4cefc-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="4cefc-288">如需如何規劃及設定 Location-Based 路由 (LBR) 的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="4cefc-289">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="4cefc-290">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="4cefc-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="4cefc-291">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="4cefc-292">Contoso 案例研究： Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="4cefc-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="4cefc-293">說明虛構的多國企業（Contoso）如何針對其組織實施 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="4cefc-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="4cefc-294">語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="4cefc-294">Network topology for voice features</span></span>

<span data-ttu-id="4cefc-295">如果您要部署動態緊急通話或 Location-Based 路由以進行直接路由，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="4cefc-296">若要瞭解如何設定網路區域、網路網站、網路子網和信任的 IP 位址的網路設定，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="4cefc-297">Microsoft 團隊中雲端語音功能的網路設定-概念與術語</span><span class="sxs-lookup"><span data-stu-id="4cefc-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="4cefc-298">在 Microsoft 團隊中管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="4cefc-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="4cefc-299">將現有的語音解決方案遷移至團隊</span><span class="sxs-lookup"><span data-stu-id="4cefc-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="4cefc-300">針對升級至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="4cefc-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="4cefc-301">只有在使用者處於 TeamsOnly 模式時，才會支援將電話系統與團隊一起使用。</span><span class="sxs-lookup"><span data-stu-id="4cefc-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="4cefc-302">如果您需要升級至團隊的基本資訊，請從這裡開始：</span><span class="sxs-lookup"><span data-stu-id="4cefc-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="4cefc-303">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4cefc-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="4cefc-304">關於升級架構</span><span class="sxs-lookup"><span data-stu-id="4cefc-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="4cefc-305">從商務用 Skype 升級至團隊-適用于 IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4cefc-305">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

<span data-ttu-id="4cefc-306">當您遷移您的語音解決方案時，當您移至 TeamsOnly 模式時，可能會有四個通話案例：</span><span class="sxs-lookup"><span data-stu-id="4cefc-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="4cefc-307">[**商務用 Skype Online 中的使用者，包含 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="4cefc-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="4cefc-308">升級時，此使用者將會繼續進行 Microsoft 通話計畫。</span><span class="sxs-lookup"><span data-stu-id="4cefc-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="4cefc-309">**[商務用 skype Online 中的使用者，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) 可透過商務用 skype 內部部署或雲端連接器版本使用內部部署語音功能**。</span><span class="sxs-lookup"><span data-stu-id="4cefc-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="4cefc-310">使用者在小組中的升級需要與使用者遷移以直接傳送路由，以確保 TeamsOnly 使用者有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="4cefc-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="4cefc-311">**[在商務用 Skype 內部部署中使用企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，他們將會移至線上並保留內部部署 PSTN 連線**。</span><span class="sxs-lookup"><span data-stu-id="4cefc-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="4cefc-312">將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將使用者的遷移轉移至直接傳送路線。</span><span class="sxs-lookup"><span data-stu-id="4cefc-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="4cefc-313">**[在商務用 Skype 內部部署中使用企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，他們將會移至線上並使用 Microsoft 通話方案**。</span><span class="sxs-lookup"><span data-stu-id="4cefc-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="4cefc-314">將此使用者遷移至小組需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將該使用者電話號碼的埠與) 的埠進行協調，) 從可用的地區指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="4cefc-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="4cefc-315">如需如何針對這些案例實施語音遷移的詳細資訊 &mdash; ，包括您需要設定混合式連線的相關資訊，以及如何使用內部部署語音功能將使用者遷移至直接佈線， &mdash; 請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="4cefc-316">升級至小組所需的 PSTN 考慮-適用于 IT 系統管理員</span><span class="sxs-lookup"><span data-stu-id="4cefc-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="4cefc-317">Contoso 語音遷移案例研究</span><span class="sxs-lookup"><span data-stu-id="4cefc-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="4cefc-318">案例研究說明虛構的多國公司（Contoso）如何針對其組織實施小組語音方案。</span><span class="sxs-lookup"><span data-stu-id="4cefc-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="4cefc-319">它包含下列文章：</span><span class="sxs-lookup"><span data-stu-id="4cefc-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="4cefc-320">團隊升級方案</span><span class="sxs-lookup"><span data-stu-id="4cefc-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="4cefc-321">電話系統和 PSTN 連線選項</span><span class="sxs-lookup"><span data-stu-id="4cefc-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="4cefc-322">以位置為基礎的路由實施</span><span class="sxs-lookup"><span data-stu-id="4cefc-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="4cefc-323">緊急通話</span><span class="sxs-lookup"><span data-stu-id="4cefc-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="4cefc-324">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="4cefc-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="4cefc-325">音訊會議</span><span class="sxs-lookup"><span data-stu-id="4cefc-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












