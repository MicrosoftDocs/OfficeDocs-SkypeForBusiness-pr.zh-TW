---
title: 規劃使用者對 Microsoft 團隊的體驗
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 [團隊用戶端應用程式]，規劃端點品質，取得部署 Wi-fi 端點及選擇音訊裝置的建議。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d156761d8ebc39822d6ccf2fc28ed6c380c4e117
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825181"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="937aa-103">規劃我的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="937aa-103">Plan my users’ experience</span></span>

<span data-ttu-id="937aa-104">本文概述正確識別您的雲端語音服務部署元素的需求，這些專案會直接影響您的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="937aa-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="937aa-105">在部署之前先準備好這些專案，就能增加成功為使用者提供高品質、可靠體驗的機會。</span><span class="sxs-lookup"><span data-stu-id="937aa-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="937aa-106">用戶端部署</span><span class="sxs-lookup"><span data-stu-id="937aa-106">Client deployment</span></span>

<span data-ttu-id="937aa-107">Microsoft 團隊擁有可供 web、桌面（Windows 和 Mac）及行動裝置（Android 與 iOS）使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="937aa-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="937aa-108">如需如何安裝桌面（Windows 和 Mac）與行動用戶端的其他詳細資料，請參閱[取得 Microsoft 團隊的用戶端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="937aa-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="client-updates"></a><span data-ttu-id="937aa-109">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="937aa-109">Client updates</span></span>

<span data-ttu-id="937aa-110">團隊的其中一個主要優點是，用戶端會自動保持為最新狀態。</span><span class="sxs-lookup"><span data-stu-id="937aa-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="937aa-111">PC 和 Mac 上的用戶端會使用背景處理常式來更新，在 app 空閒時檢查新的組建並下載新的用戶端。</span><span class="sxs-lookup"><span data-stu-id="937aa-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="937aa-112">規劃端點品質</span><span class="sxs-lookup"><span data-stu-id="937aa-112">Plan for endpoint quality</span></span>

<span data-ttu-id="937aa-113">在下圖中您可以看到，端點是提供使用者品質體驗的重要組建區塊。</span><span class="sxs-lookup"><span data-stu-id="937aa-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="937aa-114">![描述三個品質元件的圖表](media/plan-my-users-experience-image1.png "描述三個品質元件的圖表，以及服務管理如何與所有三個元件重迭。將焦點放在端點上。")</span><span class="sxs-lookup"><span data-stu-id="937aa-114">![Diagram describing the three components of quality](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="937aa-115">團隊端點可以在許多裝置上執行，包括 Pc、Mac、平板電腦和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="937aa-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="937aa-116">部分體驗不僅包括裝置，而且使用者如何連線到裝置，例如使用裝置內建的麥克風/喇叭、earbuds 或優化的耳機。</span><span class="sxs-lookup"><span data-stu-id="937aa-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="937aa-117">使用優化的耳機可豐富整體使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="937aa-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="937aa-118">下列針對端點規劃的指導方針可協助您確保貴組織成功地使用團隊加入了您的組織。</span><span class="sxs-lookup"><span data-stu-id="937aa-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="937aa-119">端點功能</span><span class="sxs-lookup"><span data-stu-id="937aa-119">Endpoint capability</span></span>

<span data-ttu-id="937aa-120">規劃中的第一個部分是確保貴組織中的所有電腦和其他裝置都能執行團隊。</span><span class="sxs-lookup"><span data-stu-id="937aa-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="937aa-121">這涉及不只是查看硬體需求，還需要瞭解電腦在背景執行的其他動作。</span><span class="sxs-lookup"><span data-stu-id="937aa-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="937aa-122">許多組織會執行其他軟體，包括入侵偵測系統和反惡意程式碼，這可能會影響裝置的基本效能。</span><span class="sxs-lookup"><span data-stu-id="937aa-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="937aa-123">如需每個平臺（網頁、桌面及行動裝置）上團隊用戶端軟體需求的相關資訊，請參閱[取得 Microsoft 團隊的用戶端](https://docs.microsoft.com/microsoftteams/get-clients)。</span><span class="sxs-lookup"><span data-stu-id="937aa-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="937aa-124">端點防火牆</span><span class="sxs-lookup"><span data-stu-id="937aa-124">Endpoint firewalls</span></span>

