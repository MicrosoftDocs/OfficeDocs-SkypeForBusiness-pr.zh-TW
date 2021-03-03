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
ms.openlocfilehash: fcd7ebfd4542c38bd56900c1e414dadec09bf246
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408189"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="a2ab2-103">規劃您的 Teams 語音解決方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="a2ab2-104">本文可協助貴組織決定適合哪一種 Microsoft 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="a2ab2-105">在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="a2ab2-106">有關規劃 Teams 語音解決方案做為整體規劃的一部分，以從商務用 Skype Server 升級到 Teams，請參閱從商務用 Skype 內部部署升級到 Teams 的 [PSTN 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="a2ab2-107">您可能會想要使用電話系統 &mdash; 與通話方案最簡單的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="a2ab2-108">這是 Microsoft 的全雲端解決方案，提供私人交換器 (PBX) 功能，並撥打到公用交換電話網路 (PSTN) ，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="a2ab2-109">有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![圖表 1 顯示電話系統與通話方案](media/voice-solutions-simple.png)

<span data-ttu-id="a2ab2-111">如果您回答下列是，則電話系統與通話方案是適合您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="a2ab2-112">通話方案可在您的地區使用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="a2ab2-113">您目前不需要保留 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="a2ab2-114">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="a2ab2-115">不過，您的情況可能較為複雜。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-115">However, your situation might be more complex.</span></span> <span data-ttu-id="a2ab2-116">例如，您可能在通話方案無法提供的位置設立辦公室。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="a2ab2-117">或者，您可能需要支援複雜且跨國家/地區部署的組合解決方案，且不同的地理位置有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="a2ab2-118">Microsoft 支援解決方案組合：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="a2ab2-119">電話系統與通話方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="a2ab2-120">具有您 PSTN 電信公司的電話系統與直接路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="a2ab2-121">同時使用電話系統與通話方案及電話系統搭配直接路由的組合解決方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="a2ab2-122">您需要閱讀哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-122">What do you need to read?</span></span>

<span data-ttu-id="a2ab2-123">**這是全部的必填專案。**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-123">**Required for all.**</span></span> <span data-ttu-id="a2ab2-124">本文中的部分章節適用于所有組織。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="a2ab2-125">例如，每個人都應該閱讀電話系統，並瞭解連接至 PSTN 網內公用交換電話 (的選項) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="a2ab2-126">所有專案都為必填專案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-126">Required for all</span></span> | <span data-ttu-id="a2ab2-127">說明</span><span class="sxs-lookup"><span data-stu-id="a2ab2-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="a2ab2-128">**電話系統**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="a2ab2-129">Microsoft 在 Microsoft 365 雲端與 Microsoft Teams 中啟用呼叫控制和私人分支 Exchange (PBX) 功能的技術。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="a2ab2-130">**公用交換電話網路 (PSTN) 選項**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="a2ab2-131">選擇使用 Microsoft 作為電話電信業者，或是使用直接路由將您自己的電話電信業者連接至 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="a2ab2-132">PSTN 連接選項與電話系統結合，可讓使用者撥打全球電話。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="a2ab2-133">**視您的需求而不同。**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-133">**Depending on your requirements.**</span></span> <span data-ttu-id="a2ab2-134">本文中的部分章節會根據您現有的部署和需求而相關。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="a2ab2-135">例如，Location-Based只針對不允許付費旁路的地理位置中的直接路由客戶，才需要路由。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="a2ab2-136">請考慮您可能需要的這些額外組配置：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-136">Consider which of these additional configurations you might need:</span></span>

