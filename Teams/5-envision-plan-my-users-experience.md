---
title: 規劃使用者使用Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 Teams應用程式、規劃端點品質、取得部署端點Wi-Fi以及選擇音訊裝置的建議。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094731"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="860d0-103">規劃使用者的體驗</span><span class="sxs-lookup"><span data-stu-id="860d0-103">Plan my users’ experience</span></span>

<span data-ttu-id="860d0-104">本文提供正確識別雲端語音服務部署元素的需求概觀，這些元素會直接影響使用者的體驗。</span><span class="sxs-lookup"><span data-stu-id="860d0-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="860d0-105">在部署前準備這些專案，將提高您成功為使用者提供高品質、可靠體驗的機會。</span><span class="sxs-lookup"><span data-stu-id="860d0-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="860d0-106">用戶端部署</span><span class="sxs-lookup"><span data-stu-id="860d0-106">Client deployment</span></span>

<span data-ttu-id="860d0-107">Microsoft Teams Android 和 iOS (Windows Mac) ，以及行動 (Android 和 iOS) 。</span><span class="sxs-lookup"><span data-stu-id="860d0-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="860d0-108">有關桌上型電腦和 Mac (Windows和) 用戶端的安裝詳細資料，請參閱取得用戶端[Microsoft Teams。](./get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="860d0-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="client-updates"></a><span data-ttu-id="860d0-109">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="860d0-109">Client updates</span></span>

<span data-ttu-id="860d0-110">其中一個Teams優點就是用戶端會自動保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="860d0-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="860d0-111">PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新建立，並下載應用程式閒置時的新用戶端。</span><span class="sxs-lookup"><span data-stu-id="860d0-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="860d0-112">規劃端點品質</span><span class="sxs-lookup"><span data-stu-id="860d0-112">Plan for endpoint quality</span></span>

<span data-ttu-id="860d0-113">如下圖所示，端點是為使用者提供品質體驗的重要建組塊。</span><span class="sxs-lookup"><span data-stu-id="860d0-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="860d0-114">![描述品質三個要素的圖表](media/plan-my-users-experience-image1.png "描述品質的三個元件，以及服務管理如何與這三個元件重迭的圖表。將焦點放在端點上。")</span><span class="sxs-lookup"><span data-stu-id="860d0-114">![Diagram describing the three components of quality](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="860d0-115">Teams端點可在許多裝置上執行，包括 PC、Mac、平板電腦和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="860d0-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="860d0-116">部分體驗不僅包含裝置，還包括使用者如何連接到裝置，例如使用裝置內建的麥克風/喇叭、耳塞或優化的耳機。</span><span class="sxs-lookup"><span data-stu-id="860d0-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="860d0-117">使用優化的耳機可豐富整體使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="860d0-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="860d0-118">下列端點規劃指南可協助確保貴組織能順利使用Teams。</span><span class="sxs-lookup"><span data-stu-id="860d0-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="860d0-119">端點功能</span><span class="sxs-lookup"><span data-stu-id="860d0-119">Endpoint capability</span></span>

<span data-ttu-id="860d0-120">規劃的第一部分，是為了確保貴組織的所有電腦和其他裝置都可以Teams。</span><span class="sxs-lookup"><span data-stu-id="860d0-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="860d0-121">這不只涉及查看硬體需求，也涉及瞭解電腦在背景中執行哪些其他操作。</span><span class="sxs-lookup"><span data-stu-id="860d0-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="860d0-122">許多組織會執行其他軟體，包括入侵偵測系統和反惡意軟體，這可能會影響裝置的基本性能。</span><span class="sxs-lookup"><span data-stu-id="860d0-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="860d0-123">有關 Web、桌面Teams行動 (每個平臺用戶端的軟體需求) ，請參閱取得用戶端[Microsoft Teams。](./get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="860d0-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="860d0-124">端點防火牆</span><span class="sxs-lookup"><span data-stu-id="860d0-124">Endpoint firewalls</span></span>