<span data-ttu-id="937aa-125">用戶端防火牆對使用者體驗的影響可能會有很大的影響。</span><span class="sxs-lookup"><span data-stu-id="937aa-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="937aa-126">用戶端防火牆可能會影響通話品質，除了可防止通話的建立。</span><span class="sxs-lookup"><span data-stu-id="937aa-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="937aa-127">根據[Office 365 url 和 IP 位址範圍](https://aka.ms/o365ips)中的資訊，在用戶端防火牆上設定適當的排除。</span><span class="sxs-lookup"><span data-stu-id="937aa-127">Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span> <span data-ttu-id="937aa-128">您的協力廠商廠商將提供有關如何建立排除項的特定指導方針。</span><span class="sxs-lookup"><span data-stu-id="937aa-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="937aa-129">Microsoft 團隊會自動使用適當的防火牆設定來更新 Windows 防火牆。</span><span class="sxs-lookup"><span data-stu-id="937aa-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="937aa-130">端點的 wi-fi 建議</span><span class="sxs-lookup"><span data-stu-id="937aa-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="937aa-131">需要進行大量規劃，才能部署已優化的 Wi-fi 網路，以支援 Microsoft 團隊中的即時工作負載。</span><span class="sxs-lookup"><span data-stu-id="937aa-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="937aa-132">下列各節提供一些一般指導方針，可協助您在規劃端點時避免常見的錯誤。</span><span class="sxs-lookup"><span data-stu-id="937aa-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="937aa-133">Wi-fi 驅動程式</span><span class="sxs-lookup"><span data-stu-id="937aa-133">Wi-Fi drivers</span></span>

<span data-ttu-id="937aa-134">某些 Wi-fi 驅動程式可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="937aa-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="937aa-135">例如，驅動程式在存取點之間可能會有非常嚴格的漫遊行為，導致通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="937aa-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="937aa-136">這不是常見的情況，但請務必確保電腦上的 Wi-fi 驅動程式已在部署之前更新並經過測試。</span><span class="sxs-lookup"><span data-stu-id="937aa-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="937aa-137">Wi-fi 區段</span><span class="sxs-lookup"><span data-stu-id="937aa-137">Wi-Fi bands</span></span>

<span data-ttu-id="937aa-138">目前在 Wi-fi 裝置、2.4 GHz 和 5.0 GHz 中，主要使用兩種類型的區段。</span><span class="sxs-lookup"><span data-stu-id="937aa-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="937aa-139">如果您的組織同時提供兩個頻帶，您應該將您的驅動程式設定設定為優先使用 5.0 GHz 區段。</span><span class="sxs-lookup"><span data-stu-id="937aa-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="937aa-140">此區段在輸送量方面是很大的 denser，而且受到 2.4 GHz 區段干擾的影響較小。</span><span class="sxs-lookup"><span data-stu-id="937aa-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="937aa-141">此建議假設您已正確優化 5.0 GHz 網路區段。</span><span class="sxs-lookup"><span data-stu-id="937aa-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="937aa-142">Wi-fi 無線電類型</span><span class="sxs-lookup"><span data-stu-id="937aa-142">Wi-Fi radio type</span></span>

<span data-ttu-id="937aa-143">規劃支援新版 Wi-fi 無線電類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="937aa-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="937aa-144">如果您在您所設定的裝置上，利用 802.11 ac 或更新版本，就能取得良好的 Wi-fi 效能。</span><span class="sxs-lookup"><span data-stu-id="937aa-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="937aa-145">無線回避</span><span class="sxs-lookup"><span data-stu-id="937aa-145">Wireless avoidance</span></span>

<span data-ttu-id="937aa-146">有些組織傾向于完全避免使用 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="937aa-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="937aa-147">在某些情況下，此指導方針是透過將使用者直接連線至有線網路的建議提供的。</span><span class="sxs-lookup"><span data-stu-id="937aa-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="937aa-148">在某些情況下，網路系結順序可能會有最佳的無線連線，而且即使電腦已連接至有線連線，仍會繼續使用該連線。</span><span class="sxs-lookup"><span data-stu-id="937aa-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="937aa-149">若要避免此意外行為，請設定系結順序來避免這種情況。</span><span class="sxs-lookup"><span data-stu-id="937aa-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="937aa-150">802.11 省電通訊協定</span><span class="sxs-lookup"><span data-stu-id="937aa-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="937aa-151">如果您的組織使用的無線存取點或路由器不支援802.11 節能通訊協定，在 Windows 裝置上執行的 Microsoft 團隊中，您可能會遇到通話中斷或太差的通話品質。</span><span class="sxs-lookup"><span data-stu-id="937aa-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="937aa-152">如果無法升級您的無線存取點或路由器，您應該在以電池電源執行的裝置上更新 Windows 電源配置設定。</span><span class="sxs-lookup"><span data-stu-id="937aa-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="937aa-153">下列[支援文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了進一步的詳細資訊和設定指導方針。</span><span class="sxs-lookup"><span data-stu-id="937aa-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="937aa-154">決策點</span><span class="sxs-lookup"><span data-stu-id="937aa-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="937aa-155">貴組織中將部署哪些團隊用戶端？</span><span class="sxs-lookup"><span data-stu-id="937aa-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="937aa-156">您要如何開始將團隊用戶端部署到您的使用者？</span><span class="sxs-lookup"><span data-stu-id="937aa-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="937aa-157">誰負責評估端點和裝置，以驗證他們是否符合品質體驗的小組需求？</span><span class="sxs-lookup"><span data-stu-id="937aa-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="937aa-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="937aa-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="937aa-159">記錄部署團隊用戶端所遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="937aa-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="937aa-160">評估端點和裝置，並需要執行與修正。</span><span class="sxs-lookup"><span data-stu-id="937aa-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="937aa-161">團隊裝置</span><span class="sxs-lookup"><span data-stu-id="937aa-161">Devices for Teams</span></span>

<span data-ttu-id="937aa-162">Microsoft 團隊可以用於會議或作為電話系統。</span><span class="sxs-lookup"><span data-stu-id="937aa-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="937aa-163">使用這些功能時，小組所用的介面裝置在使用者體驗中起著重要的作用。</span><span class="sxs-lookup"><span data-stu-id="937aa-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="937aa-164">如果您使用的是內建電腦喇叭和麥克風，擁有該設定的使用者就可能會聽到聲音。</span><span class="sxs-lookup"><span data-stu-id="937aa-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="937aa-165">但一般來說，這些裝置並未針對雜訊取消進行優化，而且任何類型的環境干擾都可能對通話中其他人產生下游影響。</span><span class="sxs-lookup"><span data-stu-id="937aa-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="937aa-166">利用針對這些案例優化的裝置將有助於確保高品質的體驗。</span><span class="sxs-lookup"><span data-stu-id="937aa-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="937aa-167">每個裝置都必須符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="937aa-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="937aa-168">您必須針對貴組織中的不同角色和使用案例，調整裝置（例如耳機）。</span><span class="sxs-lookup"><span data-stu-id="937aa-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="937aa-169">在規劃程式中應完成角色對裝置的對應練習。</span><span class="sxs-lookup"><span data-stu-id="937aa-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="937aa-170">選取裝置之後，請將它們包含在最終驗證的試驗測試方案中。</span><span class="sxs-lookup"><span data-stu-id="937aa-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="937aa-171">在試驗期間利用調查來收集意見反應，以確保您的裝置策略是最佳的。</span><span class="sxs-lookup"><span data-stu-id="937aa-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="937aa-172">目前，我們建議使用透過商務用 Skype 認證計畫認證的音訊裝置。</span><span class="sxs-lookup"><span data-stu-id="937aa-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="937aa-173">若要尋找此程式下認證的裝置，請參閱[Microsoft 團隊裝置](https://products.office.com/en-us/microsoft-teams/across-devices/devices)和[USB 音訊與視頻裝置](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)。</span><span class="sxs-lookup"><span data-stu-id="937aa-173">To find devices certified under this program, see the [Microsoft Teams devices](https://products.office.com/en-us/microsoft-teams/across-devices/devices) and [USB audio and video devices](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="937aa-174">決策點</span><span class="sxs-lookup"><span data-stu-id="937aa-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="937aa-175">決定您組織的整體裝置策略，以取得使用者和會議室的體驗。</span><span class="sxs-lookup"><span data-stu-id="937aa-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="937aa-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="937aa-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="937aa-177">針對您的組織完成角色對裝置對應練習。</span><span class="sxs-lookup"><span data-stu-id="937aa-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="937aa-178">記錄為使用者和會議室取得裝置的程式。</span><span class="sxs-lookup"><span data-stu-id="937aa-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="937aa-179">為使用者和會議室的部署和設定裝置記錄程式。</span><span class="sxs-lookup"><span data-stu-id="937aa-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="937aa-180">購買初始裝置以開始您的部署。</span><span class="sxs-lookup"><span data-stu-id="937aa-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
