---
title: 評估您的雲端語音工作負載環境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和網路分析來評估貴組織的整備狀態、開啟正確的 TCP 和 UDP 埠、執行任何網路補救。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b65e6f2f6db4f5e824e55368d0a7a097eb39ad9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094771"
---
# <a name="evaluate-my-environment"></a><span data-ttu-id="8feef-103">評估我的環境</span><span class="sxs-lookup"><span data-stu-id="8feef-103">Evaluate my environment</span></span>

<span data-ttu-id="8feef-104">本文提供正確評估您目前使用雲端語音服務之環境的需求概觀。</span><span class="sxs-lookup"><span data-stu-id="8feef-104">This article gives an overview of the requirements for properly evaluating your current environment for using cloud voice services.</span></span> <span data-ttu-id="8feef-105">您可以評估您的環境，找出會影響整體雲端語音部署的風險和需求。</span><span class="sxs-lookup"><span data-stu-id="8feef-105">By evaluating your environment, you identify risks and requirements that will influence your overall cloud voice deployment.</span></span> <span data-ttu-id="8feef-106">您可以事先識別這些專案，以調整您的規劃以推動成功。</span><span class="sxs-lookup"><span data-stu-id="8feef-106">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-evaluating-your-environment"></a><span data-ttu-id="8feef-107">評估環境簡介</span><span class="sxs-lookup"><span data-stu-id="8feef-107">Introduction to evaluating your environment</span></span>

<span data-ttu-id="8feef-108">若要在 OKRs (達成) ，您先前會做出重要的服務決策。</span><span class="sxs-lookup"><span data-stu-id="8feef-108">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="8feef-109">下一個步驟是執行環境探索，評估與 IT 和電話基礎結構、網路和營運相關的所有層面，以確認貴組織已準備好執行解決方案。</span><span class="sxs-lookup"><span data-stu-id="8feef-109">The next step is to perform environmental discovery to evaluate all aspects relating to your IT and telephony infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span>

<span data-ttu-id="8feef-110">環境探索必須包含網路就緒性評定，以確保您的網路能夠支援音訊會議或電話系統與通話方案服務的執行。</span><span class="sxs-lookup"><span data-stu-id="8feef-110">Environmental discovery must include network readiness assessment to ensure your network can support the implementation of the Audio Conferencing or Phone System with Calling Plan services.</span></span>

<span data-ttu-id="8feef-111">您將技術風險識別為環境評估與採用準備評估的一部分，並針對每個已識別的風險制定緩解計畫。</span><span class="sxs-lookup"><span data-stu-id="8feef-111">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span>
<span data-ttu-id="8feef-112">您應該在風險註冊簿中加入這項資訊。</span><span class="sxs-lookup"><span data-stu-id="8feef-112">You should incorporate this information in the risk register.</span></span>

<!--ENDOFSECTION-->

## <a name="current-environment"></a><span data-ttu-id="8feef-113">目前環境</span><span class="sxs-lookup"><span data-stu-id="8feef-113">Current environment</span></span>

<span data-ttu-id="8feef-114">在環境探索中，包含與使用者計算相關的所有事項，例如電腦和行動裝置就緒性評定，以支援音訊會議與電話系統與通話方案商務使用案例，從硬體需求到軟體需求。</span><span class="sxs-lookup"><span data-stu-id="8feef-114">As part of your environmental discovery, include all matters related to end-user computing, such as a readiness assessment of PCs and mobile devices to support Audio Conferencing and Phone System with Calling Plan business use cases, from hardware requirements to software requirements.</span></span>