<span data-ttu-id="860d0-125">用戶端防火牆會對使用者體驗有重大的影響。</span><span class="sxs-lookup"><span data-stu-id="860d0-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="860d0-126">除了防止建立通話之外，用戶端防火牆也會影響通話品質。</span><span class="sxs-lookup"><span data-stu-id="860d0-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="860d0-127">根據 URL 或 IP 位址範圍中的 Microsoft 365 或 ip 位址範圍Office 365用戶端防火牆上的[適當排除專案](/microsoft-365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="860d0-127">Configure the appropriate exclusions on the client firewall based on the information in [Microsoft 365 or Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="860d0-128">您的協力廠商廠商將擁有如何建立排除專案的特定指引。</span><span class="sxs-lookup"><span data-stu-id="860d0-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="860d0-129">Microsoft Teams會以適當的防火牆Windows防火牆的自動更新。</span><span class="sxs-lookup"><span data-stu-id="860d0-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="860d0-130">Wi-Fi端點的建議</span><span class="sxs-lookup"><span data-stu-id="860d0-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="860d0-131">部署優化的Wi-Fi網路，以支援即時工作負載，需要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="860d0-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="860d0-132">下列各節提供一些一般指南，可協助避免規劃端點時常見的錯誤。</span><span class="sxs-lookup"><span data-stu-id="860d0-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="860d0-133">Wi-Fi驅動程式</span><span class="sxs-lookup"><span data-stu-id="860d0-133">Wi-Fi drivers</span></span>

<span data-ttu-id="860d0-134">某些Wi-Fi驅動程式可能會有問題。</span><span class="sxs-lookup"><span data-stu-id="860d0-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="860d0-135">例如，驅動程式在訪問點之間可能具有非常積極的漫遊行為，導致通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="860d0-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="860d0-136">這不是很常見的情況，但一Wi-Fi在部署前，確保已更新和測試 PC 上的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="860d0-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="860d0-137">Wi-Fi帶</span><span class="sxs-lookup"><span data-stu-id="860d0-137">Wi-Fi bands</span></span>

<span data-ttu-id="860d0-138">現今在設備中使用的頻帶Wi-Fi種，2.4 GHz 和 5.0 GHz。</span><span class="sxs-lookup"><span data-stu-id="860d0-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="860d0-139">如果貴組織同時提供這兩個頻帶，您應該設定驅動程式設定，以偏好 5.0 GHz 頻帶。</span><span class="sxs-lookup"><span data-stu-id="860d0-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="860d0-140">此頻帶在輸送量方面密度更高，且受到 2.4 GHz 頻帶的干擾影響較小。</span><span class="sxs-lookup"><span data-stu-id="860d0-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="860d0-141">此建議假設您已正確優化 5.0 GHz 網路帶。</span><span class="sxs-lookup"><span data-stu-id="860d0-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="860d0-142">Wi-Fi廣播類型</span><span class="sxs-lookup"><span data-stu-id="860d0-142">Wi-Fi radio type</span></span>

<span data-ttu-id="860d0-143">規劃支援較新的無線Wi-Fi裝置。</span><span class="sxs-lookup"><span data-stu-id="860d0-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="860d0-144">如果您在您撥備的裝置Wi-Fi 802.11ac 或更新版本，就可以獲得很好的使用效果。</span><span class="sxs-lookup"><span data-stu-id="860d0-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="860d0-145">無線避免</span><span class="sxs-lookup"><span data-stu-id="860d0-145">Wireless avoidance</span></span>

<span data-ttu-id="860d0-146">有些組織偏好完全避免Wi-Fi問題。</span><span class="sxs-lookup"><span data-stu-id="860d0-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="860d0-147">有時候，這項指引會透過建議提供給使用者，讓使用者直接連接到有線網路。</span><span class="sxs-lookup"><span data-stu-id="860d0-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="860d0-148">在某些情況下，網路綁定順序可能偏好使用無線網路連接，即使電腦已連接到有線連接，仍繼續使用該連接。</span><span class="sxs-lookup"><span data-stu-id="860d0-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="860d0-149">若要避免此非預期行為，請設定綁定順序以避免此情況。</span><span class="sxs-lookup"><span data-stu-id="860d0-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="860d0-150">802.11 Power Save 通訊協定</span><span class="sxs-lookup"><span data-stu-id="860d0-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="860d0-151">如果貴組織使用不支援 802.11 Power Save 通訊協定的無線訪問點或路由器，您可能會在 Windows 裝置上Microsoft Teams通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="860d0-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="860d0-152">如果無法升級無線存取點或路由器，您應該更新Windows電池電力的裝置上的 Power Plan 設定。</span><span class="sxs-lookup"><span data-stu-id="860d0-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="860d0-153">下列支援文章提供進一步的詳細資料及組 [組指引](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)。</span><span class="sxs-lookup"><span data-stu-id="860d0-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="860d0-154">決策點</span><span class="sxs-lookup"><span data-stu-id="860d0-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="860d0-155">哪些Teams用戶端會部署在貴組織中？</span><span class="sxs-lookup"><span data-stu-id="860d0-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="860d0-156">您一開始要如何Teams用戶端？</span><span class="sxs-lookup"><span data-stu-id="860d0-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="860d0-157">神秘負責評估端點和裝置，以驗證它們符合Teams品質體驗的需求嗎？</span><span class="sxs-lookup"><span data-stu-id="860d0-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="860d0-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="860d0-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="860d0-159">記錄部署用戶端時Teams程式。</span><span class="sxs-lookup"><span data-stu-id="860d0-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="860d0-160">評估端點和裝置，並需要執行及補救。</span><span class="sxs-lookup"><span data-stu-id="860d0-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="860d0-161">適用于 Teams</span><span class="sxs-lookup"><span data-stu-id="860d0-161">Devices for Teams</span></span>

<span data-ttu-id="860d0-162">Microsoft Teams可用於會議或電話系統。</span><span class="sxs-lookup"><span data-stu-id="860d0-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="860d0-163">使用這些功能時，用於Teams介面裝置在使用者體驗中會扮演重要角色。</span><span class="sxs-lookup"><span data-stu-id="860d0-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="860d0-164">使用內建電腦喇叭和麥克風可能聽起來對擁有該組式的使用者來說可以接受。</span><span class="sxs-lookup"><span data-stu-id="860d0-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="860d0-165">但一般來說，這些裝置未針對雜訊消除進行優化，而且任何類型的環境雜訊會對通話中的其他人造成下游影響。</span><span class="sxs-lookup"><span data-stu-id="860d0-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="860d0-166">運用針對這些案例優化的裝置，有助於確保高品質的體驗。</span><span class="sxs-lookup"><span data-stu-id="860d0-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="860d0-167">每個裝置都必須符合使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="860d0-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="860d0-168">您需要為貴組織中不同的角色和使用案例量身打造裝置，例如耳機。</span><span class="sxs-lookup"><span data-stu-id="860d0-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="860d0-169">在規劃程式過程中，應完成人員對裝置映射練習。</span><span class="sxs-lookup"><span data-stu-id="860d0-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="860d0-170">選取裝置之後，請將其納入試驗測試計劃，以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="860d0-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="860d0-171">在試驗期間運用問卷收集意見，以確保您的裝置策略最佳。</span><span class="sxs-lookup"><span data-stu-id="860d0-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="860d0-172">目前，我們建議您使用通過認證計畫商務用 Skype裝置。</span><span class="sxs-lookup"><span data-stu-id="860d0-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="860d0-173">若要尋找此計畫所認證的裝置，請參閱[Microsoft Teams裝置和](https://products.office.com/microsoft-teams/across-devices/devices)USB[音訊與視音訊裝置](/SkypeForBusiness/certification/devices-usb-devices)。</span><span class="sxs-lookup"><span data-stu-id="860d0-173">To find devices certified under this program, see the [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices/devices) and [USB audio and video devices](/SkypeForBusiness/certification/devices-usb-devices).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="860d0-174">決策點</span><span class="sxs-lookup"><span data-stu-id="860d0-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="860d0-175">決定貴組織的使用者和會議室體驗的整體裝置策略。</span><span class="sxs-lookup"><span data-stu-id="860d0-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="860d0-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="860d0-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="860d0-177">為貴組織完成人員對裝置映射練習。</span><span class="sxs-lookup"><span data-stu-id="860d0-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="860d0-178">記錄取得使用者和會議室裝置的過程。</span><span class="sxs-lookup"><span data-stu-id="860d0-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="860d0-179">記錄使用者和會議室的部署和組組裝置程式。</span><span class="sxs-lookup"><span data-stu-id="860d0-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="860d0-180">取得初始裝置以開始部署。</span><span class="sxs-lookup"><span data-stu-id="860d0-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->