![圖表 2 顯示其他語音元件，例如來自 Microsoft 的電話號碼、撥號方案及通話路由等等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="a2ab2-138">視您的需求</span><span class="sxs-lookup"><span data-stu-id="a2ab2-138">Depending on your requirements</span></span> | <span data-ttu-id="a2ab2-139">說明</span><span class="sxs-lookup"><span data-stu-id="a2ab2-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="a2ab2-140">**Microsoft 的電話號碼**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="a2ab2-141">如何取得及管理 Microsoft 的電話號碼，以及如何將現有的號碼移轉至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="a2ab2-142">如果您需要取得 Microsoft 通話方案的電話號碼、轉接現有號碼、取得服務號碼等等，請閱讀此內容。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="a2ab2-143">**撥號方案與通話路由**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="a2ab2-144">如何設定及管理將撥號電話號碼轉換成替代格式的撥號 (通常是 E.164) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="a2ab2-145">如果您需要瞭解什麼是撥號表，以及是否需要為組織指定撥號方案，請閱讀此說明。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="a2ab2-146">**緊急電話**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="a2ab2-147">如何根據您的 PSTN 連接選項 &mdash; 管理及設定緊急電話。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="a2ab2-148">如果您使用的是 Microsoft 通話方案或直接路由，且需要瞭解如何管理組織的緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="a2ab2-149">**直接路由的以位置為基礎的路由**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="a2ab2-150">如何使用 Location-Based LBR (路由) 依據 Microsoft Teams 使用者的地理位置來限制付費旁路。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="a2ab2-151">如果貴組織在不允許付費旁路的位置使用直接路由，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="a2ab2-152">**雲端語音功能的網路拓撲**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="a2ab2-153">如果貴組織針對直接路由Location-Based LBR (LBR) 部署路由或動態緊急電話，您必須設定網路設定，以與 Microsoft Teams 中的這些功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="a2ab2-154">如果您正針對直接路由實施 LBR，或者要使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="a2ab2-155">**遷移您現有的語音解決方案**</span><span class="sxs-lookup"><span data-stu-id="a2ab2-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="a2ab2-156">將語音解決方案移移至 Teams 時，您需要考慮的是什麼。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="a2ab2-157">如果您是從現有的語音解決方案移向 Teams，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="a2ab2-158">本文著重在 Microsoft Teams 的語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="a2ab2-159">雖然商務用 Skype Online 解決方案仍然 (如 [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 電話解決方案) 所述，但必須瞭解商務用 Skype Online 將于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="a2ab2-160">在此日期之後，商務用 Skype Online 服務將無法再使用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="a2ab2-161">此外，將不再支援透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online 在內部部署環境之間的 &mdash; &mdash; PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="a2ab2-162">本文將介紹 Teams 語音解決方案，以及您在必要時如何使用直接路由將內部部署電話網路連接至 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="a2ab2-163">電話系統</span><span class="sxs-lookup"><span data-stu-id="a2ab2-163">Phone System</span></span>

<span data-ttu-id="a2ab2-164">電話系統是 Microsoft 在 Microsoft 365 或 Office 365 雲端與 Microsoft Teams 中啟用呼叫控制和私人分支 Exchange (PBX) 功能的技術。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="a2ab2-165">電話系統可與 Teams 或商務用 Skype 用戶端和通過認證的裝置一起運作。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="a2ab2-166">電話系統可讓您以一組直接從 Microsoft 365 或 Office 365 提供的功能取代現有的 PBX 系統。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="a2ab2-167">您組織使用者之間的通話會于電話系統內部處理，而且永遠不會進入 PSTN (公用交換電話網路) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a2ab2-168">這適用于貴組織中位於不同地理區域的使用者之間的通話，免去這些內部通話的長途電話費用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="a2ab2-169">本文將介紹下列電話系統的重要功能，以及您需要考慮的部署決策：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="a2ab2-170">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="a2ab2-171">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a2ab2-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="a2ab2-172">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="a2ab2-172">Calling identity</span></span>](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

<span data-ttu-id="a2ab2-174">有關所有電話系統功能以及如何設定電話系統的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-175">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="a2ab2-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="a2ab2-176">在組織中設定電話系統</span><span class="sxs-lookup"><span data-stu-id="a2ab2-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="a2ab2-177">說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="a2ab2-178">有關管理支援裝置的資訊，請參閱在 [Microsoft Teams](devices/device-management.md) 和 Teams Marketplace 中管理 [您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="a2ab2-179">自動 Attendant 和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="a2ab2-180">自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="a2ab2-181">通話佇列正在等候來電者的區域。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="a2ab2-182">自動語音機和通話佇列可以一起使用，輕鬆地將來電者路由給貴組織的適當人員或部門。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="a2ab2-183">有關自動 Attendant 和通話佇列的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-184">規劃 Teams 自動 Attendant 和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="a2ab2-185">設定自動 attendant</span><span class="sxs-lookup"><span data-stu-id="a2ab2-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="a2ab2-186">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="a2ab2-187">Contoso 案例研究：自動 Attendant 和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="a2ab2-188">說明虛構的多國公司 Contoso 如何針對語音解決方案實作自動語音留言和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="a2ab2-189">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a2ab2-189">Cloud Voicemail</span></span>

<span data-ttu-id="a2ab2-190">由 Azure 語音信箱服務所提供之雲端語音信箱僅支援 Exchange 信箱的語音信箱存款。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="a2ab2-191">不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="a2ab2-192">雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="a2ab2-193">您的業務需求可能會要求您停用特定使用者或整個組織所有人的語音信箱抄寫功能。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="a2ab2-194">只有線上使用者，系統會自動為使用者設定並設定雲端語音信箱，並為其指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="a2ab2-195">對於擁有 Exchange 信箱的電話系統使用者，您必須執行額外的組組步驟。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="a2ab2-196">有關雲端語音信箱及其組配置的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-197">設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a2ab2-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="a2ab2-198">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="a2ab2-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="a2ab2-199">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="a2ab2-199">Calling identity</span></span>

<span data-ttu-id="a2ab2-200">根據預設，所有外發電話會使用指派的電話號碼作為本機號碼 (本機號碼) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="a2ab2-201">來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="a2ab2-202">有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱設定 [使用者的本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="a2ab2-203">公用交換電話網路連接選項</span><span class="sxs-lookup"><span data-stu-id="a2ab2-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="a2ab2-204">電話系統可為您的組織提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="a2ab2-205">不過，若要讓使用者在組織外撥打電話，您必須將電話系統連接到 PSTN (公用交換電話網路) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a2ab2-206">若要將電話系統連接到 PSTN，您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="a2ab2-207">[**電話系統與通話方案**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="a2ab2-208">以 Microsoft 作為 PSTN 電信公司的全雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="a2ab2-209">[**使用直接路由將您的**](#phone-system-with-own-pstn-carrier-with-direct-routing) 內部部署環境連接到 Teams，使用您自己的 PSTN 電信電信公司使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="a2ab2-210">您也可以選擇選項群組合，這可讓您為複雜的環境設計解決方案，或管理多步驟移 (日後移) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="a2ab2-211">電話系統與通話方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="a2ab2-212">如本文稍早所述，電話系統與通話方案是 Microsoft 針對 Teams 使用者的雲端語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="a2ab2-213">這是將 Microsoft Phone System 連接到公用交換電話網路 (PSTN) 以撥打全球有線電話和行動電話的最簡單選項。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="a2ab2-214">Microsoft 使用此選項為貴組織 (專用 Exchange) PBX 功能，並做為 PSTN 電信者，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![圖表 4 顯示電話系統與自動語音機、通話佇列、本機號碼等，以及 Microsoft 作為 PSTN 電信業者](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="a2ab2-216">如果您回答下列是，則電話系統與通話方案是適合您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="a2ab2-217">通話方案可在您的地區使用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="a2ab2-218">您目前不需要保留 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="a2ab2-219">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="a2ab2-220">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-220">With this option:</span></span> 

- <span data-ttu-id="a2ab2-221">您可以取得新增的國內或國際通話方案來取得 Microsoft Phone System，以便根據授權服務等級 (撥打到世界各地的電話) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="a2ab2-222">您不需要部署或維護內部部署，因為通話方案是使用 &mdash; Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="a2ab2-223">注意：如有需要，您可以選擇透過直接路由連接支援的會話邊界控制器 (SBC) ，以與 SBC 支援的協力廠商 PBX、類比裝置及其他協力廠商電話設備進行互通性。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="a2ab2-224">此選項需要不間斷地連接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="a2ab2-225">有關通話方案詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-226">哪一個通話方案適合您？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="a2ab2-227">如何購買通話方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="a2ab2-228">通話方案的適用國家與地區</span><span class="sxs-lookup"><span data-stu-id="a2ab2-228">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="a2ab2-229">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="a2ab2-230">具有具有直接路由之 PSTN 電信公司的電話系統</span><span class="sxs-lookup"><span data-stu-id="a2ab2-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="a2ab2-231">此選項使用直接路由將 Microsoft Phone System 連接到電話網絡，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![圖表 5 顯示具有直接路由的電話系統](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="a2ab2-233">如果您對下列問題回答是，則具有直接路由的電話系統是適合您的解決方案：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="a2ab2-234">您想要使用 Teams 與電話系統。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="a2ab2-235">您必須保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="a2ab2-236">您想要混合路由，有些通話會透過通話方案進行，有些則透過您的電信公司進行。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="a2ab2-237">您需要與協力廠商 PBX 和/或設備交互操作，例如我們架空的分頁機、類比裝置等。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="a2ab2-238">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-238">With this option:</span></span>

- <span data-ttu-id="a2ab2-239">您將自己支援的 SBC 連接到 Microsoft Phone System，而不需要其他內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="a2ab2-240">您可以使用幾乎任何電話電信業者與 Microsoft Phone System。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="a2ab2-241">您可以選擇設定及管理此選項，也可以由您的電信公司或合作夥伴設定及管理 (詢問您的電信公司或合作夥伴是否提供此選項) 。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="a2ab2-242">您可以設定電話設備之間的互通性，例如協力廠商 PBX 和類比裝置以及 &mdash; Microsoft &mdash; Phone System。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="a2ab2-243">此選項需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-243">This option requires the following:</span></span>

- <span data-ttu-id="a2ab2-244">不中斷與 Microsoft 365 或 Office 365 的連接。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="a2ab2-245">部署和維護支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="a2ab2-246">協力廠商電信公司之合約。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="a2ab2-247"> (除非已部署為選項，可為使用通話方案的電話系統使用者提供協力廠商 PBX、類比裝置或其他電話設備) </span><span class="sxs-lookup"><span data-stu-id="a2ab2-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="a2ab2-248">有關直接路由詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-249">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="a2ab2-250">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="a2ab2-251">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="a2ab2-252">管理語音路由策略以用於直接路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="a2ab2-253">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="a2ab2-254">通過直接路由認證的工作階段邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="a2ab2-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="a2ab2-255">Microsoft 的電話號碼</span><span class="sxs-lookup"><span data-stu-id="a2ab2-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="a2ab2-256">Microsoft 提供兩種電話號碼 *類型：訂閱* 者 (使用者) 號碼，可指派給貴組織的使用者;以及服務號碼，以付費和免付費服務號碼提供。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="a2ab2-257">服務號碼的並行通話容量高於訂閱者號碼，而且可以指派給音訊會議、自動語音服務或通話佇列等服務。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="a2ab2-258">您必須決定：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-258">You will need to decide:</span></span>

- <span data-ttu-id="a2ab2-259">哪些使用者位置需要 Microsoft 的新電話號碼？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="a2ab2-260">我需要哪一 (或服務) 電話號碼？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="a2ab2-261">如何將現有的電話號碼埠至 Teams？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="a2ab2-262">有關管理貴組織電話號碼 ，包括取得新號碼或移轉離開號碼等詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-263">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="a2ab2-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="a2ab2-264">用於通話方案的電話號碼類型</span><span class="sxs-lookup"><span data-stu-id="a2ab2-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="a2ab2-265">為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="a2ab2-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="a2ab2-266">將電話號碼移轉至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2ab2-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="a2ab2-267">撥號方案與通話路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-267">Dial plans and call routing</span></span>

<span data-ttu-id="a2ab2-268">撥號表是一組標準化規則，將撥入的電話號碼轉換成替代格式 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="a2ab2-269">您必須決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="a2ab2-270">我的組織需要自訂的撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="a2ab2-271">哪些使用者需要自訂撥號表？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="a2ab2-272">應該將哪個租使用者撥號方案指派給每個使用者？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="a2ab2-273">詳細資訊請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="a2ab2-274">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="a2ab2-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="a2ab2-275">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="a2ab2-276">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a2ab2-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="a2ab2-277">緊急電話</span><span class="sxs-lookup"><span data-stu-id="a2ab2-277">Emergency calling</span></span>

<span data-ttu-id="a2ab2-278">您設定緊急電話方式會根據您的 PSTN 連接選項而不同：Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="a2ab2-279">Microsoft 通話計畫和電話系統直接路由的動態緊急電話功能，可設定及路由緊急電話，並依據 Teams 用戶端的目前位置通知安全性人員。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="a2ab2-280">有關緊急電話概念和術語以及如何設定動態緊急電話的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-281">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="a2ab2-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a2ab2-282">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="a2ab2-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="a2ab2-283">Contoso 案例研究：緊急電話</span><span class="sxs-lookup"><span data-stu-id="a2ab2-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="a2ab2-284">說明虛構的多國公司 Contoso 如何為組織實作緊急電話。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="a2ab2-285">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="a2ab2-286">在某些國家和地區，忽略公用交換電話網路 (PSTN) 降低長途電話費用是不合法的。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="a2ab2-287">Location-Based直接路由路由可讓您根據 Microsoft Teams 使用者的地理位置限制付費旁路。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="a2ab2-288">若要進一步瞭解如何規劃及設定 Location-Based LBR (路由) ，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-289">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="a2ab2-290">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="a2ab2-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="a2ab2-291">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="a2ab2-292">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="a2ab2-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="a2ab2-293">說明虛構的多國公司 Contoso 如何為Location-Based路由實作。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="a2ab2-294">語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="a2ab2-294">Network topology for voice features</span></span>

<span data-ttu-id="a2ab2-295">如果您要部署動態緊急電話或直接路由Location-Based路由，您必須設定網路設定，以與 Microsoft Teams 中的這些功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="a2ab2-296">若要瞭解如何設定網路區域、網路網站、網路子網和信任的 IP 位址的網路設定，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-297">Microsoft Teams 中雲端語音功能的網路設定 - 概念和術語</span><span class="sxs-lookup"><span data-stu-id="a2ab2-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="a2ab2-298">在 Microsoft Teams 中管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="a2ab2-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="a2ab2-299">將您現有的語音解決方案遷移到 Teams</span><span class="sxs-lookup"><span data-stu-id="a2ab2-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="a2ab2-300">針對升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="a2ab2-301">只有在使用者使用 TeamsOnly 模式時，才支援在 Teams 使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="a2ab2-302">如果您需要升級至 Teams 的基本資訊，請從這裡開始：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="a2ab2-303">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2ab2-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="a2ab2-304">關於升級架構</span><span class="sxs-lookup"><span data-stu-id="a2ab2-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="a2ab2-305">適用于 IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="a2ab2-305">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="a2ab2-306">移移語音解決方案時，在移往 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="a2ab2-307">[**商務用 Skype Online 中的使用者，具有 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="a2ab2-308">升級後，此使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="a2ab2-309">**[商務用 Skype Online 的使用者，透過](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="a2ab2-310">使用者升級至 Teams 時，必須協調使用者移至直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="a2ab2-311">**[商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="a2ab2-312">將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由的移轉。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="a2ab2-313">**[商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 內部部署與企業語音的使用者，將會移往線上，並且使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="a2ab2-314">將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並且使用 A) 將該使用者電話號碼的埠移轉至 Microsoft 通話方案，或 B) 從可用地區指派新的訂閱者號碼來協調移動。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="a2ab2-315">請參閱下列文章，以進一步瞭解如何針對這些案例實施語音移入，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移移至 &mdash; 直接路由的資訊 &mdash; ：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="a2ab2-316">升級至 Teams 時對 IT 系統管理員的 PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="a2ab2-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="a2ab2-317">Contoso 語音移移案例研究</span><span class="sxs-lookup"><span data-stu-id="a2ab2-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="a2ab2-318">案例研究說明虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2ab2-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="a2ab2-319">它包含下列文章：</span><span class="sxs-lookup"><span data-stu-id="a2ab2-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="a2ab2-320">Teams 升級方案</span><span class="sxs-lookup"><span data-stu-id="a2ab2-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="a2ab2-321">電話系統與 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="a2ab2-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="a2ab2-322">位置式路由的實現</span><span class="sxs-lookup"><span data-stu-id="a2ab2-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="a2ab2-323">緊急電話</span><span class="sxs-lookup"><span data-stu-id="a2ab2-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="a2ab2-324">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a2ab2-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="a2ab2-325">音訊會議</span><span class="sxs-lookup"><span data-stu-id="a2ab2-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