<span data-ttu-id="8feef-115">環境探索也可以發現您是否需要將電話號碼[移轉至 Microsoft。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8feef-115">Environmental discovery can also uncover whether you need to [transfer phone numbers to Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
<span data-ttu-id="8feef-116">瞭解這可協助貴組織調整其專案計劃，並準備數位移植的必要資訊。</span><span class="sxs-lookup"><span data-stu-id="8feef-116">Knowing this will help your organization adjust its project plan accordingly and prepare the necessary information for number porting.</span></span> <span data-ttu-id="8feef-117">您可以使用 Microsoft [Teams 的環境探索推出來](environmental-discovery-for-microsoft-teams-rollout.md) 執行環境探索。</span><span class="sxs-lookup"><span data-stu-id="8feef-117">You can use the [Environmental discovery for Microsoft Teams rollout](environmental-discovery-for-microsoft-teams-rollout.md) to perform environmental discovery.</span></span>

<table>
<tr><td><span data-ttu-id="8feef-118">標題</span><span class="sxs-lookup"><span data-stu-id="8feef-118">Title</span></span></td><td><span data-ttu-id="8feef-119">描述</span><span class="sxs-lookup"><span data-stu-id="8feef-119">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="8feef-120">決策點</span><span class="sxs-lookup"><span data-stu-id="8feef-120">Decision points</span></span></td><td><ul><li><span data-ttu-id="8feef-121">誰負責完成環境評估？</span><span class="sxs-lookup"><span data-stu-id="8feef-121">Who will be responsible for completing an environment assessment?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="8feef-122">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8feef-122">Next steps</span></span></td><td><ul><li><span data-ttu-id="8feef-123">記錄環境評定的結果。</span><span class="sxs-lookup"><span data-stu-id="8feef-123">Document the results of the environment assessment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a><span data-ttu-id="8feef-124">採用及變更管理評定功能</span><span class="sxs-lookup"><span data-stu-id="8feef-124">Adoption and change management assessment capabilities</span></span>

<span data-ttu-id="8feef-125">部署可讓使用者輕鬆取得新技術，但只有在使用者真正採用解決方案做為自己的解決方案之後，才能取得商業結果。</span><span class="sxs-lookup"><span data-stu-id="8feef-125">Deployment puts a new technology at a user's fingertips, but business results are only realized after users truly adopt that solution as their own.</span></span> <span data-ttu-id="8feef-126">若要協助確保持續採用新解決方案，您必須將精力集中在使用者準備狀態和變更管理上。</span><span class="sxs-lookup"><span data-stu-id="8feef-126">To help ensure sustained adoption of a new solution, you'll need to focus your efforts on user readiness and change management.</span></span> <span data-ttu-id="8feef-127">若要獲得最佳結果，請進行使用者準備規劃，做為技術準備活動的平行作業，並納入下列活動：</span><span class="sxs-lookup"><span data-stu-id="8feef-127">For optimal results, conduct user readiness planning as a parallel workstream to your technical readiness activities and incorporate the following activities:</span></span>

-   <span data-ttu-id="8feef-128">**組織和使用者剖析：** 除了使用案例和人員分析之外，組織對變更的不信度分析</span><span class="sxs-lookup"><span data-stu-id="8feef-128">**Organizational and user profiling:** Analysis of organizational receptiveness to change in addition to use case and persona analysis</span></span>

-   <span data-ttu-id="8feef-129">**準備狀態和資源準備：** 建立具有目標且廣範圍的認知、訓練和支援資源，包括焦點價值訊息，以加速使用者購買</span><span class="sxs-lookup"><span data-stu-id="8feef-129">**Readiness and resource preparation:** Creation of targeted and broad-reach awareness, training, and support resources, including focused value messaging to accelerate user buy-in</span></span>

<span data-ttu-id="8feef-130">請使用下列考慮來評估貴組織的準備程度，以解決使用者變更管理。</span><span class="sxs-lookup"><span data-stu-id="8feef-130">Use the following considerations to assess your organization's preparedness to address user change management.</span></span>

<table>
<tr><td><span data-ttu-id="8feef-131">標題</span><span class="sxs-lookup"><span data-stu-id="8feef-131">Title</span></span></td><td><span data-ttu-id="8feef-132">描述</span><span class="sxs-lookup"><span data-stu-id="8feef-132">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="8feef-133">決策點</span><span class="sxs-lookup"><span data-stu-id="8feef-133">Decision points</span></span></td><td><ul><li><span data-ttu-id="8feef-134">您之前是否成功採用軟體或服務？</span><span class="sxs-lookup"><span data-stu-id="8feef-134">Have you had previous success with user adoption of software or services?</span></span></li><li><span data-ttu-id="8feef-135">您可以追蹤使用方式的使用方式嗎？</span><span class="sxs-lookup"><span data-stu-id="8feef-135">Can you track usage uptake?</span></span></li><li><span data-ttu-id="8feef-136">您擁有資源來設計和管理初始和持續採用行銷活動， (認知、訓練 &mdash; &mdash; 和支援) ？</span><span class="sxs-lookup"><span data-stu-id="8feef-136">Do you have the resources to design and manage an initial&mdash;and ongoing&mdash;adoption campaign (awareness, training, and support)?</span></span></li><li><span data-ttu-id="8feef-137">您是否有專屬的使用者採用/變更管理團隊，或可以投資這些資源以確保業務成果？</span><span class="sxs-lookup"><span data-stu-id="8feef-137">Do you have a dedicated user adoption/change management team, or can you invest in those resources to ensure business outcomes?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="8feef-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8feef-138">Next steps</span></span></td><td><ul><li><span data-ttu-id="8feef-139">如果您對上述所有專案都回答是，請找出正確的使用者變更管理專案關係人， &quot; &quot; 並開始您的使用者準備規劃。</span><span class="sxs-lookup"><span data-stu-id="8feef-139">If you answered &quot;yes&quot; to all of the above, identify the right user change management stakeholders and begin your user readiness planning.</span></span></li><li><span data-ttu-id="8feef-140">如果您對上述部分或所有專案回答否，請考慮使用外部資源以協助推動貴組織的變更管理和採用 &quot; &quot; 相關活動。</span><span class="sxs-lookup"><span data-stu-id="8feef-140">If you answered &quot;no&quot; to some or all of the above, consider engaging outside resources to assist with driving change management and adoption-related activities for your organization.</span></span></li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a><span data-ttu-id="8feef-141">網路就緒</span><span class="sxs-lookup"><span data-stu-id="8feef-141">Network readiness</span></span>

<span data-ttu-id="8feef-142">Teams 會使用音訊和視 (編解碼) 編解碼器，這些程式可以適應大部分網路條件，因此在大部分網路條件下執行效果更好。</span><span class="sxs-lookup"><span data-stu-id="8feef-142">Teams uses audio and video technology (codecs) that can adapt to—and therefore perform better under—most network conditions.</span></span> <span data-ttu-id="8feef-143">為了確保最佳且一致的績效，您應該為 Teams 準備您的網路。</span><span class="sxs-lookup"><span data-stu-id="8feef-143">To ensure optimal and consistent performance, you should prepare your network for Teams.</span></span>

<span data-ttu-id="8feef-144">![描述品質三個要素的圖表](media/evaluate-my-environment-image1.png "描述品質的三個元件，以及服務管理如何與這三個元件重迭的圖表。將焦點放在網路上。")</span><span class="sxs-lookup"><span data-stu-id="8feef-144">![Diagram describing the three components of quality](media/evaluate-my-environment-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on the network.")</span></span>

## <a name="key-takeaways"></a><span data-ttu-id="8feef-145">金鑰外賣</span><span class="sxs-lookup"><span data-stu-id="8feef-145">Key takeaways</span></span>

<span data-ttu-id="8feef-146">以下為本指南的主要說明。</span><span class="sxs-lookup"><span data-stu-id="8feef-146">These are the main takeaways from this guidance.</span></span> <span data-ttu-id="8feef-147">您必須：</span><span class="sxs-lookup"><span data-stu-id="8feef-147">You must:</span></span>

-   <span data-ttu-id="8feef-148">從將使用 Teams 的用戶端開啟 TCP 埠 80 和 443 外發。</span><span class="sxs-lookup"><span data-stu-id="8feef-148">Open TCP ports 80 and 443 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="8feef-149">從將使用 Teams 的用戶端開啟 UDP 埠 3478 到 3481 外發。</span><span class="sxs-lookup"><span data-stu-id="8feef-149">Open UDP ports 3478 through 3481 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="8feef-150">確保您有足夠的頻寬來部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="8feef-150">Ensure that you have sufficient bandwidth for deploying Teams.</span></span>

-   <span data-ttu-id="8feef-151">執行 [網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) ，並確保您同時符合邊緣區段和用戶端區段的 [媒體](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 品質和網路連接能力描述的需求。</span><span class="sxs-lookup"><span data-stu-id="8feef-151">Run the [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) and ensure that you meet the requirements described in [Media quality and network connectivity performance](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) from both the edge segment and the client segment.</span></span>

## <a name="why-should-you-prepare-your-network"></a><span data-ttu-id="8feef-152">為什麼要準備您的網路？</span><span class="sxs-lookup"><span data-stu-id="8feef-152">Why should you prepare your network?</span></span>

<span data-ttu-id="8feef-153">在查看要採取的步驟之前，瞭解哪些因素會影響 Teams 的績效，進而影響使用者的滿意度和滿意度，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="8feef-153">Before we look at the steps to be taken, it's important to understand what can affect the performance of Teams and thereby user happiness and satisfaction.</span></span>
<span data-ttu-id="8feef-154">三個主要的風險區域可能會影響使用者對網路品質的感知：</span><span class="sxs-lookup"><span data-stu-id="8feef-154">Three major risk areas can affect how users perceive network quality:</span></span>

-   <span data-ttu-id="8feef-155">可用的頻寬不足</span><span class="sxs-lookup"><span data-stu-id="8feef-155">Insufficient bandwidth available</span></span>

-   <span data-ttu-id="8feef-156">防火牆和 Proxy 封鎖程式</span><span class="sxs-lookup"><span data-stu-id="8feef-156">Firewall and proxy blockers</span></span>

-   <span data-ttu-id="8feef-157">網路障礙，例如抖動和封包遺失</span><span class="sxs-lookup"><span data-stu-id="8feef-157">Network impairments such as jitter and packet loss</span></span>

<span data-ttu-id="8feef-158">下列步驟可協助判斷您的部署是否可能受上述任何一項因素影響，並有助於朝解決方向移動。</span><span class="sxs-lookup"><span data-stu-id="8feef-158">The steps described below will help you determine whether your deployment might be affected by any of these factors and will help you move toward a resolution.</span></span>
<span data-ttu-id="8feef-159">若無法準備您的網路，可能會導致使用者不滿意，以及代價昂貴的臨時修正程式。</span><span class="sxs-lookup"><span data-stu-id="8feef-159">Failing to prepare your network will likely lead to dissatisfied users and costly, ad-hoc fixes.</span></span> <span data-ttu-id="8feef-160">為 Teams 準備您的網路與組織，可以大幅提升成功的機會。</span><span class="sxs-lookup"><span data-stu-id="8feef-160">By preparing your network—and your organization—for Teams, you can dramatically increase your chance of success.</span></span>

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a><span data-ttu-id="8feef-161">頻寬規劃</span><span class="sxs-lookup"><span data-stu-id="8feef-161">Bandwidth planning</span></span>

<span data-ttu-id="8feef-162">網路就緒的第一個步驟，就是確保您的網路有足夠的頻寬可供 Teams 提供給使用者的方式使用。</span><span class="sxs-lookup"><span data-stu-id="8feef-162">The first step toward network readiness is ensuring your network has enough bandwidth available for the modalities Teams will provide to users.</span></span> <span data-ttu-id="8feef-163">規劃足夠的頻寬是相當簡單的工作，也是確保使用者擁有高品質 Teams 體驗的低障礙開始。</span><span class="sxs-lookup"><span data-stu-id="8feef-163">Planning for sufficient bandwidth is a fairly straightforward task and a very low-barrier start to ensure your users will have a high-quality Teams experience.</span></span>

### <a name="local-internet-egress"></a><span data-ttu-id="8feef-164">當地網際網路出口</span><span class="sxs-lookup"><span data-stu-id="8feef-164">Local internet egress</span></span>

<span data-ttu-id="8feef-165">許多網路是設計成使用中樞和分支拓撲。</span><span class="sxs-lookup"><span data-stu-id="8feef-165">Many networks were designed to use a hub and spoke topology.</span></span> <span data-ttu-id="8feef-166">在這個拓撲中，網際網路流量通常會先將 WAN 傳輸至中央資料中心，再 (網際網路) 出口。</span><span class="sxs-lookup"><span data-stu-id="8feef-166">In this topology, internet traffic typically traverses the WAN to a central datacenter before it emerges (egresses) to the internet.</span></span> <span data-ttu-id="8feef-167">通常，這麼做是為了集中網路安全性裝置，以降低整體成本。</span><span class="sxs-lookup"><span data-stu-id="8feef-167">Often, this is done to centralize network security devices with the goal of reducing overall cost.</span></span>

<span data-ttu-id="8feef-168">跨 WAN 的回程流量會增加延遲，並會對品質和使用者體驗造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="8feef-168">Back-hauling traffic across the WAN increases latency and has a negative impact on quality and the user experience.</span></span> <span data-ttu-id="8feef-169">由於 Microsoft Teams 在 Microsoft 的大型全域網路上執行，因此使用者附近通常會有網路對等位置。</span><span class="sxs-lookup"><span data-stu-id="8feef-169">Because Microsoft Teams runs on Microsoft's large global network, there's often a network peering location close to the user.</span></span> <span data-ttu-id="8feef-170">使用者最有可能從靠近其位置的當地網際網路點出口，並儘快進入我們語音優化的網路，以取得更佳的績效。</span><span class="sxs-lookup"><span data-stu-id="8feef-170">A user will most likely get better performance by egressing out of a local internet point close to their location and on to our voice-optimized network as soon as possible.</span></span> <span data-ttu-id="8feef-171">針對某些工作負載，DNS 要求會用來將流量傳送至最近的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="8feef-171">For some workloads, DNS requests are used to send traffic to the nearest front-end server.</span></span> <span data-ttu-id="8feef-172">在這種情況下，使用本地出口點時，必須搭配本地 DNS 解析度。</span><span class="sxs-lookup"><span data-stu-id="8feef-172">In such cases, it's important that when using a local egress point, it's paired with local DNS resolution.</span></span>

<span data-ttu-id="8feef-173">優化 Microsoft 全域網路的網路路徑將會改善績效，並最終為使用者提供最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="8feef-173">Optimizing the network path to Microsoft's global network will improve performance and ultimately provide the best experience for users.</span></span> <span data-ttu-id="8feef-174">詳細資料請參閱部落格文章取得 [Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)的最佳連接和績效。</span><span class="sxs-lookup"><span data-stu-id="8feef-174">For more detail, see the blog post [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

### <a name="vpn"></a><span data-ttu-id="8feef-175">Vpn</span><span class="sxs-lookup"><span data-stu-id="8feef-175">VPN</span></span>

<span data-ttu-id="8feef-176">VPN 為許多組織提供寶貴的服務。</span><span class="sxs-lookup"><span data-stu-id="8feef-176">VPNs provide a valuable service to many organizations.</span></span> <span data-ttu-id="8feef-177">很抱歉，它們通常未設計或配置為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="8feef-177">Unfortunately, they're typically not designed or configured to support real-time media.</span></span> <span data-ttu-id="8feef-178">某些 VPN 可能也不支援 UDP。</span><span class="sxs-lookup"><span data-stu-id="8feef-178">Some VPNs might also not support UDP.</span></span> <span data-ttu-id="8feef-179">VPN 也會在已加密的媒體流量上引入額外的加密層。</span><span class="sxs-lookup"><span data-stu-id="8feef-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span> <span data-ttu-id="8feef-180">此外，由於透過 VPN 裝置釘發的流量，Teams 服務的連接可能沒有效率。</span><span class="sxs-lookup"><span data-stu-id="8feef-180">In addition, connectivity to the Teams service might not be efficient due to hair-pinning traffic through a VPN device.</span></span>
<span data-ttu-id="8feef-181">此外，它們不一定是從容量角度設計，以配合 Teams 需要的預期負載。</span><span class="sxs-lookup"><span data-stu-id="8feef-181">Furthermore, they aren't necessarily designed from a capacity perspective to accommodate the anticipated loads that Teams will require.</span></span>

<span data-ttu-id="8feef-182">建議提供可忽略 Teams 專用 VPN 流量的備用路徑。</span><span class="sxs-lookup"><span data-stu-id="8feef-182">The recommendation is to provide an alternate path that bypasses the VPN for Teams traffic.</span></span> <span data-ttu-id="8feef-183">這通常稱為 *分割線 VPN。*</span><span class="sxs-lookup"><span data-stu-id="8feef-183">This is commonly known as *split-tunnel VPN*.</span></span> <span data-ttu-id="8feef-184">分割管道表示 Microsoft 365 或 Office 365 的流量不會經過 VPN，而是直接前往 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8feef-184">Split tunneling means that traffic for Microsoft 365 or Office 365 won't traverse the VPN but will go directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="8feef-185">這項變更會對品質產生正面影響，但也提供降低 VPN 裝置與組織網路負載的次要優點。</span><span class="sxs-lookup"><span data-stu-id="8feef-185">This change will have a positive impact on quality, but also provides the secondary benefit of reducing load from the VPN devices and the organization's network.</span></span>

<span data-ttu-id="8feef-186">若要執行分割區，請詢問 VPN 廠商的組組詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8feef-186">To implement a split-tunnel, consult with your VPN vendor for the configuration details.</span></span>

### <a name="wi-fi"></a><span data-ttu-id="8feef-187">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8feef-187">Wi-Fi</span></span>

<span data-ttu-id="8feef-188">與 VPN 一Wi-Fi，網路不一定設計或已配置為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="8feef-188">Like VPN, Wi-Fi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="8feef-189">規劃或優化支援 Teams Wi-Fi網路是高品質部署的一項重要考慮。</span><span class="sxs-lookup"><span data-stu-id="8feef-189">Planning for, or optimizing, a Wi-Fi network to support Teams is an important consideration for a high-quality deployment.</span></span>

<span data-ttu-id="8feef-190">有幾個因素可針對優化網路Wi-Fi作用：</span><span class="sxs-lookup"><span data-stu-id="8feef-190">There are several factors that come into play for optimizing a Wi-Fi network:</span></span>

-   <span data-ttu-id="8feef-191">在 WMM Wi-Fi中 (QoS 或) ，以確保媒體流量在網路Wi-Fi優先順序。</span><span class="sxs-lookup"><span data-stu-id="8feef-191">Implementing QoS or Wi-Fi Multimedia (WMM) to ensure that media traffic is getting prioritized accordingly over the Wi-Fi networks.</span></span>

-   <span data-ttu-id="8feef-192">規劃及優化Wi-Fi和存取點位置。</span><span class="sxs-lookup"><span data-stu-id="8feef-192">Planning and optimizing the Wi-Fi bands and access point placement.</span></span> <span data-ttu-id="8feef-193">2.4 GHz 範圍可能會根據訪問點位置提供適當的體驗，但訪問點通常會受到該範圍內運作的其他消費者裝置影響。</span><span class="sxs-lookup"><span data-stu-id="8feef-193">The 2.4 GHz range may provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="8feef-194">5 GHz 範圍較適合即時媒體使用，因為媒體範圍密集，但需要更多存取點才能獲得足夠的覆蓋。</span><span class="sxs-lookup"><span data-stu-id="8feef-194">The 5 GHz range is better suited to real-time media due to their dense range but requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="8feef-195">端點也需要支援該範圍，並據此進行配置以運用這些頻帶。</span><span class="sxs-lookup"><span data-stu-id="8feef-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span>

-   <span data-ttu-id="8feef-196">如果已部署雙Wi-Fi網路，請考慮執行帶式轉向。</span><span class="sxs-lookup"><span data-stu-id="8feef-196">If dual-band Wi-Fi networks are deployed, consider implementing band steering.</span></span> <span data-ttu-id="8feef-197">帶式轉向是一項由Wi-Fi廠商所執行的技術，可影響雙頻用戶端以使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="8feef-197">Band steering is a technique implemented by Wi-Fi vendors to influence dual-band clients to use the 5 GHz range.</span></span>

-   <span data-ttu-id="8feef-198">當同一個通道的存取點太接近時，可能會導致訊號重迭和意外競爭，給使用者造成不良體驗。</span><span class="sxs-lookup"><span data-stu-id="8feef-198">When access points of the same channel are too close together they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="8feef-199">請確保彼此旁邊的訪問點位於不重迭的頻道上。</span><span class="sxs-lookup"><span data-stu-id="8feef-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span>

<span data-ttu-id="8feef-200">每個無線廠商都有自己的無線解決方案部署建議。</span><span class="sxs-lookup"><span data-stu-id="8feef-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="8feef-201">我們建議您向廠商諮詢，以尋求特定指引。</span><span class="sxs-lookup"><span data-stu-id="8feef-201">We recommend that you consult your vendor for specific guidance.</span></span>

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a><span data-ttu-id="8feef-202">防火牆和 Proxy 需求</span><span class="sxs-lookup"><span data-stu-id="8feef-202">Firewall and proxy requirements</span></span>

<span data-ttu-id="8feef-203">Microsoft Teams 會連線到 Microsoft Online Services，因此需要網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="8feef-203">Microsoft Teams connects to Microsoft Online Services and needs internet connectivity for this.</span></span> <span data-ttu-id="8feef-204">若要讓 Teams 正確運作，您必須從用戶端到網際網路開啟 TCP 埠 80 和 443，以及從用戶端到網際網路的 UDP 埠 3478 到 3481。</span><span class="sxs-lookup"><span data-stu-id="8feef-204">For Teams to function correctly, you must open TCP ports 80 and 443 from the clients to the internet, and UDP ports 3478 through 3481 from the clients to the internet.</span></span> <span data-ttu-id="8feef-205">TCP 埠可用來連線至 Web 內容，例如 SharePoint Online、Exchange Online 和 Teams 聊天服務。</span><span class="sxs-lookup"><span data-stu-id="8feef-205">The TCP ports are used to connect to web-based content such as SharePoint Online, Exchange Online, and the Teams Chat services.</span></span>
<span data-ttu-id="8feef-206">外掛程式和連接器也會在這些 TCP 埠上連接。</span><span class="sxs-lookup"><span data-stu-id="8feef-206">Plug-ins and connectors also connect over these TCP ports.</span></span> <span data-ttu-id="8feef-207">這四個 UDP 埠用於音訊和視像等媒體，以確保它們能夠正確流動。</span><span class="sxs-lookup"><span data-stu-id="8feef-207">The four UDP ports are used for media such as audio and video, to ensure they flow correctly.</span></span>

<span data-ttu-id="8feef-208">開啟這些埠對於可靠的 Teams 部署至關重要。</span><span class="sxs-lookup"><span data-stu-id="8feef-208">Opening these ports is essential for a reliable Teams deployment.</span></span> <span data-ttu-id="8feef-209">封鎖這些埠不受支援，且會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="8feef-209">Blocking these ports is unsupported and will have an effect on media quality.</span></span>

<span data-ttu-id="8feef-210">如果貴組織要求您指定應開啟這些埠的確切 IP 位址範圍和網域，您可以限制這些埠的目標 IP 範圍和網域。</span><span class="sxs-lookup"><span data-stu-id="8feef-210">If your organization requires that you specify the exact IP address ranges and domains to which these ports should be opened, you can restrict the target IP ranges and domains for these ports.</span></span> <span data-ttu-id="8feef-211">有關確切的埠、通訊協定和 IP 範圍清單，請參閱 [Microsoft 365 或 Office 365 URL 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。</span><span class="sxs-lookup"><span data-stu-id="8feef-211">For a list of exact ports, protocols, and IP ranges, see [Microsoft 365 or Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).</span></span>
<span data-ttu-id="8feef-212">如果您選擇限制目標 IP 位址範圍和網域，您必須確保埠和範圍清單保持在最新狀態，因為它們可能會變更。</span><span class="sxs-lookup"><span data-stu-id="8feef-212">If you choose to restrict the target IP address ranges and domains, you must ensure that you keep the list of ports and ranges up to date because they might change.</span></span> <span data-ttu-id="8feef-213">您可以訂閱此 [RSS 提](https://go.microsoft.com/fwlink/p/?linkid=236301) 要，以在變更發生時進行更新。</span><span class="sxs-lookup"><span data-stu-id="8feef-213">You can subscribe to [this RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) to be updated when changes occur.</span></span> <span data-ttu-id="8feef-214">定期執行商務用 [Skype](https://www.microsoft.com/download/details.aspx?id=53885) 網路評定工具，也是測試所有埠是否開啟的一個好作法。</span><span class="sxs-lookup"><span data-stu-id="8feef-214">It's also a good practice to test whether all ports are opened by running the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) on a regular basis.</span></span> <span data-ttu-id="8feef-215">您可以在下一節中進一步瞭解此工具的功能。</span><span class="sxs-lookup"><span data-stu-id="8feef-215">You can find out more about the functionality of this tool in the next section.</span></span>

<span data-ttu-id="8feef-216">如果部署 Proxy 伺服器，建議您忽略所有 Teams 服務的 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8feef-216">In the event of a proxy server being deployed, we recommend that you bypass the proxy server for all Teams services.</span></span> <span data-ttu-id="8feef-217">雖然使用 Proxy 可能可以，但由於媒體強制使用 TCP 而非 UDP，因此品質很可能會降低。</span><span class="sxs-lookup"><span data-stu-id="8feef-217">Although using a proxy might work, it's very likely that quality will be reduced due to media being forced to use TCP instead of UDP.</span></span> <span data-ttu-id="8feef-218">有關 Proxy 伺服器和旁路詳細資訊，請參閱 [Microsoft 365 或 Office 365 URL 和 IP 位址範圍](./office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="8feef-218">For more information about proxy servers and bypassing, see [Microsoft 365 or Office 365 URLs and IP address ranges](./office-365-urls-ip-address-ranges.md).</span></span>

<!--ENDOFSECTION-->

## <a name="test-the-network"></a><span data-ttu-id="8feef-219">測試網路</span><span class="sxs-lookup"><span data-stu-id="8feef-219">Test the network</span></span>

<span data-ttu-id="8feef-220">完成規劃與網路準備之後 ，包括升級頻寬和在防火牆中開啟埠，您應該測試您的網路績效。</span><span class="sxs-lookup"><span data-stu-id="8feef-220">After you've completed your planning and network preparation—including upgrading bandwidth and opening ports in the firewall—you should test your network's performance.</span></span> <span data-ttu-id="8feef-221">此測試的結果會更清楚地說明音訊會議或電話系統與通話方案實施成功所需的任何網路優化或補救。</span><span class="sxs-lookup"><span data-stu-id="8feef-221">The results of this testing will paint a clearer picture of any network optimization or remediation required for the success of your Audio Conferencing or Phone System with Calling Plan implementation.</span></span>

<span data-ttu-id="8feef-222">您可以下載 [商務用 Skype 網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) ，以測試您的網路是否已準備好供 Teams 使用。</span><span class="sxs-lookup"><span data-stu-id="8feef-222">You can download the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span> <span data-ttu-id="8feef-223">此工具提供雙重功能：它可以測試是否已開啟所有正確的埠，也可以測試網路受損。</span><span class="sxs-lookup"><span data-stu-id="8feef-223">The tool offers dual functionality: it can test whether all the correct ports have been opened, and it can test for network impairments.</span></span>

<span data-ttu-id="8feef-224">下載並安裝工具之後，您可以在 C：程式檔案 Microsoft \\ \\ 商務用 Skype 網路評定工具找到它。</span><span class="sxs-lookup"><span data-stu-id="8feef-224">After you download and install the tool, you can find it in C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool.</span></span> <span data-ttu-id="8feef-225">該目錄中包含如何使用工具的詳細指南 ，Usage.docx指南。</span><span class="sxs-lookup"><span data-stu-id="8feef-225">A detailed guide for how to use the tool, Usage.docx, is included in that directory.</span></span>

### <a name="test-for-opened-ports"></a><span data-ttu-id="8feef-226">測試開啟的埠</span><span class="sxs-lookup"><span data-stu-id="8feef-226">Test for opened ports</span></span>

<span data-ttu-id="8feef-227">開啟命令提示視窗，然後輸入 cd C 流覽至網路評定工具目錄：程式檔案 Microsoft 商務用 **\\ Skype \\ 網路評定工具**。</span><span class="sxs-lookup"><span data-stu-id="8feef-227">Open a Command prompt window and navigate to the Network Assessment Tool directory by entering **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool**.</span></span> <span data-ttu-id="8feef-228">在命令提示符中，輸入 **/connectivitychecknetworkassessmenttool.exe開啟的埠測試**</span><span class="sxs-lookup"><span data-stu-id="8feef-228">At the command prompt, start the test for opened ports by entering **networkassessmenttool.exe /connectivitycheck**</span></span>

<span data-ttu-id="8feef-229">執行檢查之後，工具會顯示「驗證已成功完成」訊息，或是在封鎖的埠上報告。</span><span class="sxs-lookup"><span data-stu-id="8feef-229">After running the checks, the tool will either display the message "Verifications Completed Successfully" or report on the ports that were blocked.</span></span>
<span data-ttu-id="8feef-230">它也會產生名為 Connectivity_results.txt 的檔案，其中包含工具的輸出，並儲存在 %userprofile% appdata 本地商務用 \\ Microsoft \\ Skype 網路評定工具 \\ \\ 目錄中。</span><span class="sxs-lookup"><span data-stu-id="8feef-230">It also generates a file named Connectivity_results.txt, which contains the output from the tool and stores it in the %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\ directory.</span></span>

<span data-ttu-id="8feef-231">我們建議您定期執行連接檢查，以確保埠已開啟且運作正常。</span><span class="sxs-lookup"><span data-stu-id="8feef-231">We recommend that you run the connectivity checks on a regular basis to ensure the ports have been opened and are functioning correctly.</span></span>

### <a name="test-for-network-impairments"></a><span data-ttu-id="8feef-232">測試網路障礙</span><span class="sxs-lookup"><span data-stu-id="8feef-232">Test for network impairments</span></span>

<span data-ttu-id="8feef-233">若要提高使用者滿意度，您應該限制網路上任何障礙。</span><span class="sxs-lookup"><span data-stu-id="8feef-233">To increase user satisfaction, you should limit any impairments on your network.</span></span>
<span data-ttu-id="8feef-234">最常見的網路障礙是延遲 (延遲) 封包遺失和抖動：</span><span class="sxs-lookup"><span data-stu-id="8feef-234">The most common network impairments are delay (latency), packet loss, and jitter:</span></span>

-   <span data-ttu-id="8feef-235">**延遲：** 這是從 A 點到網路 B 點取得 IP 封包所花的時間。</span><span class="sxs-lookup"><span data-stu-id="8feef-235">**Latency:** This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="8feef-236">此網路傳播延遲基本上與兩點之間的實際距離和光速有關，包括介於兩者之間的各種路由器所增加的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="8feef-236">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span>
    <span data-ttu-id="8feef-237">延遲是以單向或往返時間來測量。</span><span class="sxs-lookup"><span data-stu-id="8feef-237">Latency is measured as one-way or round-trip time.</span></span>

-   <span data-ttu-id="8feef-238">**封包** 遺失：這通常定義為在給定時段內遺失的封包百分比。</span><span class="sxs-lookup"><span data-stu-id="8feef-238">**Packet loss**: This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="8feef-239">封包遺失會直接影響音訊品質，從小型、個別遺失的封包幾乎不會影響到背對背的斷流遺失，導致音訊完全中斷。</span><span class="sxs-lookup"><span data-stu-id="8feef-239">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>

-   <span data-ttu-id="8feef-240">**封包間到達的抖動，或只是抖動：** 這是連續封包之間延遲的平均變化。</span><span class="sxs-lookup"><span data-stu-id="8feef-240">**Inter-packet arrival jitter, or simply jitter:** This is the average change in delay between successive packets.</span></span> <span data-ttu-id="8feef-241">大部分的新式 VoIP 軟體 ，包括商務用 Skype，都可以透過緩衝來適應某些層級的抖動。</span><span class="sxs-lookup"><span data-stu-id="8feef-241">Most modern VoIP software, including Skype for Business, can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="8feef-242">只有當抖動超過緩衝時，參與者才能注意到抖動的影響。</span><span class="sxs-lookup"><span data-stu-id="8feef-242">It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.</span></span>

<span data-ttu-id="8feef-243">這些障礙的最大值會以 [媒體質量和](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)網路連接能力描述。</span><span class="sxs-lookup"><span data-stu-id="8feef-243">The maximum values for these impairments are described in [Media quality and network connectivity performance](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>
<span data-ttu-id="8feef-244">針對這些障礙進行測試時，我們會區分兩個不同的區段：</span><span class="sxs-lookup"><span data-stu-id="8feef-244">When testing for these impairments, we distinguish between two separate segments:</span></span>

-   <span data-ttu-id="8feef-245">邊緣 *區段* 是路由器所生活的區段。</span><span class="sxs-lookup"><span data-stu-id="8feef-245">The *edge segment* is the segment in which your router lives.</span></span> <span data-ttu-id="8feef-246">這是您每個位置連接網際網路的最接近邏輯網路區段。</span><span class="sxs-lookup"><span data-stu-id="8feef-246">This is the closest logical network segment connected to the internet at each of your locations.</span></span> <span data-ttu-id="8feef-247">在大多數情況下，這是路由器的連接點，或可能是周邊網路 (也稱為 *DMZ、* 非軍事區和已篩選的子網) 。  </span><span class="sxs-lookup"><span data-stu-id="8feef-247">In most cases, this is the connection point of the router, or possibly a perimeter network (also known as *DMZ*, *demilitarized zone*, and *screened subnet*).</span></span> <span data-ttu-id="8feef-248">此區段與網際網路之間不應發生其他影響路由器外裝置的流量。</span><span class="sxs-lookup"><span data-stu-id="8feef-248">No further traffic that affects devices other than the router should occur between this segment and the internet.</span></span>

-   <span data-ttu-id="8feef-249">用戶端 *區段* 是用戶端所在的邏輯網路區段。</span><span class="sxs-lookup"><span data-stu-id="8feef-249">The *client segment* is the logical network segment in which your clients reside.</span></span>

<span data-ttu-id="8feef-250">您應該使用網路評定工具來測試這兩個區段。</span><span class="sxs-lookup"><span data-stu-id="8feef-250">You should test both segments by using the Network Assessment Tool.</span></span> <span data-ttu-id="8feef-251">若要測試區段，請流覽至目錄，networkassessmenttool.exe提示 **符** 輸入資料。</span><span class="sxs-lookup"><span data-stu-id="8feef-251">To test the segment, navigate to the directory and enter **networkassessmenttool.exe** at the command prompt.</span></span> <span data-ttu-id="8feef-252">結果會寫入名為 Results.tsv 的檔案，您可以將結果與 [每個區段](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 的需求進行比較。</span><span class="sxs-lookup"><span data-stu-id="8feef-252">The results are written to a file named Results.tsv, and you can compare them to the [requirements](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) for each segment.</span></span>

<span data-ttu-id="8feef-253">請注意，這兩個區段必須符合高品質部署的需求。</span><span class="sxs-lookup"><span data-stu-id="8feef-253">Note that both segments must meet the requirements for a high-quality deployment.</span></span> <span data-ttu-id="8feef-254">我們建議您直接執行工具多次一小時，以取得網路良好表現的指示。</span><span class="sxs-lookup"><span data-stu-id="8feef-254">We recommend that you run the tool multiple times for one hour straight to get a good indication of your network's performance.</span></span>

<!--ENDOFSECTION-->

## <a name="network-remediation"></a><span data-ttu-id="8feef-255">網路修復</span><span class="sxs-lookup"><span data-stu-id="8feef-255">Network remediation</span></span>

<span data-ttu-id="8feef-256">如果頻寬規劃、埠測試或網路需求測試結果顯示，您目前的網路需要修復才能部署 Teams，您可以用多種方式完成此工作：</span><span class="sxs-lookup"><span data-stu-id="8feef-256">If the results of bandwidth planning, port testing, or network requirements testing show that your current network needs remediation before you deploy Teams, you can accomplish this in several ways:</span></span>

-   <span data-ttu-id="8feef-257">如果頻寬不足，請升級連接，讓 Microsoft 365 或 Office 365 的流量不受阻礙。</span><span class="sxs-lookup"><span data-stu-id="8feef-257">For insufficient bandwidth, upgrade connections so that traffic to Microsoft 365 or Office 365 can flow unhindered.</span></span>

-   <span data-ttu-id="8feef-258">針對封鎖的埠，變更防火牆規則，然後重新測試埠。</span><span class="sxs-lookup"><span data-stu-id="8feef-258">For blocked ports, change firewall rules and retest the ports.</span></span>

-   <span data-ttu-id="8feef-259">針對網路障礙，請一直執行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="8feef-259">For network impairments, always perform a root-cause analysis.</span></span>

<span data-ttu-id="8feef-260">QoS (服務品質) 優先處理和分隔流量，以與障礙進行較量。</span><span class="sxs-lookup"><span data-stu-id="8feef-260">Quality of service (QoS) can be used to battle impairments by prioritizing and separating traffic.</span></span> <span data-ttu-id="8feef-261">有些組織選擇部署 QoS 以克服頻寬問題或限制流量流量。</span><span class="sxs-lookup"><span data-stu-id="8feef-261">Some organizations choose to deploy QoS to overcome bandwidth issues or restrict the amount of traffic flowing.</span></span> <span data-ttu-id="8feef-262">這無法改善品質，並會導致新的問題。</span><span class="sxs-lookup"><span data-stu-id="8feef-262">This won't improve quality and will lead to new problems.</span></span> <span data-ttu-id="8feef-263">當網路受損超過需求時，應一直執行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="8feef-263">A root-cause analysis should always be performed when network impairments exceed requirements.</span></span> <span data-ttu-id="8feef-264">QoS 可以是解決方案。</span><span class="sxs-lookup"><span data-stu-id="8feef-264">QoS can be a solution.</span></span>
<span data-ttu-id="8feef-265">詳細資訊，請參閱 [Microsoft Teams 中的服務品質](./qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8feef-265">For more information, see [Quality of Service in Microsoft Teams](./qos-in-teams.md).</span></span>

>[!NOTE]
><span data-ttu-id="8feef-266">由於升級、擴充或其他商務需求，許多網路會隨著時間而演進。</span><span class="sxs-lookup"><span data-stu-id="8feef-266">Many networks evolve over time due to upgrades, expansion, or other business requirements.</span></span> <span data-ttu-id="8feef-267">在服務管理規劃中，請確保您擁有維護這些區域的操作程式。</span><span class="sxs-lookup"><span data-stu-id="8feef-267">Ensure that you have operational processes in place to maintain these areas as part of your service management planning.</span></span>


<table>
<tr><td><span data-ttu-id="8feef-268">標題</span><span class="sxs-lookup"><span data-stu-id="8feef-268">Title</span></span></td><td><span data-ttu-id="8feef-269">描述</span><span class="sxs-lookup"><span data-stu-id="8feef-269">Description</span></span></td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="8feef-270">決策點</span><span class="sxs-lookup"><span data-stu-id="8feef-270">Decision points</span></span></td><td><ul><li><span data-ttu-id="8feef-271">誰負責完成所有網路區段和組織位置的適當網路評定？</span><span class="sxs-lookup"><span data-stu-id="8feef-271">Who will be responsible for completing proper network assessments across all network segments and organization locations?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="8feef-272">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8feef-272">Next steps</span></span></td><td><ul><li><span data-ttu-id="8feef-273">您可以執行詳細的網路評估，協助確保您的網路準備好進行 Microsoft Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="8feef-273">You can perform a detailed network assessment to help ensure your network is ready for your Microsoft Teams deployment.</span></span></li><li><span data-ttu-id="8feef-274">根據每個網路區段的評估結果執行網路補救。</span><span class="sxs-lookup"><span data-stu-id="8feef-274">Perform network remediation based on the results of the assessment for every network segment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->