---
title: 在 Microsoft Teams
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
description: 深入瞭解雲端Microsoft Teams功能，以及您將為貴組織做出部署決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92b28a00e1737b533c17cf3f1f670bc23561620d
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689791"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="1911d-103">規劃您的Teams語音解決方案</span><span class="sxs-lookup"><span data-stu-id="1911d-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="1911d-104">本文可協助您決定適合貴組織的 Microsoft 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="1911d-105">在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="1911d-106">有關規劃 Teams 語音解決方案做為從 商務用 Skype Server 升級至 Teams 的整體計畫之一的指引，請參閱從 商務用 Skype 內部部署升級到 Teams 的[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)考慮。</span><span class="sxs-lookup"><span data-stu-id="1911d-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="1911d-107">您可能會想要使用通話方案 &mdash; 電話系統最簡單的解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="1911d-108">這是 Microsoft 的全雲端解決方案，提供私人分支 Exchange (PBX) 功能，並撥打到公用交換電話網路 (PSTN) ，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="1911d-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="1911d-109">有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="1911d-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![圖表 1 顯示電話系統通話方案](media/voice-solutions-simple.png)

<span data-ttu-id="1911d-111">如果您對下列專案回答是，電話系統通話方案是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="1911d-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="1911d-112">地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="1911d-113">您不需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="1911d-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="1911d-114">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="1911d-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="1911d-115">不過，您的情況可能較為複雜。</span><span class="sxs-lookup"><span data-stu-id="1911d-115">However, your situation might be more complex.</span></span> <span data-ttu-id="1911d-116">例如，您可能有辦公室位於沒有通話方案的位置。</span><span class="sxs-lookup"><span data-stu-id="1911d-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="1911d-117">或者，您可能需要支援複雜、多國部署的組合解決方案，且不同的地理位置有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="1911d-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="1911d-118">Microsoft 支援一組解決方案：</span><span class="sxs-lookup"><span data-stu-id="1911d-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="1911d-119">電話系統通話方案</span><span class="sxs-lookup"><span data-stu-id="1911d-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="1911d-120">電話系統具有運算子的 PSTN 電信連線 (目前僅適用于公用 **預覽版)**</span><span class="sxs-lookup"><span data-stu-id="1911d-120">Phone System with your own PSTN carrier with Operator Connect (currently available only in **public preview**)</span></span>
- <span data-ttu-id="1911d-121">電話系統直接路由使用您自己的 PSTN 電信公司</span><span class="sxs-lookup"><span data-stu-id="1911d-121">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="1911d-122">搭配通話方案使用電話系統組合解決方案電話系統運算子連線，以及/或電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="1911d-122">A combination solution that uses Phone System with Calling Plan, Phone System with Operator Connect, and/or Phone System with Direct Routing</span></span>


## <a name="what-do-you-need-to-read"></a><span data-ttu-id="1911d-123">您需要閱讀哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="1911d-123">What do you need to read?</span></span>

