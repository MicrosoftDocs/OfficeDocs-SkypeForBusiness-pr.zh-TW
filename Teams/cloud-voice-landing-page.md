---
title: 在 Microsoft Teams 中規劃語音解決方案
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
description: 深入瞭解 Microsoft Teams 雲端語音功能，以及您將為貴組織做出部署決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d77e0b1ec6277bfeffd85d6657d14fe810aae96
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102569"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="c95e8-103">規劃您的 Teams 語音解決方案</span><span class="sxs-lookup"><span data-stu-id="c95e8-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="c95e8-104">本文可協助您決定適合貴組織的 Microsoft 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="c95e8-105">在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="c95e8-106">請參閱從商務用 Skype 內部部署升級至 Teams 的 [PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)考慮，以規劃 Teams 語音解決方案做為整體規劃的一部分。</span><span class="sxs-lookup"><span data-stu-id="c95e8-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="c95e8-107">您可能會想要最簡單的解決方案電話 &mdash; 系統與通話方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="c95e8-108">這是 Microsoft 的全雲端解決方案，提供私人分支 Exchange (PBX) 功能，以及撥打公用交換電話網絡 (PSTN) ，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c95e8-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="c95e8-109">有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="c95e8-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![圖表 1 顯示具有通話方案的電話系統](media/voice-solutions-simple.png)

<span data-ttu-id="c95e8-111">如果您對下列專案回答是，則電話系統與通話方案是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="c95e8-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="c95e8-112">地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="c95e8-113">您不需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="c95e8-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="c95e8-114">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="c95e8-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="c95e8-115">不過，您的情況可能較為複雜。</span><span class="sxs-lookup"><span data-stu-id="c95e8-115">However, your situation might be more complex.</span></span> <span data-ttu-id="c95e8-116">例如，您可能在無法使用通話方案的位置有辦公室。</span><span class="sxs-lookup"><span data-stu-id="c95e8-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="c95e8-117">或者，您可能需要支援複雜、多國部署的組合解決方案，且不同的地理位置有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="c95e8-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="c95e8-118">Microsoft 支援一組解決方案：</span><span class="sxs-lookup"><span data-stu-id="c95e8-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="c95e8-119">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="c95e8-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="c95e8-120">具有您 PSTN 電信商的電話系統與直接路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="c95e8-121">使用電話系統搭配通話方案與電話系統與直接路由的組合解決方案</span><span class="sxs-lookup"><span data-stu-id="c95e8-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="c95e8-122">您需要閱讀哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="c95e8-122">What do you need to read?</span></span>

<span data-ttu-id="c95e8-123">**全部為必填專案。**</span><span class="sxs-lookup"><span data-stu-id="c95e8-123">**Required for all.**</span></span> <span data-ttu-id="c95e8-124">本文中的部分章節與所有組織有關。</span><span class="sxs-lookup"><span data-stu-id="c95e8-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="c95e8-125">例如，每個人都應該閱讀電話系統，並瞭解在 PSTN (上連接公用電話) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="c95e8-126">全部為必填專案</span><span class="sxs-lookup"><span data-stu-id="c95e8-126">Required for all</span></span> | <span data-ttu-id="c95e8-127">說明</span><span class="sxs-lookup"><span data-stu-id="c95e8-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="c95e8-128">**電話系統**</span><span class="sxs-lookup"><span data-stu-id="c95e8-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="c95e8-129">Microsoft 在 Microsoft 365 雲端與 Microsoft Teams 中啟用通話控制和私人分支 Exchange (PBX) 功能的技術。</span><span class="sxs-lookup"><span data-stu-id="c95e8-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="c95e8-130">**公用交換電話網絡 (PSTN) 連接選項**</span><span class="sxs-lookup"><span data-stu-id="c95e8-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="c95e8-131">選擇使用 Microsoft 做為電話電信業者，或使用直接路由將您自己的電話電信業者連接到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c95e8-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="c95e8-132">PSTN 連接選項與電話系統結合，可讓使用者撥打全球電話。</span><span class="sxs-lookup"><span data-stu-id="c95e8-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="c95e8-133">**視您的需求而不同。**</span><span class="sxs-lookup"><span data-stu-id="c95e8-133">**Depending on your requirements.**</span></span> <span data-ttu-id="c95e8-134">本文中的部分章節會根據您的現有部署和需求而相關。</span><span class="sxs-lookup"><span data-stu-id="c95e8-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="c95e8-135">例如，Location-Based不允許免付費路的地理位置中的直接路由客戶，才需要直接路由。</span><span class="sxs-lookup"><span data-stu-id="c95e8-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="c95e8-136">請考慮您可能需要的這些額外配置：</span><span class="sxs-lookup"><span data-stu-id="c95e8-136">Consider which of these additional configurations you might need:</span></span>

