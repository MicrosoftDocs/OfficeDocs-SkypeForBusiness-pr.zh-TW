---
title: 針對雲端語音工作負載評估您的環境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和網路分析來評估貴組織的就緒性，開啟正確的 TCP 和 UDP 埠，然後執行任何網路修正。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 698d63f0d53119569f6b212fa7db7a16c827f571
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610055"
---
# <a name="evaluate-my-environment"></a><span data-ttu-id="72b5b-103">評估我的環境</span><span class="sxs-lookup"><span data-stu-id="72b5b-103">Evaluate my environment</span></span>

<span data-ttu-id="72b5b-104">本文概述針對使用雲端語音服務來正確評估目前環境的需求。</span><span class="sxs-lookup"><span data-stu-id="72b5b-104">This article gives an overview of the requirements for properly evaluating your current environment for using cloud voice services.</span></span> <span data-ttu-id="72b5b-105">您可以評估您的環境，找出會影響整體雲端語音部署的風險與需求。</span><span class="sxs-lookup"><span data-stu-id="72b5b-105">By evaluating your environment, you identify risks and requirements that will influence your overall cloud voice deployment.</span></span> <span data-ttu-id="72b5b-106">透過預先識別這些專案，您可以調整您的規劃來促進成功。</span><span class="sxs-lookup"><span data-stu-id="72b5b-106">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-evaluating-your-environment"></a><span data-ttu-id="72b5b-107">評估您的環境簡介</span><span class="sxs-lookup"><span data-stu-id="72b5b-107">Introduction to evaluating your environment</span></span> 

<span data-ttu-id="72b5b-108">為了達到您的目標金鑰結果（OKRs），您先前已進行重要的服務決策。</span><span class="sxs-lookup"><span data-stu-id="72b5b-108">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="72b5b-109">下一步是執行環保探索，以評估與您 IT 和電話結構、網路及作業相關的所有方面，以確認貴組織已準備好要實施方案。</span><span class="sxs-lookup"><span data-stu-id="72b5b-109">The next step is to perform environmental discovery to evaluate all aspects relating to your IT and telephony infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span>

<span data-ttu-id="72b5b-110">環境探索必須包含網路就緒評估，以確保您的網路可支援使用通話方案服務來實現音訊會議或電話系統。</span><span class="sxs-lookup"><span data-stu-id="72b5b-110">Environmental discovery must include network readiness assessment to ensure your network can support the implementation of the Audio Conferencing or Phone System with Calling Plan services.</span></span>

<span data-ttu-id="72b5b-111">您可以在環境評估與採納準備情況評估中識別技術風險，並針對每個已識別的風險開發緩解方案。</span><span class="sxs-lookup"><span data-stu-id="72b5b-111">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span>
<span data-ttu-id="72b5b-112">您應該將此資訊納入風險登記簿中。</span><span class="sxs-lookup"><span data-stu-id="72b5b-112">You should incorporate this information in the risk register.</span></span>

<!--ENDOFSECTION-->

## <a name="current-environment"></a><span data-ttu-id="72b5b-113">目前環境</span><span class="sxs-lookup"><span data-stu-id="72b5b-113">Current environment</span></span>

<span data-ttu-id="72b5b-114">在您的環境探索中，包括與使用者計算有關的所有相關事項，例如電腦和行動裝置的準備情況評估，以支援音訊會議和電話系統規劃商務使用案例（從硬體需求到軟體需求）。</span><span class="sxs-lookup"><span data-stu-id="72b5b-114">As part of your environmental discovery, include all matters related to end-user computing, such as a readiness assessment of PCs and mobile devices to support Audio Conferencing and Phone System with Calling Plan business use cases, from hardware requirements to software requirements.</span></span>