<span data-ttu-id="1911d-124">**全部為必填專案。**</span><span class="sxs-lookup"><span data-stu-id="1911d-124">**Required for all.**</span></span> <span data-ttu-id="1911d-125">本文中的部分章節與所有組織有關。</span><span class="sxs-lookup"><span data-stu-id="1911d-125">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="1911d-126">例如，每個人都應該閱讀電話系統並瞭解在 PSTN 中連接至公用交換電話網絡 (選項) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-126">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="1911d-127">全部為必填專案</span><span class="sxs-lookup"><span data-stu-id="1911d-127">Required for all</span></span> | <span data-ttu-id="1911d-128">說明</span><span class="sxs-lookup"><span data-stu-id="1911d-128">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="1911d-129">**電話系統**</span><span class="sxs-lookup"><span data-stu-id="1911d-129">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="1911d-130">Microsoft 的技術可啟用通話控制和私人分支Exchange (PBX) 雲端Microsoft 365功能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-130">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="1911d-131">**公用交換電話網絡 (PSTN) 連接選項**</span><span class="sxs-lookup"><span data-stu-id="1911d-131">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="1911d-132">使用 Microsoft 做為電話電信業者，或使用直接路由或電信業者Microsoft Teams電話電信業者連線。</span><span class="sxs-lookup"><span data-stu-id="1911d-132">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing or Operator Connect.</span></span> <span data-ttu-id="1911d-133">PSTN 電話系統結合，可讓使用者撥打全球電話。</span><span class="sxs-lookup"><span data-stu-id="1911d-133">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="1911d-134">**視您的需求而不同。**</span><span class="sxs-lookup"><span data-stu-id="1911d-134">**Depending on your requirements.**</span></span> <span data-ttu-id="1911d-135">本文中的部分章節會根據您的現有部署和需求而相關。</span><span class="sxs-lookup"><span data-stu-id="1911d-135">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="1911d-136">例如，Location-Based不允許免付費路的地理位置中的直接路由客戶，才需要直接路由。</span><span class="sxs-lookup"><span data-stu-id="1911d-136">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="1911d-137">請考慮您可能需要的這些額外配置：</span><span class="sxs-lookup"><span data-stu-id="1911d-137">Consider which of these additional configurations you might need:</span></span>

