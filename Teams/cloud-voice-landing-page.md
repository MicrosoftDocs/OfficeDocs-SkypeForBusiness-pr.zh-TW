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
ms.openlocfilehash: 95b8f60f9d664432fbb68c48ee61d6f26902eeae
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354379"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="a321e-103">規劃您的Teams語音解決方案</span><span class="sxs-lookup"><span data-stu-id="a321e-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="a321e-104">本文可協助您決定適合貴組織的 Microsoft 語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="a321e-105">在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

<span data-ttu-id="a321e-106">您可能會想要使用通話方案 &mdash; 電話系統最簡單的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-106">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="a321e-107">這是 Microsoft 的全雲端解決方案，提供私人分支 Exchange (PBX) 功能，並撥打到公用交換電話網路 (PSTN) ，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="a321e-107">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="a321e-108">有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a321e-108">With this solution, Microsoft is your PSTN carrier.</span></span>

![圖表 1 顯示電話系統通話方案](media/voice-solutions-simple.png)

<span data-ttu-id="a321e-110">如果您對下列專案回答是，電話系統通話方案是適合的解決方案：</span><span class="sxs-lookup"><span data-stu-id="a321e-110">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="a321e-111">地區提供通話方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-111">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="a321e-112">您不需要保留目前的 PSTN 電信公司。</span><span class="sxs-lookup"><span data-stu-id="a321e-112">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="a321e-113">您想要使用 Microsoft 管理的 PSTN 存取權。</span><span class="sxs-lookup"><span data-stu-id="a321e-113">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="a321e-114">不過，您的情況可能較為複雜。</span><span class="sxs-lookup"><span data-stu-id="a321e-114">However, your situation might be more complex.</span></span> <span data-ttu-id="a321e-115">例如，您可能有辦公室位於沒有通話方案的位置。</span><span class="sxs-lookup"><span data-stu-id="a321e-115">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="a321e-116">或者，您可能需要支援複雜、多國部署的組合解決方案，且不同的地理位置有不同的需求。</span><span class="sxs-lookup"><span data-stu-id="a321e-116">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="a321e-117">Microsoft 支援一組解決方案：</span><span class="sxs-lookup"><span data-stu-id="a321e-117">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="a321e-118">電話系統通話方案</span><span class="sxs-lookup"><span data-stu-id="a321e-118">Phone System with Calling Plan</span></span>
- <span data-ttu-id="a321e-119">電話系統具有運算子的 PSTN 電信連線 (目前僅適用于公用 **預覽版)**</span><span class="sxs-lookup"><span data-stu-id="a321e-119">Phone System with your own PSTN carrier with Operator Connect (currently available only in **public preview**)</span></span>
- <span data-ttu-id="a321e-120">電話系統直接路由使用您自己的 PSTN 電信公司</span><span class="sxs-lookup"><span data-stu-id="a321e-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="a321e-121">搭配通話方案使用電話系統組合解決方案電話系統運算子連線，以及/或電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="a321e-121">A combination solution that uses Phone System with Calling Plan, Phone System with Operator Connect, and/or Phone System with Direct Routing</span></span>


## <a name="what-do-you-need-to-read"></a><span data-ttu-id="a321e-122">您需要閱讀哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="a321e-122">What do you need to read?</span></span>