![圖表 2 顯示其他語音元件，例如 Microsoft 的電話號碼、撥號方案及通話路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="c95e8-138">視您的需求而不同</span><span class="sxs-lookup"><span data-stu-id="c95e8-138">Depending on your requirements</span></span> | <span data-ttu-id="c95e8-139">說明</span><span class="sxs-lookup"><span data-stu-id="c95e8-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="c95e8-140">**Microsoft 的電話號碼**</span><span class="sxs-lookup"><span data-stu-id="c95e8-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="c95e8-141">如何取得和管理 Microsoft 的電話號碼，以及如何將現有的號碼移轉至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c95e8-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="c95e8-142">如果您需要取得 Microsoft 通話方案的電話號碼、轉接現有號碼、取得服務號碼等，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="c95e8-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="c95e8-143">**撥號方案與通話路由**</span><span class="sxs-lookup"><span data-stu-id="c95e8-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="c95e8-144">如何設定及管理撥號方案，將撥號電話號碼轉換成替代格式 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c95e8-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="c95e8-145">如果您需要瞭解什麼是撥號方案，以及您是否需要為貴組織指定撥號方案，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="c95e8-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="c95e8-146">**緊急電話**</span><span class="sxs-lookup"><span data-stu-id="c95e8-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="c95e8-147">如何管理及設定緊急電話 &mdash; ，取決於您的 PSTN 連接選項。</span><span class="sxs-lookup"><span data-stu-id="c95e8-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="c95e8-148">如果您使用的是 Microsoft 通話方案或直接路由，並需要瞭解如何管理組織的緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="c95e8-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="c95e8-149">**直接路由的基於位置的路由**</span><span class="sxs-lookup"><span data-stu-id="c95e8-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="c95e8-150">如何使用 Location-Based路由 (LBR) 根據 Microsoft Teams 使用者的地理位置來限制免付費。</span><span class="sxs-lookup"><span data-stu-id="c95e8-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="c95e8-151">如果貴組織在不允許免付費路的位置使用直接路由，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="c95e8-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="c95e8-152">**雲端語音功能的網路拓撲**</span><span class="sxs-lookup"><span data-stu-id="c95e8-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="c95e8-153">如果貴組織正在部署 Location-Based路由 (LBR) 直接路由或動態緊急電話，您必須設定網路設定，以用於 Microsoft Teams 中的這些功能。</span><span class="sxs-lookup"><span data-stu-id="c95e8-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="c95e8-154">如果您正針對直接路由執行 LBR，或是使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="c95e8-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="c95e8-155">**遷移現有的語音解決方案**</span><span class="sxs-lookup"><span data-stu-id="c95e8-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="c95e8-156">將語音解決方案移遷移到 Teams 時，您需要思考的問題。</span><span class="sxs-lookup"><span data-stu-id="c95e8-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="c95e8-157">如果您是從現有的語音解決方案移向 Teams，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="c95e8-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="c95e8-158">本文著重于 Microsoft Teams 的語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="c95e8-159">雖然商務用 Skype Online 解決方案 (如 [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) 電話解決方案) 所述，但必須瞭解商務用 Skype Online 將于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="c95e8-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="c95e8-160">之後，商務用 Skype Online 服務將無法再使用。</span><span class="sxs-lookup"><span data-stu-id="c95e8-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="c95e8-161">此外，將不再支援內部部署環境之間的 PSTN 連線，無論是透過商務用 Skype Server 或雲端連接器版本，還是商務用 &mdash; &mdash; Skype Online。</span><span class="sxs-lookup"><span data-stu-id="c95e8-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="c95e8-162">本文將介紹 Teams 語音解決方案，以及如何在必要時使用直接路由將您的內部部署電話網路連接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="c95e8-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="c95e8-163">電話系統</span><span class="sxs-lookup"><span data-stu-id="c95e8-163">Phone System</span></span>

<span data-ttu-id="c95e8-164">電話系統是 Microsoft 使用 Microsoft Teams 在 Microsoft 365 或 Office 365 雲端中啟用通話控制和私人分支 exchange (PBX) 功能的技術。</span><span class="sxs-lookup"><span data-stu-id="c95e8-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="c95e8-165">電話系統可與 Teams 或商務用 Skype 用戶端及認證裝置一起運作。</span><span class="sxs-lookup"><span data-stu-id="c95e8-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="c95e8-166">電話系統可讓您以一組直接從 Microsoft 365 或 Office 365 提供的功能取代現有的 PBX 系統。</span><span class="sxs-lookup"><span data-stu-id="c95e8-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="c95e8-167">貴組織使用者之間的通話在電話系統內部處理，而且永遠不會在 PSTN (電話) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c95e8-168">這適用于貴組織中位於不同地理區域的使用者之間的通話，這可移除這些內部通話的長途費用。</span><span class="sxs-lookup"><span data-stu-id="c95e8-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="c95e8-169">本文將介紹下列電話系統的重要功能，以及您需要考慮的部署決策：</span><span class="sxs-lookup"><span data-stu-id="c95e8-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="c95e8-170">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="c95e8-171">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="c95e8-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="c95e8-172">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="c95e8-172">Calling identity</span></span>](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

<span data-ttu-id="c95e8-174">有關所有電話系統功能以及如何設定電話系統的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-175">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="c95e8-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- <span data-ttu-id="c95e8-176">[設定貴組織的 [電話系統]](setting-up-your-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="c95e8-176">[Set up Phone System in your organization](setting-up-your-phone-system.md)</span></span><br>
  <span data-ttu-id="c95e8-177">說明如何購買和指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊額度。</span><span class="sxs-lookup"><span data-stu-id="c95e8-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="c95e8-178">有關管理支援裝置的資訊，請參閱在 [Microsoft Teams](devices/device-management.md) 和 Teams Marketplace 中管理 [您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="c95e8-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="c95e8-179">自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="c95e8-180">自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。</span><span class="sxs-lookup"><span data-stu-id="c95e8-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="c95e8-181">通話佇列正在等待來電者的區域。</span><span class="sxs-lookup"><span data-stu-id="c95e8-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="c95e8-182">自動語音回應和通話佇列一起使用，可以輕鬆地將來電者路由至貴組織中適當的人員或部門。</span><span class="sxs-lookup"><span data-stu-id="c95e8-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="c95e8-183">有關自動電話機和通話佇列的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-184">規劃 Teams 自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="c95e8-185">設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="c95e8-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="c95e8-186">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="c95e8-187">Contoso 案例研究：自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="c95e8-188">說明一家虛構的多國公司 Contoso 如何實作自動語音語音和通話佇列，以尋求語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="c95e8-189">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="c95e8-189">Cloud Voicemail</span></span>

<span data-ttu-id="c95e8-190">雲端語音信箱由 Azure 語音信箱服務提供，僅支援語音信箱存款至 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="c95e8-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="c95e8-191">它不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="c95e8-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="c95e8-192">雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="c95e8-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="c95e8-193">您的業務需求可能會要求您針對特定使用者或整個組織的每一個人停用語音信箱翻譯。</span><span class="sxs-lookup"><span data-stu-id="c95e8-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="c95e8-194">僅針對線上使用者，在指派使用者電話系統授權後，系統會自動為使用者設定和設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c95e8-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="c95e8-195">對於擁有 Exchange 信箱的電話系統使用者，您必須執行額外的組組步驟。</span><span class="sxs-lookup"><span data-stu-id="c95e8-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="c95e8-196">有關雲端語音信箱及其組組的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- <span data-ttu-id="c95e8-197">[設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="c95e8-197">[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)</span></span>
- [<span data-ttu-id="c95e8-198">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="c95e8-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="c95e8-199">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="c95e8-199">Calling identity</span></span>

<span data-ttu-id="c95e8-200">根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c95e8-201">來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。</span><span class="sxs-lookup"><span data-stu-id="c95e8-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="c95e8-202">有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱為使用者設定 [本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c95e8-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="c95e8-203">公用交換電話網路連接選項</span><span class="sxs-lookup"><span data-stu-id="c95e8-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="c95e8-204">電話系統為貴組織提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="c95e8-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="c95e8-205">不過，若要讓使用者在組織外撥打電話，您必須將電話系統連接到公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c95e8-206">若要將電話系統連接到 PSTN，您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c95e8-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="c95e8-207">[**電話系統與通話方案**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="c95e8-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="c95e8-208">以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="c95e8-209">[**使用自己的 PSTN 電信**](#phone-system-with-own-pstn-carrier-with-direct-routing) 公司電話系統，使用直接路由將您的內部部署環境連接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="c95e8-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="c95e8-210">您也可以選擇選項群組合，以設計複雜環境的解決方案，或管理多步驟移 (移) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="c95e8-211">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="c95e8-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="c95e8-212">如本文先前所述，電話系統與通話方案是 Microsoft 針對 Teams 使用者的全雲端語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="c95e8-213">這是將 Microsoft Phone System 連接到公用交換電話網絡 (PSTN) 以啟用撥打全球有線電話和行動電話最簡單的選項。</span><span class="sxs-lookup"><span data-stu-id="c95e8-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="c95e8-214">有了這個選項，Microsoft (PBX) 私人分支 Exchange 功能，並做為您的 PSTN 電信公司，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="c95e8-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![圖表 4 顯示具有自動語音機、通話佇列、本機號碼等功能的電話系統，以及 Microsoft 作為 PSTN 電信業者](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="c95e8-216">如果您對下列專案回答是，則電話系統與通話方案是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="c95e8-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="c95e8-217">地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="c95e8-218">您不需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="c95e8-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="c95e8-219">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="c95e8-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="c95e8-220">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="c95e8-220">With this option:</span></span> 

- <span data-ttu-id="c95e8-221">您取得 Microsoft Phone 系統時，新增了國內或國際通話方案， (視全球授權服務等級) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="c95e8-222">由於通話方案在 &mdash; Microsoft 365 或 Office 365 外運作，因此不需要部署或維護內部部署。</span><span class="sxs-lookup"><span data-stu-id="c95e8-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="c95e8-223">注意：如有需要，您可以選擇透過直接路由連接支援的會話邊界控制器 (SBC) ，以與 SBC 支援的協力廠商 PBX、類比裝置和其他協力廠商電話設備進行互通性。</span><span class="sxs-lookup"><span data-stu-id="c95e8-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="c95e8-224">此選項需要不間斷地連接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c95e8-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="c95e8-225">有關通話方案的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-226">哪一個通話方案適合您？</span><span class="sxs-lookup"><span data-stu-id="c95e8-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="c95e8-227">如何購買通話方案</span><span class="sxs-lookup"><span data-stu-id="c95e8-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="c95e8-228">通話方案的適用國家與地區</span><span class="sxs-lookup"><span data-stu-id="c95e8-228">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="c95e8-229">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="c95e8-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="c95e8-230">具有具有直接路由的 PSTN 電信公司的電話系統</span><span class="sxs-lookup"><span data-stu-id="c95e8-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="c95e8-231">此選項使用直接路由將 Microsoft Phone System 連接到您的電話網絡，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="c95e8-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![圖表 5 顯示具有直接路由的電話系統](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="c95e8-233">如果您對下列問題回答是，則使用直接路由的電話系統是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="c95e8-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="c95e8-234">您想要使用 Teams 與電話系統。</span><span class="sxs-lookup"><span data-stu-id="c95e8-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="c95e8-235">您需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="c95e8-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="c95e8-236">您想要混合路由，有些通話會透過通話方案進行，有些則透過您的電信公司進行。</span><span class="sxs-lookup"><span data-stu-id="c95e8-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="c95e8-237">您需要與協力廠商 PBX 和/或設備進行交互操作，例如架空傳呼機、類比裝置等。</span><span class="sxs-lookup"><span data-stu-id="c95e8-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="c95e8-238">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="c95e8-238">With this option:</span></span>

- <span data-ttu-id="c95e8-239">您將自己支援的 SBC 連接到 Microsoft Phone System，而不需要其他內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="c95e8-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="c95e8-240">您幾乎可以在 Microsoft Phone System 中使用幾乎任何電話電信業者。</span><span class="sxs-lookup"><span data-stu-id="c95e8-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="c95e8-241">您可以選擇設定及管理這個選項，也可以由您的電信公司或合作夥伴設定及管理 (詢問您的電信公司或合作夥伴是否提供此選項) 。</span><span class="sxs-lookup"><span data-stu-id="c95e8-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="c95e8-242">您可以設定電話設備之間的互通性，例如協力廠商 PBX 和類比裝置與 &mdash; Microsoft &mdash; Phone System。</span><span class="sxs-lookup"><span data-stu-id="c95e8-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="c95e8-243">此選項需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="c95e8-243">This option requires the following:</span></span>

- <span data-ttu-id="c95e8-244">不間斷地連接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c95e8-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="c95e8-245">部署及維護支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="c95e8-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="c95e8-246">與協力廠商電信公司簽訂合約。</span><span class="sxs-lookup"><span data-stu-id="c95e8-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="c95e8-247"> (除非已部署為選項，為使用通話方案的電話系統使用者提供協力廠商 PBX、類比裝置或其他電話設備) </span><span class="sxs-lookup"><span data-stu-id="c95e8-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="c95e8-248">有關直接路由的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-249">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="c95e8-250">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="c95e8-251">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="c95e8-252">管理語音路由策略，以用於直接路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="c95e8-253">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c95e8-254">通過直接路由認證的工作階段邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="c95e8-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="c95e8-255">Microsoft 的電話號碼</span><span class="sxs-lookup"><span data-stu-id="c95e8-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="c95e8-256">Microsoft 有兩種可用的電話號碼：訂閱者 *(* 使用者) 號碼，可指派給貴組織的使用者;以及服務號碼，以付費和免付費服務號碼提供。</span><span class="sxs-lookup"><span data-stu-id="c95e8-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="c95e8-257">服務號碼的並行通話容量高於訂閱者號碼，並可以指派給音訊會議、自動語音服務或通話佇列等服務。</span><span class="sxs-lookup"><span data-stu-id="c95e8-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="c95e8-258">您必須決定：</span><span class="sxs-lookup"><span data-stu-id="c95e8-258">You will need to decide:</span></span>

- <span data-ttu-id="c95e8-259">哪些使用者位置需要 Microsoft 的新電話號碼？</span><span class="sxs-lookup"><span data-stu-id="c95e8-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="c95e8-260">我需要哪一 (或服務) 電話號碼？</span><span class="sxs-lookup"><span data-stu-id="c95e8-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="c95e8-261">如何將現有的電話號碼移植到 Teams？</span><span class="sxs-lookup"><span data-stu-id="c95e8-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="c95e8-262">有關管理貴組織電話號碼 ，包括取得新號碼或移轉離職號碼等詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-263">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="c95e8-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="c95e8-264">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="c95e8-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="c95e8-265">為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="c95e8-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="c95e8-266">將電話號碼轉接至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c95e8-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="c95e8-267">撥號方案與通話路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-267">Dial plans and call routing</span></span>

<span data-ttu-id="c95e8-268">撥號方案是一組將撥號電話號碼轉換成替代格式的標準化規則 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c95e8-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="c95e8-269">您必須決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="c95e8-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="c95e8-270">我的組織需要自訂的撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="c95e8-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="c95e8-271">哪些使用者需要自訂撥號方案？</span><span class="sxs-lookup"><span data-stu-id="c95e8-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="c95e8-272">應該為每個使用者指派哪一個租使用者撥號方案？</span><span class="sxs-lookup"><span data-stu-id="c95e8-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="c95e8-273">詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="c95e8-274">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="c95e8-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="c95e8-275">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="c95e8-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="c95e8-276">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="c95e8-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="c95e8-277">緊急電話</span><span class="sxs-lookup"><span data-stu-id="c95e8-277">Emergency calling</span></span>

<span data-ttu-id="c95e8-278">您設定緊急電話方式會根據您的 PSTN 連接選項而不同：Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="c95e8-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="c95e8-279">Microsoft 通話方案與電話系統直接路由的動態緊急電話提供設定及路由緊急電話的能力，並依據 Teams 用戶端的目前位置通知安全人員。</span><span class="sxs-lookup"><span data-stu-id="c95e8-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="c95e8-280">若要進一步瞭解緊急電話概念和術語，以及如何設定動態緊急電話，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-281">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="c95e8-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="c95e8-282">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="c95e8-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="c95e8-283">Contoso 案例研究：緊急電話</span><span class="sxs-lookup"><span data-stu-id="c95e8-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="c95e8-284">說明一家虛構的多國公司 Contoso 如何為組織實作緊急電話。</span><span class="sxs-lookup"><span data-stu-id="c95e8-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="c95e8-285">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="c95e8-286">在一些國家和地區，若要降低長途電話費用， (PSTN) 通電話網絡不合法。</span><span class="sxs-lookup"><span data-stu-id="c95e8-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="c95e8-287">Location-Based直接路由路由可讓您根據 Microsoft Teams 使用者的地理位置限制免付費路。</span><span class="sxs-lookup"><span data-stu-id="c95e8-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="c95e8-288">若要進一步瞭解如何規劃及設定 LBR Location-Based路由 (，請參閱) 文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="c95e8-289">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="c95e8-290">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="c95e8-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="c95e8-291">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="c95e8-292">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="c95e8-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="c95e8-293">說明一家虛構的多國公司 Contoso 如何為Location-Based路由實作。</span><span class="sxs-lookup"><span data-stu-id="c95e8-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="c95e8-294">語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="c95e8-294">Network topology for voice features</span></span>

<span data-ttu-id="c95e8-295">如果您要部署動態緊急電話或直接路由Location-Based路由，您必須設定網路設定，以在 Microsoft Teams 中與這些功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="c95e8-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="c95e8-296">若要瞭解如何設定網路區域、網路網站、網路子網和受信任的 IP 位址的網路設定，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="c95e8-297">Microsoft Teams 中雲端語音功能的網路設定 - 概念和術語</span><span class="sxs-lookup"><span data-stu-id="c95e8-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="c95e8-298">在 Microsoft Teams 中管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="c95e8-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="c95e8-299">將現有的語音解決方案遷移到 Teams</span><span class="sxs-lookup"><span data-stu-id="c95e8-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="c95e8-300">對於升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="c95e8-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="c95e8-301">只有在使用者進入 TeamsOnly 模式時，才支援在 Teams 中使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="c95e8-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="c95e8-302">如果您需要升級至 Teams 的基本資訊，請從這裡開始：</span><span class="sxs-lookup"><span data-stu-id="c95e8-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="c95e8-303">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c95e8-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="c95e8-304">關於升級架構</span><span class="sxs-lookup"><span data-stu-id="c95e8-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="c95e8-305">IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="c95e8-305">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="c95e8-306">移移語音解決方案時，移至 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="c95e8-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="c95e8-307">[**商務用 Skype Online 中的使用者，具有 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="c95e8-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="c95e8-308">升級後，該使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="c95e8-309">**[商務用 Skype Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。</span><span class="sxs-lookup"><span data-stu-id="c95e8-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="c95e8-310">使用者升級至 Teams 時，必須協調使用者的移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="c95e8-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="c95e8-311">**[商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="c95e8-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="c95e8-312">將此使用者移轉至 Teams，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。</span><span class="sxs-lookup"><span data-stu-id="c95e8-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="c95e8-313">**[在商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 內部部署中使用企業語音的使用者，該使用者將會移往線上，並且使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="c95e8-314">將該使用者移轉至 Teams 時，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並配合 A) 將該使用者電話號碼的埠移至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="c95e8-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="c95e8-315">若要進一步瞭解如何針對這些案例執行語音移移，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移向直接路由的資訊，請參閱 &mdash; &mdash; 下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="c95e8-316">升級至 Teams 時 ，適用于 IT 系統管理員的 PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="c95e8-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="c95e8-317">Contoso 語音移移案例研究</span><span class="sxs-lookup"><span data-stu-id="c95e8-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="c95e8-318">案例研究說明虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c95e8-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="c95e8-319">它包含下列文章：</span><span class="sxs-lookup"><span data-stu-id="c95e8-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="c95e8-320">Teams 升級計畫</span><span class="sxs-lookup"><span data-stu-id="c95e8-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="c95e8-321">電話系統與 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="c95e8-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="c95e8-322">位置式路由實現</span><span class="sxs-lookup"><span data-stu-id="c95e8-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="c95e8-323">緊急電話</span><span class="sxs-lookup"><span data-stu-id="c95e8-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="c95e8-324">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="c95e8-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="c95e8-325">音訊會議</span><span class="sxs-lookup"><span data-stu-id="c95e8-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)