![圖表 2 顯示其他語音元件，例如電話的號碼、撥號方案及通話路由等等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="1911d-139">根據您的需求</span><span class="sxs-lookup"><span data-stu-id="1911d-139">Depending on your requirements</span></span> | <span data-ttu-id="1911d-140">說明</span><span class="sxs-lookup"><span data-stu-id="1911d-140">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="1911d-141">**電話 Microsoft 的號碼**</span><span class="sxs-lookup"><span data-stu-id="1911d-141">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="1911d-142">如何取得和管理 Microsoft 的電話號碼，以及如何將現有號碼移轉至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="1911d-142">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="1911d-143">如果您需要取得 Microsoft 通話方案的電話號碼、轉接現有號碼、取得服務號碼等，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="1911d-143">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="1911d-144">**撥號方案與通話路由**</span><span class="sxs-lookup"><span data-stu-id="1911d-144">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="1911d-145">如何設定及管理撥號方案，將撥號電話號碼轉換成替代格式 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1911d-145">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="1911d-146">如果您需要瞭解什麼是撥號方案，以及您是否需要為貴組織指定撥號方案，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="1911d-146">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="1911d-147">**緊急電話**</span><span class="sxs-lookup"><span data-stu-id="1911d-147">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="1911d-148">如何管理及設定緊急電話 &mdash; ，取決於您的 PSTN 連接選項。</span><span class="sxs-lookup"><span data-stu-id="1911d-148">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="1911d-149">如果您使用的是 Microsoft 通話方案或直接路由，並需要瞭解如何管理組織的緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="1911d-149">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="1911d-150">**直接路由的基於位置的路由**</span><span class="sxs-lookup"><span data-stu-id="1911d-150">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="1911d-151">如何使用 LBR Location-Based路由 (，) 使用者根據地理位置Microsoft Teams免付費路。</span><span class="sxs-lookup"><span data-stu-id="1911d-151">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="1911d-152">如果貴組織在不允許免付費路的位置使用直接路由，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="1911d-152">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="1911d-153">**雲端語音功能的網路拓撲**</span><span class="sxs-lookup"><span data-stu-id="1911d-153">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="1911d-154">如果貴組織正在部署 Location-Based路由 (LBR) 直接路由或動態緊急電話，您必須設定網路設定，以在 Microsoft Teams 中與這些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-154">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="1911d-155">如果您正針對直接路由執行 LBR，或是使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="1911d-155">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="1911d-156">**遷移現有的語音解決方案**</span><span class="sxs-lookup"><span data-stu-id="1911d-156">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="1911d-157">當您將語音解決方案移向 Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-157">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="1911d-158">如果您要從現有的語音解決方案移向新的語音解決方案，請閱讀Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-158">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="1911d-159">本文著重于語音解決方案與Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-159">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="1911d-160">雖然 microsoft 商務用 Skype 解決方案) 所述 (仍提供[商務用 Skype](/SkypeForBusiness/hybrid/msft-telephony-solutions) Online 解決方案，但必須瞭解 商務用 Skype Online 將于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="1911d-160">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="1911d-161">在此日期之後，商務用 Skype線上服務將無法再使用。</span><span class="sxs-lookup"><span data-stu-id="1911d-161">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="1911d-162">此外，不再支援內部部署環境之間的 PSTN 連線商務用 Skype Server雲端連接器版本和 商務用 Skype Online 之間的 &mdash; &mdash; PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="1911d-162">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="1911d-163">本文將介紹Teams語音解決方案，以及如何在必要時使用直接路由或運算子Teams內部部署電話網絡連線。</span><span class="sxs-lookup"><span data-stu-id="1911d-163">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing or Operator Connect.</span></span>


## <a name="phone-system"></a><span data-ttu-id="1911d-164">電話系統</span><span class="sxs-lookup"><span data-stu-id="1911d-164">Phone System</span></span>

<span data-ttu-id="1911d-165">電話系統 Microsoft 的技術，在 Microsoft 365 或 Office 365 雲端中啟用通話控制和私人分支 Exchange (PBX) 功能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-165">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="1911d-166">電話系統用戶端Teams或商務用 Skype認證裝置。</span><span class="sxs-lookup"><span data-stu-id="1911d-166">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="1911d-167">電話系統可讓您將現有的 PBX 系統取代為一組直接從 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1911d-167">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="1911d-168">貴組織使用者之間的通話在內部處理電話系統，而且永遠不會前往 PSTN (電話) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-168">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1911d-169">這適用于貴組織中位於不同地理區域的使用者之間的通話，可移除這些內部通話的長途費用。</span><span class="sxs-lookup"><span data-stu-id="1911d-169">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="1911d-170">本文將介紹下列電話系統功能，以及您需要考慮的部署決策：</span><span class="sxs-lookup"><span data-stu-id="1911d-170">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="1911d-171">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-171">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="1911d-172">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="1911d-172">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="1911d-173">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="1911d-173">Calling identity</span></span>](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

<span data-ttu-id="1911d-175">若要瞭解所有電話系統功能，以及如何設定電話系統，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-175">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="1911d-176">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="1911d-176">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- <span data-ttu-id="1911d-177">[設定貴組織的 [電話系統]](setting-up-your-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="1911d-177">[Set up Phone System in your organization](setting-up-your-phone-system.md)</span></span><br>
  <span data-ttu-id="1911d-178">說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="1911d-178">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="1911d-179">有關管理支援裝置的資訊，請參閱在[](devices/device-management.md)Microsoft Teams Teams[管理您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="1911d-179">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="1911d-180">自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-180">Auto attendants and Call queues</span></span>

<span data-ttu-id="1911d-181">自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。</span><span class="sxs-lookup"><span data-stu-id="1911d-181">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="1911d-182">通話佇列正在等待來電者的區域。</span><span class="sxs-lookup"><span data-stu-id="1911d-182">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="1911d-183">自動語音回應和通話佇列一起使用，可以輕鬆地將來電者路由至貴組織中適當的人員或部門。</span><span class="sxs-lookup"><span data-stu-id="1911d-183">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="1911d-184">有關自動電話機和通話佇列的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-184">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="1911d-185">規劃自動Teams和通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-185">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="1911d-186">設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="1911d-186">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="1911d-187">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-187">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="1911d-188">Contoso 案例研究：自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-188">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="1911d-189">說明一家虛構的多國公司 Contoso 如何實作自動語音語音和通話佇列，以尋求語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-189">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="1911d-190">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="1911d-190">Cloud Voicemail</span></span>

<span data-ttu-id="1911d-191">雲端語音信箱 Azure 語音信箱服務提供的支援，僅支援語音信箱Exchange信箱。</span><span class="sxs-lookup"><span data-stu-id="1911d-191">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="1911d-192">它不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="1911d-192">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="1911d-193">雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="1911d-193">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="1911d-194">您的業務需求可能會要求您針對特定使用者或整個組織的每一個人停用語音信箱翻譯。</span><span class="sxs-lookup"><span data-stu-id="1911d-194">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="1911d-195">只有線上使用者雲端語音信箱，系統會在使用者獲得授權後，自動設定電話系統設定。</span><span class="sxs-lookup"><span data-stu-id="1911d-195">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="1911d-196">對於電話系統信箱的使用者Exchange，您必須執行額外的組組步驟。</span><span class="sxs-lookup"><span data-stu-id="1911d-196">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="1911d-197">有關雲端語音信箱及其組雲端語音信箱，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-197">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- <span data-ttu-id="1911d-198">[設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="1911d-198">[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)</span></span>
- [<span data-ttu-id="1911d-199">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="1911d-199">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="1911d-200">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="1911d-200">Calling identity</span></span>

<span data-ttu-id="1911d-201">根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-201">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="1911d-202">來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。</span><span class="sxs-lookup"><span data-stu-id="1911d-202">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="1911d-203">有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱為使用者設定 [本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1911d-203">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="1911d-204">公用交換電話網路連接選項</span><span class="sxs-lookup"><span data-stu-id="1911d-204">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="1911d-205">電話系統為貴組織提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="1911d-205">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="1911d-206">不過，若要讓使用者在組織外撥打電話，您必須將電話電話系統到公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-206">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1911d-207">若要電話系統 PSTN，您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1911d-207">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="1911d-208">[**電話系統通話方案 。**](#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="1911d-208">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="1911d-209">以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-209">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="1911d-210">[**電話系統使用**](#phone-system-with-own-pstn-carrier-with-direct-routing)直接路由將您的內部部署環境連接到您的 PSTN 電信Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-210">[**Phone System with your own PSTN carrier by using Direct Routing**](#phone-system-with-own-pstn-carrier-with-direct-routing) to connect your on-premises environment to Teams.</span></span>

- <span data-ttu-id="1911d-211">[**電話系統您的 PSTN 電信公司使用運算子連線**](operator-connect-plan.md)，目前僅適用于公用 **預覽版。**</span><span class="sxs-lookup"><span data-stu-id="1911d-211">[**Phone System with your own PSTN carrier by using Operator Connect**](operator-connect-plan.md), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="1911d-212">使用運算子連線，如果您現有的接線員是 Microsoft Operator 連線 計畫的參與者，他們可以管理將 PSTN 通話Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-212">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="1911d-213">有關運算子的權益和需求連線，以及參與此計畫的運算子清單，請參閱規劃運算子[連線。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="1911d-213">For information on the benefits and requirements of Operator Connect, and for a list of operators participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span>

<span data-ttu-id="1911d-214">您也可以選擇選項群組合，以設計複雜環境的解決方案，或管理多步驟移 (移) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-214">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="1911d-215">電話系統通話方案</span><span class="sxs-lookup"><span data-stu-id="1911d-215">Phone System with Calling Plan</span></span> 

<span data-ttu-id="1911d-216">如本文前面所述，電話系統通話方案是 Microsoft 針對使用者所使用之全雲端語音Teams解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-216">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="1911d-217">這是將 Microsoft 電話 系統連接到公用交換電話網絡 (PSTN) 以啟用撥打全球有線電話和行動電話的最簡單選項。</span><span class="sxs-lookup"><span data-stu-id="1911d-217">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="1911d-218">有了這個選項，Microsoft Exchange (PBX) 提供貴組織的功能，並做為 PSTN 電信者，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="1911d-218">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![圖表 4 顯示電話系統語音機、通話佇列、本機號碼等，以及 Microsoft 作為 PSTN 電信業者](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="1911d-220">如果您對下列專案回答是，電話系統通話方案是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="1911d-220">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="1911d-221">地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-221">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="1911d-222">您不需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="1911d-222">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="1911d-223">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="1911d-223">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="1911d-224">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="1911d-224">With this option:</span></span> 

- <span data-ttu-id="1911d-225">您可以Microsoft 電話國內或國際通話方案來使用系統，這些方案 (視全球授權服務等級) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-225">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="1911d-226">您不需要部署或維護內部部署，因為通話方案無法 &mdash; Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1911d-226">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="1911d-227">注意：如有需要，您可以選擇透過直接路由連接支援的會話邊界控制器 (SBC) ，以與 SBC 支援的協力廠商 PBX、類比裝置和其他協力廠商電話設備進行互通性。</span><span class="sxs-lookup"><span data-stu-id="1911d-227">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="1911d-228">此選項需要不間斷地Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="1911d-228">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="1911d-229">有關通話方案的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-229">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="1911d-230">哪一個通話方案適合您？</span><span class="sxs-lookup"><span data-stu-id="1911d-230">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="1911d-231">如何購買通話方案</span><span class="sxs-lookup"><span data-stu-id="1911d-231">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="1911d-232">通話方案的適用國家與地區</span><span class="sxs-lookup"><span data-stu-id="1911d-232">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="1911d-233">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="1911d-233">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="1911d-234">電話系統具有直接路由的 PSTN 電信公司</span><span class="sxs-lookup"><span data-stu-id="1911d-234">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="1911d-235">此選項使用直接路由Microsoft 電話將系統連接到您的電話網絡，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="1911d-235">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![圖表 5 顯示電話系統路由的圖表](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="1911d-237">如果您對下列問題回答是，電話系統直接路由是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="1911d-237">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="1911d-238">您想要在 Teams 中電話系統。</span><span class="sxs-lookup"><span data-stu-id="1911d-238">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="1911d-239">您需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="1911d-239">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="1911d-240">您想要混合路由，有些通話會透過通話方案進行，有些則透過您的電信公司進行。</span><span class="sxs-lookup"><span data-stu-id="1911d-240">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="1911d-241">您需要與協力廠商 PBX 和/或設備進行交互操作，例如架空傳呼機、類比裝置等。</span><span class="sxs-lookup"><span data-stu-id="1911d-241">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="1911d-242">使用此選項：</span><span class="sxs-lookup"><span data-stu-id="1911d-242">With this option:</span></span>

- <span data-ttu-id="1911d-243">您將自己支援的 SBC Microsoft 電話系統，而不需要其他內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="1911d-243">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="1911d-244">您幾乎可以在任何電話電信業者使用 Microsoft 電話 System。</span><span class="sxs-lookup"><span data-stu-id="1911d-244">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="1911d-245">您可以選擇設定及管理這個選項，也可以由您的電信公司或合作夥伴設定及管理 (詢問您的電信公司或合作夥伴是否提供此選項) 。</span><span class="sxs-lookup"><span data-stu-id="1911d-245">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="1911d-246">您可以設定電話設備之間的互通性，例如協力廠商 PBX 和類比裝置Microsoft 電話 &mdash; &mdash; 系統。</span><span class="sxs-lookup"><span data-stu-id="1911d-246">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="1911d-247">此選項需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="1911d-247">This option requires the following:</span></span>

- <span data-ttu-id="1911d-248">不間斷地Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="1911d-248">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="1911d-249">部署及維護支援的 SBC。</span><span class="sxs-lookup"><span data-stu-id="1911d-249">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="1911d-250">與協力廠商電信公司簽訂合約。</span><span class="sxs-lookup"><span data-stu-id="1911d-250">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="1911d-251"> (除非已部署為選項，為使用通話方案的使用者提供協力廠商 PBX、類比裝置或其他電話電話系統裝置) </span><span class="sxs-lookup"><span data-stu-id="1911d-251">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="1911d-252">有關直接路由的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-252">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="1911d-253">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="1911d-253">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="1911d-254">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="1911d-254">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="1911d-255">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="1911d-255">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="1911d-256">管理語音路由策略，以用於直接路由</span><span class="sxs-lookup"><span data-stu-id="1911d-256">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="1911d-257">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="1911d-257">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="1911d-258">通過直接路由認證的工作階段邊界控制器清單</span><span class="sxs-lookup"><span data-stu-id="1911d-258">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="1911d-259">電話 Microsoft 的號碼</span><span class="sxs-lookup"><span data-stu-id="1911d-259">Phone numbers from Microsoft</span></span>

<span data-ttu-id="1911d-260">Microsoft 有兩種可用的電話號碼：訂閱者 *(* 使用者) 號碼，可指派給貴組織的使用者;以及服務號碼，以付費和免付費服務號碼提供。</span><span class="sxs-lookup"><span data-stu-id="1911d-260">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="1911d-261">服務號碼的並行通話容量高於訂閱者號碼，並可以指派給音訊會議、自動語音服務或通話佇列等服務。</span><span class="sxs-lookup"><span data-stu-id="1911d-261">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="1911d-262">您必須決定：</span><span class="sxs-lookup"><span data-stu-id="1911d-262">You will need to decide:</span></span>

- <span data-ttu-id="1911d-263">哪些使用者位置需要 Microsoft 的新電話號碼？</span><span class="sxs-lookup"><span data-stu-id="1911d-263">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="1911d-264">我需要哪一 (或服務) 電話號碼？</span><span class="sxs-lookup"><span data-stu-id="1911d-264">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="1911d-265">如何將現有的電話號碼Teams？</span><span class="sxs-lookup"><span data-stu-id="1911d-265">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="1911d-266">有關管理貴組織電話號碼 ，包括取得新號碼或移轉離職號碼等詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-266">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="1911d-267">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="1911d-267">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="1911d-268">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="1911d-268">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="1911d-269">為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="1911d-269">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="1911d-270">將電話號碼轉接到Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1911d-270">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="1911d-271">撥號方案與通話路由</span><span class="sxs-lookup"><span data-stu-id="1911d-271">Dial plans and call routing</span></span>

<span data-ttu-id="1911d-272">撥號方案是一組將撥號電話號碼轉換成替代格式的標準化規則 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1911d-272">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="1911d-273">您必須決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="1911d-273">You will need to decide the following:</span></span> 

- <span data-ttu-id="1911d-274">我的組織需要自訂的撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="1911d-274">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="1911d-275">哪些使用者需要自訂撥號方案？</span><span class="sxs-lookup"><span data-stu-id="1911d-275">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="1911d-276">應該為每個使用者指派哪一個租使用者撥號方案？</span><span class="sxs-lookup"><span data-stu-id="1911d-276">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="1911d-277">詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-277">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="1911d-278">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="1911d-278">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="1911d-279">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="1911d-279">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="1911d-280">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="1911d-280">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="1911d-281">緊急電話</span><span class="sxs-lookup"><span data-stu-id="1911d-281">Emergency calling</span></span>

<span data-ttu-id="1911d-282">您設定緊急電話方式會根據您的 PSTN 連接選項而不同：Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="1911d-282">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="1911d-283">Microsoft 通話方案與直接路由的動態緊急電話系統提供設定及路由緊急電話的能力，並依據用戶端目前的位置通知Teams人員。</span><span class="sxs-lookup"><span data-stu-id="1911d-283">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="1911d-284">若要進一步瞭解緊急電話概念和術語，以及如何設定動態緊急電話，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-284">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="1911d-285">管理緊急電話</span><span class="sxs-lookup"><span data-stu-id="1911d-285">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="1911d-286">規劃和設定動態緊急電話</span><span class="sxs-lookup"><span data-stu-id="1911d-286">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="1911d-287">Contoso 案例研究：緊急電話</span><span class="sxs-lookup"><span data-stu-id="1911d-287">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="1911d-288">說明一家虛構的多國公司 Contoso 如何為組織實作緊急電話。</span><span class="sxs-lookup"><span data-stu-id="1911d-288">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="1911d-289">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="1911d-289">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="1911d-290">在一些國家和地區，若要降低長途電話費用， (PSTN) 通電話網絡不合法。</span><span class="sxs-lookup"><span data-stu-id="1911d-290">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="1911d-291">Location-Based直接路由路由可讓您根據使用者Microsoft Teams限制付費旁路。</span><span class="sxs-lookup"><span data-stu-id="1911d-291">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="1911d-292">若要進一步瞭解如何規劃及設定 LBR Location-Based路由 (，請參閱) 文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-292">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="1911d-293">規劃直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="1911d-293">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="1911d-294">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="1911d-294">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="1911d-295">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="1911d-295">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="1911d-296">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="1911d-296">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="1911d-297">說明一家虛構的多國公司 Contoso 如何為Location-Based路由實作。</span><span class="sxs-lookup"><span data-stu-id="1911d-297">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="1911d-298">語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="1911d-298">Network topology for voice features</span></span>

<span data-ttu-id="1911d-299">如果您要部署動態緊急電話或直接路由Location-Based路由，您必須設定網路設定，以在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1911d-299">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="1911d-300">若要瞭解如何設定網路區域、網路網站、網路子網和受信任的 IP 位址的網路設定，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-300">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="1911d-301">雲端語音功能的網路設定Microsoft Teams概念和術語</span><span class="sxs-lookup"><span data-stu-id="1911d-301">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="1911d-302">管理雲端語音功能的網路拓撲Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1911d-302">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="1911d-303">將現有的語音解決方案遷移到 Teams</span><span class="sxs-lookup"><span data-stu-id="1911d-303">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="1911d-304">對於升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="1911d-304">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="1911d-305">只有在電話系統 TeamsOnly Teams，才支援在 Teams 中使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="1911d-305">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="1911d-306">如果您需要升級至 Teams 的基本資訊，請從這裡開始：</span><span class="sxs-lookup"><span data-stu-id="1911d-306">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="1911d-307">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1911d-307">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="1911d-308">關於升級架構</span><span class="sxs-lookup"><span data-stu-id="1911d-308">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="1911d-309">IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="1911d-309">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="1911d-310">移移您的語音解決方案時，移至 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="1911d-310">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="1911d-311">[**使用 Microsoft 通話商務用 Skype Online 中的使用者**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="1911d-311">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="1911d-312">升級後，該使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-312">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="1911d-313">**[透過內部商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 或雲端連接器版本使用內部部署語音功能的使用者商務用 Skype Online 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="1911d-313">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="1911d-314">使用者的升級至Teams使用者移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="1911d-314">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="1911d-315">使用 商務用 Skype 內部部署的使用者 **[企業語音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 該使用者將會移往線上並保持內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="1911d-315">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="1911d-316">將此使用者移Teams需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。</span><span class="sxs-lookup"><span data-stu-id="1911d-316">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="1911d-317">使用 商務用 Skype 內部部署 **[的使用者企業語音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 該使用者將會移往線上，並且使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-317">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="1911d-318">將該使用者移轉至 Teams 需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調該移動與 A) 該使用者電話號碼的埠到 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="1911d-318">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="1911d-319">若要進一步瞭解如何針對這些案例執行語音移移，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移向直接路由的資訊，請參閱 &mdash; &mdash; 下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-319">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="1911d-320">升級至適用于 IT 系統管理員的 PSTN Teams PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="1911d-320">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="1911d-321">Contoso 語音移移案例研究</span><span class="sxs-lookup"><span data-stu-id="1911d-321">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="1911d-322">案例研究說明一家虛構的多國公司 Contoso 如何為組織Teams語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="1911d-322">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="1911d-323">它包含下列文章：</span><span class="sxs-lookup"><span data-stu-id="1911d-323">It contains the following articles:</span></span>

  - [<span data-ttu-id="1911d-324">Teams升級方案</span><span class="sxs-lookup"><span data-stu-id="1911d-324">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="1911d-325">電話系統 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="1911d-325">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="1911d-326">位置式路由實現</span><span class="sxs-lookup"><span data-stu-id="1911d-326">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="1911d-327">緊急電話</span><span class="sxs-lookup"><span data-stu-id="1911d-327">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="1911d-328">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="1911d-328">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="1911d-329">音訊會議</span><span class="sxs-lookup"><span data-stu-id="1911d-329">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)