<span data-ttu-id="a321e-123">**全部為必填專案。**</span><span class="sxs-lookup"><span data-stu-id="a321e-123">**Required for all.**</span></span> <span data-ttu-id="a321e-124">本文中的部分章節與所有組織有關。</span><span class="sxs-lookup"><span data-stu-id="a321e-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="a321e-125">例如，每個人都應該閱讀電話系統並瞭解在 PSTN 中連接至公用交換電話網絡 (選項) 。</span><span class="sxs-lookup"><span data-stu-id="a321e-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="a321e-126">全部為必填專案</span><span class="sxs-lookup"><span data-stu-id="a321e-126">Required for all</span></span> | <span data-ttu-id="a321e-127">說明</span><span class="sxs-lookup"><span data-stu-id="a321e-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="a321e-128">**電話系統**</span><span class="sxs-lookup"><span data-stu-id="a321e-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="a321e-129">Microsoft 的技術可啟用通話控制和私人分支Exchange (PBX) 雲端Microsoft 365功能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="a321e-130">**公用交換電話網絡 (PSTN) 連接選項**</span><span class="sxs-lookup"><span data-stu-id="a321e-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="a321e-131">使用 Microsoft 做為電話電信業者，或使用直接路由或電信業者Microsoft Teams電話電信業者連線。</span><span class="sxs-lookup"><span data-stu-id="a321e-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing or Operator Connect.</span></span> <span data-ttu-id="a321e-132">PSTN 電話系統結合，可讓使用者撥打全球電話。</span><span class="sxs-lookup"><span data-stu-id="a321e-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="a321e-133">**視您的需求而不同。**</span><span class="sxs-lookup"><span data-stu-id="a321e-133">**Depending on your requirements.**</span></span> <span data-ttu-id="a321e-134">本文和相關文章中的一些章節會根據您的現有部署和需求而相關。</span><span class="sxs-lookup"><span data-stu-id="a321e-134">Some of the sections in this and related articles are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="a321e-135">例如，Location-Based不允許免付費路的地理位置中的直接路由客戶，才需要直接路由。</span><span class="sxs-lookup"><span data-stu-id="a321e-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="a321e-136">請考慮您可能需要的這些額外配置：</span><span class="sxs-lookup"><span data-stu-id="a321e-136">Consider which of these additional configurations you might need:</span></span>