<span data-ttu-id="72b5b-115">環境探索也可以揭示您是否需要將[電話號碼傳送給 Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="72b5b-115">Environmental discovery can also uncover whether you need to [transfer phone numbers to Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
<span data-ttu-id="72b5b-116">瞭解這將會協助您的組織調整其專案計劃，並準備數位移植所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="72b5b-116">Knowing this will help your organization adjust its project plan accordingly and prepare the necessary information for number porting.</span></span> <span data-ttu-id="72b5b-117">您可以使用[Microsoft 團隊推出的環境探索](environmental-discovery-for-microsoft-teams-rollout.md)來執行環境探索。</span><span class="sxs-lookup"><span data-stu-id="72b5b-117">You can use the [Environmental discovery for Microsoft Teams rollout](environmental-discovery-for-microsoft-teams-rollout.md) to perform environmental discovery.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="72b5b-118">決策點</span><span class="sxs-lookup"><span data-stu-id="72b5b-118">Decision points</span></span></td><td><ul><li><span data-ttu-id="72b5b-119">誰負責完成環境評估？</span><span class="sxs-lookup"><span data-stu-id="72b5b-119">Who will be responsible for completing an environment assessment?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="72b5b-120">後續步驟</span><span class="sxs-lookup"><span data-stu-id="72b5b-120">Next steps</span></span></td><td><ul><li><span data-ttu-id="72b5b-121">記錄環境評估的結果。</span><span class="sxs-lookup"><span data-stu-id="72b5b-121">Document the results of the environment assessment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a><span data-ttu-id="72b5b-122">採納與變更管理評估功能</span><span class="sxs-lookup"><span data-stu-id="72b5b-122">Adoption and change management assessment capabilities</span></span> 

<span data-ttu-id="72b5b-123">部署在使用者的使用中提供了新的技術，但商務結果只會在使用者真正採用該方案本身之後才會實現。</span><span class="sxs-lookup"><span data-stu-id="72b5b-123">Deployment puts a new technology at a user's fingertips, but business results are only realized after users truly adopt that solution as their own.</span></span> <span data-ttu-id="72b5b-124">為了協助確保持續採用新的解決方案，您必須將精力集中在使用者就緒性與變更管理上。</span><span class="sxs-lookup"><span data-stu-id="72b5b-124">To help ensure sustained adoption of a new solution, you'll need to focus your efforts on user readiness and change management.</span></span> <span data-ttu-id="72b5b-125">若要取得最佳結果，請執行使用者準備規劃，做為您的技術準備活動的並行工作流，並納入下列活動：</span><span class="sxs-lookup"><span data-stu-id="72b5b-125">For optimal results, conduct user readiness planning as a parallel workstream to your technical readiness activities and incorporate the following activities:</span></span>

-   <span data-ttu-id="72b5b-126">**組織與使用者的分析：** 除了使用案例與角色分析之外，還能分析組織 receptiveness 變更</span><span class="sxs-lookup"><span data-stu-id="72b5b-126">**Organizational and user profiling:** Analysis of organizational receptiveness to change in addition to use case and persona analysis</span></span>

-   <span data-ttu-id="72b5b-127">**準備就緒與資源準備：** 建立具有針對性和廣泛認識、訓練及支援資源的功能，包括焦點價值訊息，以加速使用者購買</span><span class="sxs-lookup"><span data-stu-id="72b5b-127">**Readiness and resource preparation:** Creation of targeted and broad-reach awareness, training, and support resources, including focused value messaging to accelerate user buy-in</span></span>

<span data-ttu-id="72b5b-128">使用下列考慮來評估貴組織的準備工作，以解決使用者變更管理問題。</span><span class="sxs-lookup"><span data-stu-id="72b5b-128">Use the following considerations to assess your organization's preparedness to address user change management.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="72b5b-129">決策點</span><span class="sxs-lookup"><span data-stu-id="72b5b-129">Decision points</span></span></td><td><ul><li><span data-ttu-id="72b5b-130">您是否曾在使用者採用軟體或服務之前取得成功？</span><span class="sxs-lookup"><span data-stu-id="72b5b-130">Have you had previous success with user adoption of software or services?</span></span></li><li><span data-ttu-id="72b5b-131">您可以追蹤使用 uptake 嗎？</span><span class="sxs-lookup"><span data-stu-id="72b5b-131">Can you track usage uptake?</span></span></li><li><span data-ttu-id="72b5b-132">您是否擁有設計及管理初始 &mdash; 和持續進行的 &mdash; 採納活動（認識、訓練及支援）的資源？</span><span class="sxs-lookup"><span data-stu-id="72b5b-132">Do you have the resources to design and manage an initial&mdash;and ongoing&mdash;adoption campaign (awareness, training, and support)?</span></span></li><li><span data-ttu-id="72b5b-133">您是否擁有專用的使用者採用/變更管理小組，或是您是否可以投資這些資源以確保商業結果？</span><span class="sxs-lookup"><span data-stu-id="72b5b-133">Do you have a dedicated user adoption/change management team, or can you invest in those resources to ensure business outcomes?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="72b5b-134">後續步驟</span><span class="sxs-lookup"><span data-stu-id="72b5b-134">Next steps</span></span></td><td><ul><li><span data-ttu-id="72b5b-135">如果您 &quot; 對上述所有專案回答 [是] &quot; ，請找出適當的使用者變更管理專案關係人，並開始進行您的使用者準備規劃。</span><span class="sxs-lookup"><span data-stu-id="72b5b-135">If you answered &quot;yes&quot; to all of the above, identify the right user change management stakeholders and begin your user readiness planning.</span></span></li><li><span data-ttu-id="72b5b-136">如果您回答「 &quot; 不 &quot; 是」的部分或全部，請考慮使用外部資源來協助您的組織進行變更管理與採納相關活動。</span><span class="sxs-lookup"><span data-stu-id="72b5b-136">If you answered &quot;no&quot; to some or all of the above, consider engaging outside resources to assist with driving change management and adoption-related activities for your organization.</span></span></li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a><span data-ttu-id="72b5b-137">網路就緒</span><span class="sxs-lookup"><span data-stu-id="72b5b-137">Network readiness</span></span>

<span data-ttu-id="72b5b-138">團隊使用可適應的音訊和視頻技術（編解碼器），因此在大多數網路條件下都能更好地執行。</span><span class="sxs-lookup"><span data-stu-id="72b5b-138">Teams uses audio and video technology (codecs) that can adapt to—and therefore perform better under—most network conditions.</span></span> <span data-ttu-id="72b5b-139">為確保最佳且一致的效能，您應該為小組準備好您的網路。</span><span class="sxs-lookup"><span data-stu-id="72b5b-139">To ensure optimal and consistent performance, you should prepare your network for Teams.</span></span>

<span data-ttu-id="72b5b-140">![描述三個品質元件的圖表](media/evaluate-my-environment-image1.png "描述三個品質元件的圖表，以及服務管理如何與所有三個元件重迭。焦點放在網路上。")</span><span class="sxs-lookup"><span data-stu-id="72b5b-140">![Diagram describing the three components of quality](media/evaluate-my-environment-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on the network.")</span></span>

## <a name="key-takeaways"></a><span data-ttu-id="72b5b-141">主要優點</span><span class="sxs-lookup"><span data-stu-id="72b5b-141">Key takeaways</span></span>

<span data-ttu-id="72b5b-142">這些是本指南的主要優點。</span><span class="sxs-lookup"><span data-stu-id="72b5b-142">These are the main takeaways from this guidance.</span></span> <span data-ttu-id="72b5b-143">您必須：</span><span class="sxs-lookup"><span data-stu-id="72b5b-143">You must:</span></span>

-   <span data-ttu-id="72b5b-144">開啟從將使用團隊之用戶端傳出的 TCP 埠80和443。</span><span class="sxs-lookup"><span data-stu-id="72b5b-144">Open TCP ports 80 and 443 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="72b5b-145">從將使用團隊的用戶端向外開啟 UDP 埠3478到3481。</span><span class="sxs-lookup"><span data-stu-id="72b5b-145">Open UDP ports 3478 through 3481 outgoing from clients that will use Teams.</span></span>

-   <span data-ttu-id="72b5b-146">確定您有足夠的頻寬可用於部署團隊。</span><span class="sxs-lookup"><span data-stu-id="72b5b-146">Ensure that you have sufficient bandwidth for deploying Teams.</span></span>

-   <span data-ttu-id="72b5b-147">執行 [[網路評](https://www.microsoft.com/download/details.aspx?id=53885)量] 工具，並確保符合從邊緣區段和用戶端區段的[媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的需求。</span><span class="sxs-lookup"><span data-stu-id="72b5b-147">Run the [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) and ensure that you meet the requirements described in [Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) from both the edge segment and the client segment.</span></span>

## <a name="why-should-you-prepare-your-network"></a><span data-ttu-id="72b5b-148">為什麼應該準備網路？</span><span class="sxs-lookup"><span data-stu-id="72b5b-148">Why should you prepare your network?</span></span>

<span data-ttu-id="72b5b-149">在我們開始查看要採取的步驟之前，請務必瞭解可能會影響團隊效能的專案，進而讓使用者的幸福與滿意。</span><span class="sxs-lookup"><span data-stu-id="72b5b-149">Before we look at the steps to be taken, it's important to understand what can affect the performance of Teams and thereby user happiness and satisfaction.</span></span>
<span data-ttu-id="72b5b-150">三個主要的風險區域會影響使用者如何感覺網路品質：</span><span class="sxs-lookup"><span data-stu-id="72b5b-150">Three major risk areas can affect how users perceive network quality:</span></span>

-   <span data-ttu-id="72b5b-151">沒有足夠的頻寬</span><span class="sxs-lookup"><span data-stu-id="72b5b-151">Insufficient bandwidth available</span></span>

-   <span data-ttu-id="72b5b-152">防火牆與 proxy 攔截程式</span><span class="sxs-lookup"><span data-stu-id="72b5b-152">Firewall and proxy blockers</span></span>

-   <span data-ttu-id="72b5b-153">網路障礙，例如抖動和資料包遺失</span><span class="sxs-lookup"><span data-stu-id="72b5b-153">Network impairments such as jitter and packet loss</span></span>

<span data-ttu-id="72b5b-154">下面所述的步驟可協助您判斷您的部署是否可能受到這些因素的影響，並將協助您移至解決方法。</span><span class="sxs-lookup"><span data-stu-id="72b5b-154">The steps described below will help you determine whether your deployment might be affected by any of these factors and will help you move toward a resolution.</span></span>
<span data-ttu-id="72b5b-155">無法準備您的網路，可能會導致不滿意的使用者，以及大量、較高的臨時修正程式。</span><span class="sxs-lookup"><span data-stu-id="72b5b-155">Failing to prepare your network will likely lead to dissatisfied users and costly, ad-hoc fixes.</span></span> <span data-ttu-id="72b5b-156">透過為小組準備您的網路和您的組織，您就能極大地增加成功的機率。</span><span class="sxs-lookup"><span data-stu-id="72b5b-156">By preparing your network—and your organization—for Teams, you can dramatically increase your chance of success.</span></span>

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a><span data-ttu-id="72b5b-157">頻寬規劃</span><span class="sxs-lookup"><span data-stu-id="72b5b-157">Bandwidth planning</span></span>

<span data-ttu-id="72b5b-158">網路準備就緒的第一個步驟是確保您的網路有足夠的頻寬可供形式小組提供給使用者使用。</span><span class="sxs-lookup"><span data-stu-id="72b5b-158">The first step toward network readiness is ensuring your network has enough bandwidth available for the modalities Teams will provide to users.</span></span> <span data-ttu-id="72b5b-159">規劃足夠的頻寬是相當簡單的工作，而且是一個非常低的障礙開始，以確保您的使用者具備高品質的團隊體驗。</span><span class="sxs-lookup"><span data-stu-id="72b5b-159">Planning for sufficient bandwidth is a fairly straightforward task and a very low-barrier start to ensure your users will have a high-quality Teams experience.</span></span>

### <a name="local-internet-egress"></a><span data-ttu-id="72b5b-160">本機網際網路出口</span><span class="sxs-lookup"><span data-stu-id="72b5b-160">Local internet egress</span></span>

<span data-ttu-id="72b5b-161">許多網路都是用來使用中樞與輪輻拓朴的設計。</span><span class="sxs-lookup"><span data-stu-id="72b5b-161">Many networks were designed to use a hub and spoke topology.</span></span> <span data-ttu-id="72b5b-162">在此拓朴中，網際網路流量通常會在 WAN （egresses）到網際網路前，先將 WAN 移到中央資料中心。</span><span class="sxs-lookup"><span data-stu-id="72b5b-162">In this topology, internet traffic typically traverses the WAN to a central datacenter before it emerges (egresses) to the internet.</span></span> <span data-ttu-id="72b5b-163">通常，這是為了將網路安全裝置集中化以減少總成本的目的。</span><span class="sxs-lookup"><span data-stu-id="72b5b-163">Often, this is done to centralize network security devices with the goal of reducing overall cost.</span></span>

<span data-ttu-id="72b5b-164">跨 WAN 的 hauling 流量會增加延遲，並對品質和使用者體驗造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="72b5b-164">Back-hauling traffic across the WAN increases latency and has a negative impact on quality and the user experience.</span></span> <span data-ttu-id="72b5b-165">因為 Microsoft 團隊是在 Microsoft 大型全域網路上執行，所以通常會有網路對等位置靠近使用者。</span><span class="sxs-lookup"><span data-stu-id="72b5b-165">Because Microsoft Teams runs on Microsoft's large global network, there's often a network peering location close to the user.</span></span> <span data-ttu-id="72b5b-166">使用者最有可能獲得較佳的效能，只要從當地的網際網路點 egressing 到他們的位置，並儘快將它移到我們的語音優化網路上。</span><span class="sxs-lookup"><span data-stu-id="72b5b-166">A user will most likely get better performance by egressing out of a local internet point close to their location and on to our voice-optimized network as soon as possible.</span></span> <span data-ttu-id="72b5b-167">針對某些工作負荷，DNS 要求是用來傳送流量到最接近的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="72b5b-167">For some workloads, DNS requests are used to send traffic to the nearest front-end server.</span></span> <span data-ttu-id="72b5b-168">在這種情況下，請務必注意，當您使用本機的出局點時，它會與本機 DNS 解析搭配使用。</span><span class="sxs-lookup"><span data-stu-id="72b5b-168">In such cases, it's important that when using a local egress point, it's paired with local DNS resolution.</span></span>

<span data-ttu-id="72b5b-169">將網路路徑優化至 Microsoft 的全域網路可改善效能，並最終為使用者提供最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="72b5b-169">Optimizing the network path to Microsoft's global network will improve performance and ultimately provide the best experience for users.</span></span> <span data-ttu-id="72b5b-170">如需詳細資訊，請參閱在[Office 365 中取得最佳連線和效能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)的博客文章。</span><span class="sxs-lookup"><span data-stu-id="72b5b-170">For more detail, see the blog post [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

### <a name="vpn"></a><span data-ttu-id="72b5b-171">點對點</span><span class="sxs-lookup"><span data-stu-id="72b5b-171">VPN</span></span>

<span data-ttu-id="72b5b-172">Vpn 為許多組織提供重要的服務。</span><span class="sxs-lookup"><span data-stu-id="72b5b-172">VPNs provide a valuable service to many organizations.</span></span> <span data-ttu-id="72b5b-173">遺憾的是，它們通常不是專為支援即時媒體而設計或設定。</span><span class="sxs-lookup"><span data-stu-id="72b5b-173">Unfortunately, they're typically not designed or configured to support real-time media.</span></span> <span data-ttu-id="72b5b-174">某些 Vpn 可能也不支援 UDP。</span><span class="sxs-lookup"><span data-stu-id="72b5b-174">Some VPNs might also not support UDP.</span></span> <span data-ttu-id="72b5b-175">Vpn 也會在已加密的媒體流量上方引入額外的加密層級。</span><span class="sxs-lookup"><span data-stu-id="72b5b-175">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span> <span data-ttu-id="72b5b-176">此外，由於將流量釘選到 VPN 裝置，因此小組服務的連線可能無法有效。</span><span class="sxs-lookup"><span data-stu-id="72b5b-176">In addition, connectivity to the Teams service might not be efficient due to hair-pinning traffic through a VPN device.</span></span>
<span data-ttu-id="72b5b-177">此外，它們不一定是從容量角度設計來容納小組將需要的預期負載。</span><span class="sxs-lookup"><span data-stu-id="72b5b-177">Furthermore, they aren't necessarily designed from a capacity perspective to accommodate the anticipated loads that Teams will require.</span></span>

<span data-ttu-id="72b5b-178">建議您提供一個替代路徑來避開團隊交通的 VPN。</span><span class="sxs-lookup"><span data-stu-id="72b5b-178">The recommendation is to provide an alternate path that bypasses the VPN for Teams traffic.</span></span> <span data-ttu-id="72b5b-179">這通常稱為*分割隧道 VPN*。</span><span class="sxs-lookup"><span data-stu-id="72b5b-179">This is commonly known as *split-tunnel VPN*.</span></span> <span data-ttu-id="72b5b-180">分割隧道意味著 Microsoft 365 或 Office 365 的流量不會穿過 VPN，但會直接移至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="72b5b-180">Split tunneling means that traffic for Microsoft 365 or Office 365 won't traverse the VPN but will go directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="72b5b-181">這項變更會對品質產生正面的影響，但也會提供減少 VPN 裝置與組織網路負載的次要優點。</span><span class="sxs-lookup"><span data-stu-id="72b5b-181">This change will have a positive impact on quality, but also provides the secondary benefit of reducing load from the VPN devices and the organization's network.</span></span>

<span data-ttu-id="72b5b-182">若要實現分割隧道，請諮詢您的 VPN 供應商以取得設定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="72b5b-182">To implement a split-tunnel, consult with your VPN vendor for the configuration details.</span></span>

### <a name="wi-fi"></a><span data-ttu-id="72b5b-183">Wi-fi</span><span class="sxs-lookup"><span data-stu-id="72b5b-183">Wi-Fi</span></span>

<span data-ttu-id="72b5b-184">就像 VPN，Wi-fi 網路不一定設計或設定為支援即時媒體。</span><span class="sxs-lookup"><span data-stu-id="72b5b-184">Like VPN, Wi-Fi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="72b5b-185">規劃或優化 Wi-fi 網路以支援小組是高品質部署的重要考慮。</span><span class="sxs-lookup"><span data-stu-id="72b5b-185">Planning for, or optimizing, a Wi-Fi network to support Teams is an important consideration for a high-quality deployment.</span></span>

<span data-ttu-id="72b5b-186">在優化 Wi-fi 網路時，有幾個因素會進入播放：</span><span class="sxs-lookup"><span data-stu-id="72b5b-186">There are several factors that come into play for optimizing a Wi-Fi network:</span></span>

-   <span data-ttu-id="72b5b-187">實施 QoS 或 Wi-fi 多媒體（WMM），以確保媒體流量在 Wi-fi 網路上得到相應的優先順序。</span><span class="sxs-lookup"><span data-stu-id="72b5b-187">Implementing QoS or Wi-Fi Multimedia (WMM) to ensure that media traffic is getting prioritized accordingly over the Wi-Fi networks.</span></span>

-   <span data-ttu-id="72b5b-188">規劃及優化 Wi-fi 區段和存取點位置。</span><span class="sxs-lookup"><span data-stu-id="72b5b-188">Planning and optimizing the Wi-Fi bands and access point placement.</span></span> <span data-ttu-id="72b5b-189">2.4 GHz 範圍可能會根據存取點位置提供適當的體驗，但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。</span><span class="sxs-lookup"><span data-stu-id="72b5b-189">The 2.4 GHz range may provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="72b5b-190">5 GHz 的範圍更適合即時媒體，因為它們的密集範圍，但需要更多存取點才能取得足夠的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="72b5b-190">The 5 GHz range is better suited to real-time media due to their dense range but requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="72b5b-191">端點也需要支援該範圍，並將其設定為可據此加以設定以利用這些區段。</span><span class="sxs-lookup"><span data-stu-id="72b5b-191">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span>

-   <span data-ttu-id="72b5b-192">如果已部署雙頻帶 Wi-fi 網路，請考慮實施頻帶指導委員會。</span><span class="sxs-lookup"><span data-stu-id="72b5b-192">If dual-band Wi-Fi networks are deployed, consider implementing band steering.</span></span> <span data-ttu-id="72b5b-193">[樂隊控制] 是由 Wi-fi 廠家提供的技術，可影響雙頻帶用戶端使用 5 GHz 範圍。</span><span class="sxs-lookup"><span data-stu-id="72b5b-193">Band steering is a technique implemented by Wi-Fi vendors to influence dual-band clients to use the 5 GHz range.</span></span>

-   <span data-ttu-id="72b5b-194">當同一個頻道的存取點太靠近時，可能會導致信號重迭，並無意間爭奪，進而導致使用者無法正常發揮問題。</span><span class="sxs-lookup"><span data-stu-id="72b5b-194">When access points of the same channel are too close together they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="72b5b-195">確定彼此連續的存取點位於沒有交疊的頻道上。</span><span class="sxs-lookup"><span data-stu-id="72b5b-195">Ensure that access points that are next to each other are on channels that don't overlap.</span></span>

<span data-ttu-id="72b5b-196">每個無線廠商都有自己的部署其無線解決方案的建議。</span><span class="sxs-lookup"><span data-stu-id="72b5b-196">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="72b5b-197">我們建議您向您的廠商諮詢特定的指導方針。</span><span class="sxs-lookup"><span data-stu-id="72b5b-197">We recommend that you consult your vendor for specific guidance.</span></span>

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a><span data-ttu-id="72b5b-198">防火牆與 proxy 需求</span><span class="sxs-lookup"><span data-stu-id="72b5b-198">Firewall and proxy requirements</span></span>

<span data-ttu-id="72b5b-199">Microsoft 團隊會連線到 Microsoft Online 服務，並需要網際網路連線才能取得此問題。</span><span class="sxs-lookup"><span data-stu-id="72b5b-199">Microsoft Teams connects to Microsoft Online Services and needs internet connectivity for this.</span></span> <span data-ttu-id="72b5b-200">若要讓團隊正常運作，您必須從用戶端開啟 TCP 埠80和443，以及從用戶端到網際網路的 UDP 埠3478到3481。</span><span class="sxs-lookup"><span data-stu-id="72b5b-200">For Teams to function correctly, you must open TCP ports 80 and 443 from the clients to the internet, and UDP ports 3478 through 3481 from the clients to the internet.</span></span> <span data-ttu-id="72b5b-201">TCP 埠是用來連線到網路內容（例如 SharePoint Online、Exchange Online 和團隊聊天服務）。</span><span class="sxs-lookup"><span data-stu-id="72b5b-201">The TCP ports are used to connect to web-based content such as SharePoint Online, Exchange Online, and the Teams Chat services.</span></span>
<span data-ttu-id="72b5b-202">外掛程式和連接器也會連線到這些 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="72b5b-202">Plug-ins and connectors also connect over these TCP ports.</span></span> <span data-ttu-id="72b5b-203">在音訊和影片等媒體使用四個 UDP 埠，以確保它們正常流動。</span><span class="sxs-lookup"><span data-stu-id="72b5b-203">The four UDP ports are used for media such as audio and video, to ensure they flow correctly.</span></span>

<span data-ttu-id="72b5b-204">開啟這些埠對於可靠的小組部署而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="72b5b-204">Opening these ports is essential for a reliable Teams deployment.</span></span> <span data-ttu-id="72b5b-205">封鎖這些埠是不受支援的，而且會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="72b5b-205">Blocking these ports is unsupported and will have an effect on media quality.</span></span>

<span data-ttu-id="72b5b-206">如果您的組織要求您指定要開啟這些埠的確切 IP 位址範圍和網域，您可以限制這些埠的目標 IP 範圍和網域。</span><span class="sxs-lookup"><span data-stu-id="72b5b-206">If your organization requires that you specify the exact IP address ranges and domains to which these ports should be opened, you can restrict the target IP ranges and domains for these ports.</span></span> <span data-ttu-id="72b5b-207">如需確切的埠、通訊協定和 IP 範圍清單，請參閱[Microsoft 365 或 Office 365 url 與 ip 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。</span><span class="sxs-lookup"><span data-stu-id="72b5b-207">For a list of exact ports, protocols, and IP ranges, see [Microsoft 365 or Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).</span></span>
<span data-ttu-id="72b5b-208">如果您選擇限制目標 IP 位址範圍和網域，您必須確保將埠清單和範圍保持在最新狀態，因為它們可能會變更。</span><span class="sxs-lookup"><span data-stu-id="72b5b-208">If you choose to restrict the target IP address ranges and domains, you must ensure that you keep the list of ports and ranges up to date because they might change.</span></span> <span data-ttu-id="72b5b-209">您可以訂閱[此 RSS](https://go.microsoft.com/fwlink/p/?linkid=236301)摘要，以便在變更發生時進行更新。</span><span class="sxs-lookup"><span data-stu-id="72b5b-209">You can subscribe to [this RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) to be updated when changes occur.</span></span> <span data-ttu-id="72b5b-210">您也可以定期執行[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試所有埠是否已開啟，這也是一種很好的做法。</span><span class="sxs-lookup"><span data-stu-id="72b5b-210">It's also a good practice to test whether all ports are opened by running the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) on a regular basis.</span></span> <span data-ttu-id="72b5b-211">您可以在下一節中找到更多關於此工具功能的資訊。</span><span class="sxs-lookup"><span data-stu-id="72b5b-211">You can find out more about the functionality of this tool in the next section.</span></span>

<span data-ttu-id="72b5b-212">在要部署的 proxy 伺服器事件中，建議您略過所有團隊服務的 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="72b5b-212">In the event of a proxy server being deployed, we recommend that you bypass the proxy server for all Teams services.</span></span> <span data-ttu-id="72b5b-213">雖然您可以使用 proxy，但很可能是因為媒體不得不使用 TCP，而不是 UDP，所以品質會降低。</span><span class="sxs-lookup"><span data-stu-id="72b5b-213">Although using a proxy might work, it's very likely that quality will be reduced due to media being forced to use TCP instead of UDP.</span></span> <span data-ttu-id="72b5b-214">如需 proxy 伺服器及回避的詳細資訊，請參閱[Microsoft 365 或 Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="72b5b-214">For more information about proxy servers and bypassing, see [Microsoft 365 or Office 365 URLs and IP address ranges](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).</span></span>

<!--ENDOFSECTION-->

## <a name="test-the-network"></a><span data-ttu-id="72b5b-215">測試網路</span><span class="sxs-lookup"><span data-stu-id="72b5b-215">Test the network</span></span>

<span data-ttu-id="72b5b-216">完成規劃和網路準備之後（包括升級防火牆中的 [升級頻寬] 和 [開啟埠]），您應該測試網路的效能。</span><span class="sxs-lookup"><span data-stu-id="72b5b-216">After you've completed your planning and network preparation—including upgrading bandwidth and opening ports in the firewall—you should test your network's performance.</span></span> <span data-ttu-id="72b5b-217">這個測試的結果會讓您更清楚地瞭解任何網路優化，或您的音訊會議或電話系統是否有通話方案實現所需的修正。</span><span class="sxs-lookup"><span data-stu-id="72b5b-217">The results of this testing will paint a clearer picture of any network optimization or remediation required for the success of your Audio Conferencing or Phone System with Calling Plan implementation.</span></span>

<span data-ttu-id="72b5b-218">您可以下載[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)，以測試您的網路是否已準備好供團隊進行。</span><span class="sxs-lookup"><span data-stu-id="72b5b-218">You can download the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span> <span data-ttu-id="72b5b-219">此工具提供雙重功能：可以測試是否所有正確的埠都已開啟，而且可以測試網路是否有障礙。</span><span class="sxs-lookup"><span data-stu-id="72b5b-219">The tool offers dual functionality: it can test whether all the correct ports have been opened, and it can test for network impairments.</span></span>

<span data-ttu-id="72b5b-220">下載並安裝該工具之後，您可以在 C： \\ Program Files \\ Microsoft 商務用 Skype Network 評估工具中找到該工具。</span><span class="sxs-lookup"><span data-stu-id="72b5b-220">After you download and install the tool, you can find it in C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool.</span></span> <span data-ttu-id="72b5b-221">該目錄中包含如何使用此工具的詳細指南（例如，用法 .docx）。</span><span class="sxs-lookup"><span data-stu-id="72b5b-221">A detailed guide for how to use the tool, Usage.docx, is included in that directory.</span></span>

### <a name="test-for-opened-ports"></a><span data-ttu-id="72b5b-222">測試已開啟的埠</span><span class="sxs-lookup"><span data-stu-id="72b5b-222">Test for opened ports</span></span>

<span data-ttu-id="72b5b-223">若要開啟命令提示字元視窗並流覽至網路評量工具目錄，請輸入**Cd C： \\ Program Files \\ Microsoft 商務用 Skype Network 評估工具**。</span><span class="sxs-lookup"><span data-stu-id="72b5b-223">Open a Command prompt window and navigate to the Network Assessment Tool directory by entering **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool**.</span></span> <span data-ttu-id="72b5b-224">在命令提示字元中，輸入 networkassessmenttool 以開始測試已開啟的埠 **/connectivitycheck**</span><span class="sxs-lookup"><span data-stu-id="72b5b-224">At the command prompt, start the test for opened ports by entering **networkassessmenttool.exe /connectivitycheck**</span></span>

<span data-ttu-id="72b5b-225">執行檢查之後，該工具會顯示「驗證已成功完成」的訊息，或報告已封鎖的埠。</span><span class="sxs-lookup"><span data-stu-id="72b5b-225">After running the checks, the tool will either display the message "Verifications Completed Successfully" or report on the ports that were blocked.</span></span>
<span data-ttu-id="72b5b-226">它也會產生名為 Connectivity_results .txt 的檔案，其中包含該工具的輸出，並將其儲存在% userprofile% \\ appdata \\ 本機 \\ microsoft 商務用 skype 網路評估工具 \\ 目錄中。</span><span class="sxs-lookup"><span data-stu-id="72b5b-226">It also generates a file named Connectivity_results.txt, which contains the output from the tool and stores it in the %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\ directory.</span></span>

<span data-ttu-id="72b5b-227">我們建議您定期執行連接檢查，以確保埠已開啟且正常運作。</span><span class="sxs-lookup"><span data-stu-id="72b5b-227">We recommend that you run the connectivity checks on a regular basis to ensure the ports have been opened and are functioning correctly.</span></span>

### <a name="test-for-network-impairments"></a><span data-ttu-id="72b5b-228">測試網路是否有障礙</span><span class="sxs-lookup"><span data-stu-id="72b5b-228">Test for network impairments</span></span>

<span data-ttu-id="72b5b-229">若要提高使用者滿意度，您應該限制在網路上有任何障礙。</span><span class="sxs-lookup"><span data-stu-id="72b5b-229">To increase user satisfaction, you should limit any impairments on your network.</span></span>
<span data-ttu-id="72b5b-230">最常見的網路障礙是延遲（延遲）、資料包遺失和抖動：</span><span class="sxs-lookup"><span data-stu-id="72b5b-230">The most common network impairments are delay (latency), packet loss, and jitter:</span></span>

-   <span data-ttu-id="72b5b-231">**延遲：** 這是取得 IP 資料包從點 A 到網路上的點 B 所需的時間。</span><span class="sxs-lookup"><span data-stu-id="72b5b-231">**Latency:** This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="72b5b-232">此網路傳播延遲實質上會與兩個點之間的實際距離和光線速度之間的距離產生關聯，包括不同的路由器所佔用的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="72b5b-232">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span>
    <span data-ttu-id="72b5b-233">延遲是以單向或往返時間的方式來測量。</span><span class="sxs-lookup"><span data-stu-id="72b5b-233">Latency is measured as one-way or round-trip time.</span></span>

-   <span data-ttu-id="72b5b-234">**資料包遺失**：這通常是定義為在指定的時間視窗中遺失的資料包百分比。</span><span class="sxs-lookup"><span data-stu-id="72b5b-234">**Packet loss**: This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="72b5b-235">資料包遺失會直接影響音訊品質-從較小、個別的遺失式資料包，幾乎不會影響到完全剪下音訊的背對後爆發損失。</span><span class="sxs-lookup"><span data-stu-id="72b5b-235">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact to back-to-back burst losses that cause audio to cut out completely.</span></span>

-   <span data-ttu-id="72b5b-236">**資料包間的抖動，或簡單地抖動：** 這是連續資料包之間延遲的平均變更。</span><span class="sxs-lookup"><span data-stu-id="72b5b-236">**Inter-packet arrival jitter, or simply jitter:** This is the average change in delay between successive packets.</span></span> <span data-ttu-id="72b5b-237">大多數現代 VoIP 軟體（包括商務用 Skype）都可以透過緩衝來適應某些層級的抖動。</span><span class="sxs-lookup"><span data-stu-id="72b5b-237">Most modern VoIP software, including Skype for Business, can adapt to some levels of jitter through buffering.</span></span> <span data-ttu-id="72b5b-238">只有抖動超過了參與者會注意到抖動效果的緩衝，才會出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="72b5b-238">It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.</span></span>

<span data-ttu-id="72b5b-239">在[媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中，會說明這些障礙的最大值。</span><span class="sxs-lookup"><span data-stu-id="72b5b-239">The maximum values for these impairments are described in [Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>
<span data-ttu-id="72b5b-240">測試這些障礙時，我們會區分兩個不同的區段：</span><span class="sxs-lookup"><span data-stu-id="72b5b-240">When testing for these impairments, we distinguish between two separate segments:</span></span>

-   <span data-ttu-id="72b5b-241">[*邊緣] 區段*是您的路由器所在的區段。</span><span class="sxs-lookup"><span data-stu-id="72b5b-241">The *edge segment* is the segment in which your router lives.</span></span> <span data-ttu-id="72b5b-242">這是您在每個位置都連接至網際網路的最接近邏輯網路區段。</span><span class="sxs-lookup"><span data-stu-id="72b5b-242">This is the closest logical network segment connected to the internet at each of your locations.</span></span> <span data-ttu-id="72b5b-243">在大多數情況下，這是路由器的連接點，或可能是周邊網路（也稱為*DMZ*、*隔離區域*及*遮罩子網*）。</span><span class="sxs-lookup"><span data-stu-id="72b5b-243">In most cases, this is the connection point of the router, or possibly a perimeter network (also known as *DMZ*, *demilitarized zone*, and *screened subnet*).</span></span> <span data-ttu-id="72b5b-244">除了路由器以外的裝置之外，不會發生任何其他影響裝置與網際網路之間的通信量。</span><span class="sxs-lookup"><span data-stu-id="72b5b-244">No further traffic that affects devices other than the router should occur between this segment and the internet.</span></span>

-   <span data-ttu-id="72b5b-245">*用戶端區段*是您的用戶端所在的邏輯網路區段。</span><span class="sxs-lookup"><span data-stu-id="72b5b-245">The *client segment* is the logical network segment in which your clients reside.</span></span>

<span data-ttu-id="72b5b-246">您應該使用 [網路評量] 工具測試這兩個區段。</span><span class="sxs-lookup"><span data-stu-id="72b5b-246">You should test both segments by using the Network Assessment Tool.</span></span> <span data-ttu-id="72b5b-247">若要測試區段，請流覽至該目錄，然後在命令提示字元中輸入**networkassessmenttool。**</span><span class="sxs-lookup"><span data-stu-id="72b5b-247">To test the segment, navigate to the directory and enter **networkassessmenttool.exe** at the command prompt.</span></span> <span data-ttu-id="72b5b-248">結果會寫入名為 tsv 的檔案名，您可以將其與每個區段的[需求](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)進行比較。</span><span class="sxs-lookup"><span data-stu-id="72b5b-248">The results are written to a file named Results.tsv, and you can compare them to the [requirements](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) for each segment.</span></span>

<span data-ttu-id="72b5b-249">請注意，這兩個區段必須符合高品質部署的需求。</span><span class="sxs-lookup"><span data-stu-id="72b5b-249">Note that both segments must meet the requirements for a high-quality deployment.</span></span> <span data-ttu-id="72b5b-250">我們建議您多次執行該工具，以讓您的網路效能得到良好的指示。</span><span class="sxs-lookup"><span data-stu-id="72b5b-250">We recommend that you run the tool multiple times for one hour straight to get a good indication of your network's performance.</span></span>

<!--ENDOFSECTION-->

## <a name="network-remediation"></a><span data-ttu-id="72b5b-251">網路修正</span><span class="sxs-lookup"><span data-stu-id="72b5b-251">Network remediation</span></span>

<span data-ttu-id="72b5b-252">如果頻寬規劃、埠測試或網路需求測試的結果顯示您目前的網路需要修正，才能部署小組，您可以透過下列幾種方式來完成此動作：</span><span class="sxs-lookup"><span data-stu-id="72b5b-252">If the results of bandwidth planning, port testing, or network requirements testing show that your current network needs remediation before you deploy Teams, you can accomplish this in several ways:</span></span>

-   <span data-ttu-id="72b5b-253">如果沒有足夠的頻寬，請升級連線，讓 Microsoft 365 或 Office 365 的流量能夠流過 unhindered。</span><span class="sxs-lookup"><span data-stu-id="72b5b-253">For insufficient bandwidth, upgrade connections so that traffic to Microsoft 365 or Office 365 can flow unhindered.</span></span>

-   <span data-ttu-id="72b5b-254">針對封鎖的埠，請變更防火牆規則並重新測試埠。</span><span class="sxs-lookup"><span data-stu-id="72b5b-254">For blocked ports, change firewall rules and retest the ports.</span></span>

-   <span data-ttu-id="72b5b-255">針對網路障礙，請務必執行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="72b5b-255">For network impairments, always perform a root-cause analysis.</span></span>

<span data-ttu-id="72b5b-256">您可以將服務品質（QoS）劃分優先順序並分隔流量，以讓障礙不足。</span><span class="sxs-lookup"><span data-stu-id="72b5b-256">Quality of service (QoS) can be used to battle impairments by prioritizing and separating traffic.</span></span> <span data-ttu-id="72b5b-257">有些組織會選擇部署 QoS 來克服頻寬問題，或限制流量流動的通信量。</span><span class="sxs-lookup"><span data-stu-id="72b5b-257">Some organizations choose to deploy QoS to overcome bandwidth issues or restrict the amount of traffic flowing.</span></span> <span data-ttu-id="72b5b-258">這不會改善品質，也會導致新問題。</span><span class="sxs-lookup"><span data-stu-id="72b5b-258">This won't improve quality and will lead to new problems.</span></span> <span data-ttu-id="72b5b-259">當網路障礙超過需求時，請務必執行根本原因分析。</span><span class="sxs-lookup"><span data-stu-id="72b5b-259">A root-cause analysis should always be performed when network impairments exceed requirements.</span></span> <span data-ttu-id="72b5b-260">QoS 可以是解決方案。</span><span class="sxs-lookup"><span data-stu-id="72b5b-260">QoS can be a solution.</span></span>
<span data-ttu-id="72b5b-261">如需詳細資訊，請參閱[Microsoft 團隊中的服務品質](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="72b5b-261">For more information, see [Quality of Service in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).</span></span>

>[!NOTE]
><span data-ttu-id="72b5b-262">許多網路由於升級、擴充或其他業務需求而逐漸隨著時間發展。</span><span class="sxs-lookup"><span data-stu-id="72b5b-262">Many networks evolve over time due to upgrades, expansion, or other business requirements.</span></span> <span data-ttu-id="72b5b-263">請確定您有適當的運作程式，以維護這些區域做為服務管理規劃的一部分。</span><span class="sxs-lookup"><span data-stu-id="72b5b-263">Ensure that you have operational processes in place to maintain these areas as part of your service management planning.</span></span>


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="72b5b-264">決策點</span><span class="sxs-lookup"><span data-stu-id="72b5b-264">Decision points</span></span></td><td><ul><li><span data-ttu-id="72b5b-265">誰負責在所有網路區段和組織位置完成正確的網路評估？</span><span class="sxs-lookup"><span data-stu-id="72b5b-265">Who will be responsible for completing proper network assessments across all network segments and organization locations?</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="72b5b-266">後續步驟</span><span class="sxs-lookup"><span data-stu-id="72b5b-266">Next steps</span></span></td><td><ul><li><span data-ttu-id="72b5b-267">您可以執行詳細的網路評量，以協助確保您的網路可供您的 Microsoft 團隊部署使用。</span><span class="sxs-lookup"><span data-stu-id="72b5b-267">You can perform a detailed network assessment to help ensure your network is ready for your Microsoft Teams deployment.</span></span></li><li><span data-ttu-id="72b5b-268">根據每個網路區段評估的結果來執行網路修正。</span><span class="sxs-lookup"><span data-stu-id="72b5b-268">Perform network remediation based on the results of the assessment for every network segment.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