![圖表 2 顯示其他語音元件，例如電話的號碼、撥號方案及通話路由等等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="a321e-138">根據您的需求</span><span class="sxs-lookup"><span data-stu-id="a321e-138">Depending on your requirements</span></span> | <span data-ttu-id="a321e-139">說明</span><span class="sxs-lookup"><span data-stu-id="a321e-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="a321e-140">**電話號碼管理**</span><span class="sxs-lookup"><span data-stu-id="a321e-140">**Phone number management**</span></span>](pstn-connectivity.md#phone-number-management) | <span data-ttu-id="a321e-141">如何取得和管理電話號碼會根據您的 PSTN 連接選項而不同。</span><span class="sxs-lookup"><span data-stu-id="a321e-141">How to get and manage phone numbers differs depending on your PSTN connectivity option.</span></span> <span data-ttu-id="a321e-142">如果您需要取得電話號碼、傳輸現有號碼、取得服務號碼等，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a321e-142">Read this section if you need to obtain phone numbers, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="a321e-143">**通話路由和撥號方案**</span><span class="sxs-lookup"><span data-stu-id="a321e-143">**Call routing and dial plans**</span></span>](pstn-connectivity.md#call-routing-and-dial-plans) | <span data-ttu-id="a321e-144">如何設定及管理撥號方案，將撥號電話號碼轉換成替代格式 (通常是 E.164 格式) 電話授權和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a321e-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="a321e-145">如果您需要瞭解什麼是撥號方案，以及您是否需要為貴組織指定撥號方案，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a321e-145">Read this section if you need to understand what dial plans are and whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="a321e-146">**緊急電話**</span><span class="sxs-lookup"><span data-stu-id="a321e-146">**Emergency calling**</span></span>](pstn-connectivity.md#emergency-calling) | <span data-ttu-id="a321e-147">如何管理及設定緊急電話會根據您的 PSTN 連接選項而不同。</span><span class="sxs-lookup"><span data-stu-id="a321e-147">How to manage and configure emergency calling differs depending on your PSTN connectivity option.</span></span> <span data-ttu-id="a321e-148">如果您需要瞭解如何管理組織的緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a321e-148">Read this section if you need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="a321e-149">**直接路由的基於位置的路由**</span><span class="sxs-lookup"><span data-stu-id="a321e-149">**Location-Based Routing for Direct Routing**</span></span>](pstn-connectivity.md#location-based-routing-for-direct-routing) |<span data-ttu-id="a321e-150">如何使用 LBR Location-Based路由 (，) 使用者根據地理位置Microsoft Teams免付費路。</span><span class="sxs-lookup"><span data-stu-id="a321e-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="a321e-151">如果貴組織在不允許免付費路的位置使用直接路由，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a321e-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="a321e-152">**雲端語音功能的網路拓撲**</span><span class="sxs-lookup"><span data-stu-id="a321e-152">**Network topology for cloud voice features**</span></span>](pstn-connectivity.md#network-topology-for-voice-features) | <span data-ttu-id="a321e-153">如果貴組織正在部署 Location-Based路由 (LBR) 直接路由或動態緊急電話，您必須設定網路設定，以在 Microsoft Teams 中與這些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="a321e-154">如果您正針對直接路由執行 LBR，或是使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。</span><span class="sxs-lookup"><span data-stu-id="a321e-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="a321e-155">**遷移現有的語音解決方案**</span><span class="sxs-lookup"><span data-stu-id="a321e-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="a321e-156">當您將語音解決方案移向 Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="a321e-157">如果您要從現有的語音解決方案移向新的語音解決方案，請閱讀Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 

> [!Important]
> <span data-ttu-id="a321e-158">本文著重于語音解決方案與Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="a321e-159">雖然仍商務用 Skype線上版解決方案，但必須瞭解 商務用 Skype Online 將于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="a321e-159">While solutions with Skype for Business Online are still available, it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="a321e-160">在此日期之後，商務用 Skype線上服務將無法再使用。</span><span class="sxs-lookup"><span data-stu-id="a321e-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="a321e-161">此外，不再支援內部部署環境之間的 PSTN 連線商務用 Skype Server雲端連接器版本和 商務用 Skype Online 之間的 &mdash; &mdash; PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="a321e-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="a321e-162">本文將介紹Teams語音解決方案，以及如何在必要時使用直接路由或運算子Teams內部部署電話網絡連線。</span><span class="sxs-lookup"><span data-stu-id="a321e-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing or Operator Connect.</span></span>


## <a name="phone-system"></a><span data-ttu-id="a321e-163">電話系統</span><span class="sxs-lookup"><span data-stu-id="a321e-163">Phone System</span></span>

<span data-ttu-id="a321e-164">電話系統 Microsoft 的技術，可啟用通話控制與私人分支 Exchange (PBX) 雲端Microsoft 365功能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="a321e-165">電話系統用戶端Teams或商務用 Skype認證裝置。</span><span class="sxs-lookup"><span data-stu-id="a321e-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="a321e-166">電話系統可讓您將現有的 PBX 系統取代為一組直接從 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a321e-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365.</span></span> 

<span data-ttu-id="a321e-167">貴組織使用者之間的通話在內部處理電話系統，而且永遠不會前往 PSTN (電話) 。</span><span class="sxs-lookup"><span data-stu-id="a321e-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a321e-168">這適用于貴組織中位於不同地理區域的使用者之間的通話，可移除這些內部通話的長途費用。</span><span class="sxs-lookup"><span data-stu-id="a321e-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="a321e-169">本文將介紹下列電話系統功能，以及您需要考慮的部署決策：</span><span class="sxs-lookup"><span data-stu-id="a321e-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="a321e-170">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="a321e-171">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a321e-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="a321e-172">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="a321e-172">Calling identity</span></span>](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

<span data-ttu-id="a321e-174">若要瞭解所有電話系統功能，以及如何設定電話系統，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a321e-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="a321e-175">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="a321e-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- <span data-ttu-id="a321e-176">[設定貴組織的 [電話系統]](setting-up-your-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="a321e-176">[Set up Phone System in your organization](setting-up-your-phone-system.md)</span></span><br>
  <span data-ttu-id="a321e-177">說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="a321e-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="a321e-178">有關管理支援裝置的資訊，請參閱在[](devices/device-management.md)Microsoft Teams Teams[管理您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="a321e-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="a321e-179">自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="a321e-180">自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。</span><span class="sxs-lookup"><span data-stu-id="a321e-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="a321e-181">通話佇列正在等待來電者的區域。</span><span class="sxs-lookup"><span data-stu-id="a321e-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="a321e-182">自動語音回應和通話佇列一起使用，可以輕鬆地將來電者路由至貴組織中適當的人員或部門。</span><span class="sxs-lookup"><span data-stu-id="a321e-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="a321e-183">有關自動電話機和通話佇列的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a321e-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="a321e-184">規劃自動Teams和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="a321e-185">設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="a321e-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="a321e-186">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="a321e-187">Contoso 案例研究：自動電話機和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="a321e-188">說明一家虛構的多國公司 Contoso 如何實作自動語音語音和通話佇列，以尋求語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="a321e-189">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="a321e-189">Cloud Voicemail</span></span>

<span data-ttu-id="a321e-190">雲端語音信箱 Azure 語音信箱服務提供的支援，僅支援語音信箱Exchange信箱。</span><span class="sxs-lookup"><span data-stu-id="a321e-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="a321e-191">它不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="a321e-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="a321e-192">雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="a321e-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="a321e-193">您的業務需求可能會要求您針對特定使用者或整個組織的每一個人停用語音信箱翻譯。</span><span class="sxs-lookup"><span data-stu-id="a321e-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="a321e-194">只有線上使用者雲端語音信箱，系統會在使用者獲得授權後，自動設定電話系統設定。</span><span class="sxs-lookup"><span data-stu-id="a321e-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="a321e-195">對於電話系統信箱的使用者Exchange，您必須執行額外的組組步驟。</span><span class="sxs-lookup"><span data-stu-id="a321e-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="a321e-196">有關雲端語音信箱及其組雲端語音信箱，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="a321e-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- <span data-ttu-id="a321e-197">[設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="a321e-197">[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)</span></span>
- [<span data-ttu-id="a321e-198">在組織中設定語音信箱政策</span><span class="sxs-lookup"><span data-stu-id="a321e-198">Set voicemail policies in your organization</span></span>](manage-voicemail-policies.md)


### <a name="calling-identity"></a><span data-ttu-id="a321e-199">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="a321e-199">Calling identity</span></span>

<span data-ttu-id="a321e-200">根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。</span><span class="sxs-lookup"><span data-stu-id="a321e-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="a321e-201">來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。</span><span class="sxs-lookup"><span data-stu-id="a321e-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="a321e-202">有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱為使用者設定 [本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a321e-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="a321e-203">公用交換電話網路連接選項</span><span class="sxs-lookup"><span data-stu-id="a321e-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="a321e-204">電話系統為貴組織提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="a321e-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="a321e-205">不過，若要讓使用者在組織外撥打電話，您必須將電話電話系統到公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="a321e-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a321e-206">若要電話系統 PSTN，您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="a321e-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="a321e-207">[**電話系統通話方案 。**](pstn-connectivity.md#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="a321e-207">[**Phone System with Calling Plan**](pstn-connectivity.md#phone-system-with-calling-plan).</span></span> <span data-ttu-id="a321e-208">以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="a321e-209">[**電話系統使用**](pstn-connectivity.md#phone-system-with-direct-routing)直接路由將您的內部部署環境連接到您的 PSTN 電信Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-209">[**Phone System with your own PSTN carrier by using Direct Routing**](pstn-connectivity.md#phone-system-with-direct-routing) to connect your on-premises environment to Teams.</span></span>

- <span data-ttu-id="a321e-210">[**電話系統您的 PSTN 電信公司使用運算子連線**](operator-connect-plan.md)，目前僅適用于公用 **預覽版。**</span><span class="sxs-lookup"><span data-stu-id="a321e-210">[**Phone System with your own PSTN carrier by using Operator Connect**](operator-connect-plan.md), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="a321e-211">使用運算子連線，如果您現有的接線員是 Microsoft Operator 連線 計畫的參與者，他們可以管理將 PSTN 通話Teams。</span><span class="sxs-lookup"><span data-stu-id="a321e-211">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="a321e-212">有關運算子的權益和需求連線，以及參與此計畫的運算子清單，請參閱規劃運算子[連線。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="a321e-212">For information on the benefits and requirements of Operator Connect, and for a list of operators participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span>

<span data-ttu-id="a321e-213">您也可以選擇選項群組合，以設計複雜環境的解決方案，或管理多步驟移 (移) 。</span><span class="sxs-lookup"><span data-stu-id="a321e-213">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

<span data-ttu-id="a321e-214">無論您選擇電話系統 PSTN 連接選項，大多數的功能都是相同的。</span><span class="sxs-lookup"><span data-stu-id="a321e-214">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="a321e-215">不過，功能有一些差異，會影響您設定特定 電話系統功能 ，例如呼叫路由和緊急電話。</span><span class="sxs-lookup"><span data-stu-id="a321e-215">There are some differences in functionality, however, that affect how you configure certain Phone System features, such as call routing and emergency calling.</span></span> <span data-ttu-id="a321e-216">有關 PSTN 連接選項和這些組組考慮的詳細資訊，請參閱 [PSTN 連接選項](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="a321e-216">For more information about PSTN connectivity options and these configuration considerations, see [PSTN connectivity options](pstn-connectivity.md).</span></span>


## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="a321e-217">將現有的語音解決方案遷移到 Teams</span><span class="sxs-lookup"><span data-stu-id="a321e-217">Migrate your existing voice solution to Teams</span></span>

> [!NOTE]
> <span data-ttu-id="a321e-218">有關規劃 Teams 語音解決方案做為從 商務用 Skype Server 升級至 Teams 的整體計畫之一的指引，請參閱從 商務用 Skype 內部部署升級到 Teams 的[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)考慮。</span><span class="sxs-lookup"><span data-stu-id="a321e-218">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="a321e-219">對於升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="a321e-219">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="a321e-220">只有在電話系統 TeamsOnly Teams，才支援在 Teams 中使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="a321e-220">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="a321e-221">如果您需要升級至 Teams 的基本資訊，請從這裡開始：</span><span class="sxs-lookup"><span data-stu-id="a321e-221">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="a321e-222">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a321e-222">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="a321e-223">關於升級架構</span><span class="sxs-lookup"><span data-stu-id="a321e-223">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="a321e-224">IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="a321e-224">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="a321e-225">移移您的語音解決方案時，移至 TeamsOnly 模式時，有四種可能的通話案例：</span><span class="sxs-lookup"><span data-stu-id="a321e-225">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="a321e-226">[**使用 Microsoft 通話商務用 Skype Online 中的使用者**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="a321e-226">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="a321e-227">升級後，該使用者會繼續擁有 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-227">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="a321e-228">**[透過內部商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 或雲端連接器版本使用內部部署語音功能的使用者商務用 Skype Online 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="a321e-228">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="a321e-229">使用者的升級至Teams使用者移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="a321e-229">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="a321e-230">使用 商務用 Skype 內部部署的使用者 **[企業語音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 該使用者將會移往線上並保持內部部署 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="a321e-230">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="a321e-231">將此使用者移Teams需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。</span><span class="sxs-lookup"><span data-stu-id="a321e-231">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="a321e-232">使用 商務用 Skype 內部部署 **[的使用者企業語音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 該使用者將會移往線上，並且使用 Microsoft 通話方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-232">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="a321e-233">將該使用者移轉至 Teams 需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調該移動與 A) 該使用者電話號碼的埠到 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。</span><span class="sxs-lookup"><span data-stu-id="a321e-233">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="a321e-234">若要進一步瞭解如何針對這些案例執行語音移移，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移向直接路由的資訊，請參閱 &mdash; &mdash; 下列文章：</span><span class="sxs-lookup"><span data-stu-id="a321e-234">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="a321e-235">升級至適用于 IT 系統管理員的 PSTN Teams PSTN 考慮</span><span class="sxs-lookup"><span data-stu-id="a321e-235">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="a321e-236">Contoso 語音移移案例研究</span><span class="sxs-lookup"><span data-stu-id="a321e-236">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="a321e-237">案例研究說明一家虛構的多國公司 Contoso 如何為組織Teams語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="a321e-237">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="a321e-238">它包含下列文章：</span><span class="sxs-lookup"><span data-stu-id="a321e-238">It contains the following articles:</span></span>

  - [<span data-ttu-id="a321e-239">Teams升級方案</span><span class="sxs-lookup"><span data-stu-id="a321e-239">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="a321e-240">電話系統 PSTN 連接選項</span><span class="sxs-lookup"><span data-stu-id="a321e-240">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="a321e-241">位置式路由實現</span><span class="sxs-lookup"><span data-stu-id="a321e-241">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="a321e-242">緊急電話</span><span class="sxs-lookup"><span data-stu-id="a321e-242">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="a321e-243">自動語音應答和通話佇列</span><span class="sxs-lookup"><span data-stu-id="a321e-243">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="a321e-244">音訊會議</span><span class="sxs-lookup"><span data-stu-id="a321e-244">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)
