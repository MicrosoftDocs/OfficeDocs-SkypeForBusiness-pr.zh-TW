---
title: 商務用 Skype Server 的以影片為基礎的螢幕共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 商務用 Skype Server 規劃與影片畫面共用的配置資訊 (VbSS)
ms.openlocfilehash: ae2cc683148fdb2a2cb80e3fe3cf25a698a56c00
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "36193924"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="c086a-103">商務用 Skype Server 的以影片為基礎的螢幕共用</span><span class="sxs-lookup"><span data-stu-id="c086a-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="c086a-104">商務用 Skype Server 2015 中的影片畫面共用 (VbSS) 現已可供下載:[商務用 Skype server 2015 累計更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="c086a-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690).</span></span> <span data-ttu-id="c086a-105">VbSS 隨附于商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="c086a-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="c086a-106">以影片為基礎的畫面共用或 VbSS, 會隨著 Lync 螢幕共用而增長。</span><span class="sxs-lookup"><span data-stu-id="c086a-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="c086a-107">VbSS 與傳統螢幕共用的差異, 必須與所使用的基本協定以及其 excel 位於何處。</span><span class="sxs-lookup"><span data-stu-id="c086a-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="c086a-108">螢幕共用使用遠端桌面通訊協定 (RDP), 這相當於在人員電腦之間建立數以千計的1對1會話。</span><span class="sxs-lookup"><span data-stu-id="c086a-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="c086a-109">較新的技術 (VbSS) 會使用使用者資料包通訊協定 (UDP)。</span><span class="sxs-lookup"><span data-stu-id="c086a-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="c086a-110">商務用 Skype Server 想要改善人員的1對 1, 以及其一對多 (多方) 交談和會議體驗。</span><span class="sxs-lookup"><span data-stu-id="c086a-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="c086a-111">VbSS 會使用媒體平臺 (依賴 UDP 做為基礎通訊協定), 目的是改善影片啟動時間、觀賞品質 (尤其是您正在觀看的內容是快速的移動), 以及整體的可靠性。</span><span class="sxs-lookup"><span data-stu-id="c086a-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="c086a-112">改善螢幕共用的其中一個原因, 就是 VbSS 和 RDP 之間的轉換會盡可能順暢地進行。</span><span class="sxs-lookup"><span data-stu-id="c086a-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="c086a-113">由於 VbSS 是在商務用 Skype Server 的螢幕共用中所使用的基礎技術的更新, 因此, 除非您是在網路流量中查看 SIP 詳細資料, 或是您要共用的內容, 否則可能難以偵測到您正在使用的技術為快速移動或立體。</span><span class="sxs-lookup"><span data-stu-id="c086a-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="c086a-114">例如, 如果您的工作場所有許多舊版用戶端, 則在您的會議和交談中, RDP 仍可提供安全的故障。</span><span class="sxs-lookup"><span data-stu-id="c086a-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="c086a-115">商務用 Skype Server 在用戶端連線時, 會使用內部邏輯來決定要套用哪兩種方法 (VbSS 或傳統螢幕共用)。</span><span class="sxs-lookup"><span data-stu-id="c086a-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="c086a-116">在情況下, RDP 可以和將取代為 VbSS, 因此您的流覽體驗不會中斷。</span><span class="sxs-lookup"><span data-stu-id="c086a-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="c086a-117">規劃</span><span class="sxs-lookup"><span data-stu-id="c086a-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="c086a-118">VbSS 的優點與缺點</span><span class="sxs-lookup"><span data-stu-id="c086a-118">VbSS pros and cons</span></span>

<span data-ttu-id="c086a-119">切換到 VbSS 旨在改善三項主要功能:</span><span class="sxs-lookup"><span data-stu-id="c086a-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="c086a-120">進行螢幕共用 (最多 5%)與 RDP 單獨比較, 以獲得更可靠的對比。</span><span class="sxs-lookup"><span data-stu-id="c086a-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="c086a-121">讓會話設定和影片體驗與 RDP (半時間) 更快速, 且每秒的畫面改善6:1。</span><span class="sxs-lookup"><span data-stu-id="c086a-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="c086a-122">在低頻寬情況下, 即使是在共用高運動內容 (例如3D 圖形) 時, 它的運作效果都比 RDP 要好得多。</span><span class="sxs-lookup"><span data-stu-id="c086a-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="c086a-123">請記住, 這些數位依賴于健康情況和對您網路的適當效能調整, 如果您的用戶端在行動裝置上, 也可能會包含您自己的外部網路。</span><span class="sxs-lookup"><span data-stu-id="c086a-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="c086a-124">您也應該注意, 您的共用內容的一些逼真度/crispness 已經過大量的可靠性、速度和效能。</span><span class="sxs-lookup"><span data-stu-id="c086a-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="c086a-125">在大多數情況下, 使用者不會看到這種情況。</span><span class="sxs-lookup"><span data-stu-id="c086a-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="c086a-126">埠與通訊協定</span><span class="sxs-lookup"><span data-stu-id="c086a-126">Ports and protocols</span></span>

<span data-ttu-id="c086a-127">**所需的伺服器埠**</span><span class="sxs-lookup"><span data-stu-id="c086a-127">**Required server ports**</span></span>

|<span data-ttu-id="c086a-128">**伺服器角色**</span><span class="sxs-lookup"><span data-stu-id="c086a-128">**Server role**</span></span>|<span data-ttu-id="c086a-129">**服務名稱**</span><span class="sxs-lookup"><span data-stu-id="c086a-129">**Service name**</span></span>|<span data-ttu-id="c086a-130">**埠或埠範圍**</span><span class="sxs-lookup"><span data-stu-id="c086a-130">**Port or port range**</span></span>|<span data-ttu-id="c086a-131">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="c086a-131">**Protocol**</span></span>|<span data-ttu-id="c086a-132">**筆記**</span><span class="sxs-lookup"><span data-stu-id="c086a-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c086a-133">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c086a-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="c086a-134">商務用 Skype Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="c086a-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="c086a-135">5065</span><span class="sxs-lookup"><span data-stu-id="c086a-135">5065</span></span>  <br/> |<span data-ttu-id="c086a-136">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="c086a-136">TCP</span></span>  <br/> |<span data-ttu-id="c086a-137">用於應用程式共用的傳入 SIP 偵聽要求。</span><span class="sxs-lookup"><span data-stu-id="c086a-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="c086a-138">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c086a-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="c086a-139">商務用 Skype Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="c086a-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="c086a-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="c086a-140">49152-65535</span></span>  <br/> |<span data-ttu-id="c086a-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c086a-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="c086a-142">用來共用應用程式的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="c086a-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="c086a-143">**所需的用戶端埠**</span><span class="sxs-lookup"><span data-stu-id="c086a-143">**Required client ports**</span></span>

|<span data-ttu-id="c086a-144">**元件**</span><span class="sxs-lookup"><span data-stu-id="c086a-144">**Component**</span></span>|<span data-ttu-id="c086a-145">**埠範圍**</span><span class="sxs-lookup"><span data-stu-id="c086a-145">**Port range**</span></span>|<span data-ttu-id="c086a-146">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="c086a-146">**Protocol**</span></span>|<span data-ttu-id="c086a-147">**筆記**</span><span class="sxs-lookup"><span data-stu-id="c086a-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c086a-148">台</span><span class="sxs-lookup"><span data-stu-id="c086a-148">Clients</span></span>  <br/> |<span data-ttu-id="c086a-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="c086a-149">1024-65535</span></span>  <br/> |<span data-ttu-id="c086a-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c086a-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="c086a-151">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="c086a-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="c086a-152">如果已啟用下列媒體埠的 QoS, 且 VbSS 已啟用, 則在包含桌面共用作為 MCU 的會議期間, 就會使用下方以粗體顯示的視訊連接埠設定, 以供螢幕共用流量使用。</span><span class="sxs-lookup"><span data-stu-id="c086a-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c086a-153">這些設定是一個特殊的情況, 在同時執行這兩個功能時, 必須使用這些確切的設定。</span><span class="sxs-lookup"><span data-stu-id="c086a-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="c086a-154">這會覆寫 [QoS][檔](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的其他建議設定。</span><span class="sxs-lookup"><span data-stu-id="c086a-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="c086a-155">針對應用程式共用, 除了定義這些埠值之外, 您還需要在 QoS GPO 中指定 ASMCUSVC。</span><span class="sxs-lookup"><span data-stu-id="c086a-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="c086a-156">**應用程式伺服器 QoS/VbSS 必要的設定**</span><span class="sxs-lookup"><span data-stu-id="c086a-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="c086a-157">**Property**</span><span class="sxs-lookup"><span data-stu-id="c086a-157">**Property**</span></span>|<span data-ttu-id="c086a-158">**埠值**</span><span class="sxs-lookup"><span data-stu-id="c086a-158">**Port value**</span></span>|<span data-ttu-id="c086a-159">**通訊協定**</span><span class="sxs-lookup"><span data-stu-id="c086a-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c086a-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="c086a-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="c086a-161">49152</span><span class="sxs-lookup"><span data-stu-id="c086a-161">49152</span></span>  <br/> |<span data-ttu-id="c086a-162">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="c086a-162">UDP</span></span>  <br/> |
|<span data-ttu-id="c086a-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="c086a-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="c086a-164">8348</span><span class="sxs-lookup"><span data-stu-id="c086a-164">8348</span></span>  <br/> |<span data-ttu-id="c086a-165">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="c086a-165">UDP</span></span>  <br/> |
|<span data-ttu-id="c086a-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="c086a-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="c086a-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="c086a-167">**57501**</span></span> <br/> |<span data-ttu-id="c086a-168">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="c086a-168">UDP</span></span>  <br/> |
|<span data-ttu-id="c086a-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="c086a-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="c086a-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="c086a-170">**8034**</span></span> <br/> |<span data-ttu-id="c086a-171">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="c086a-171">UDP</span></span>  <br/> |
|<span data-ttu-id="c086a-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="c086a-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="c086a-173">40803</span><span class="sxs-lookup"><span data-stu-id="c086a-173">40803</span></span>  <br/> |<span data-ttu-id="c086a-174">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="c086a-174">TCP</span></span>  <br/> |
|<span data-ttu-id="c086a-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="c086a-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="c086a-176">8348</span><span class="sxs-lookup"><span data-stu-id="c086a-176">8348</span></span>  <br/> |<span data-ttu-id="c086a-177">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="c086a-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="c086a-178">容量規劃</span><span class="sxs-lookup"><span data-stu-id="c086a-178">Capacity planning</span></span>

<span data-ttu-id="c086a-179">每個執行商務用 Skype Server 2015 累積更新 2 (CU2) 或更新版本的前端伺服器, 都支援最多375個參與者使用 RDP 進行畫面共用 (不過每個會議僅有 250)。</span><span class="sxs-lookup"><span data-stu-id="c086a-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="c086a-180">此容量不會變更 CU3, 而是在推出 VbSS 時使用。</span><span class="sxs-lookup"><span data-stu-id="c086a-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="c086a-181">我們所說的是, 我們已在實驗室中完成效能與壓力測試, 而且應該考慮使用您自己的部署 (視情況而定)。</span><span class="sxs-lookup"><span data-stu-id="c086a-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="c086a-182">假如</span><span class="sxs-lookup"><span data-stu-id="c086a-182">Assuming:</span></span>
  
- <span data-ttu-id="c086a-183">您在部署中使用商務用 Skype Server 2015 CU2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="c086a-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="c086a-184">商務用 Skype Server 環境中的所有使用者都有比1920x1080 高的螢幕解析度。</span><span class="sxs-lookup"><span data-stu-id="c086a-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="c086a-185">在完整容量 (如上所述) 是每個前端伺服器總的375螢幕共用參與者, 但在每個會議中只有 250, 則您的前端伺服器可能會利用的是1十億位元網卡的 ~ 89%。</span><span class="sxs-lookup"><span data-stu-id="c086a-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="c086a-186">這是因為商務用 Skype Server CU2 (RDP) 中現有的螢幕共用技術會以簡報者電腦的原生解析度來傳送螢幕內容。</span><span class="sxs-lookup"><span data-stu-id="c086a-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="c086a-187">如此一來, 使用商務用 Skype Server 2015 CU2, 您可能已遇到網路瓶頸, 讓螢幕解析度更高。</span><span class="sxs-lookup"><span data-stu-id="c086a-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="c086a-188">若要緩解此情況, 下列其中一或多個選項可能很有用:</span><span class="sxs-lookup"><span data-stu-id="c086a-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="c086a-189">將您的前端伺服器從1千兆網卡升級為 10 Gigabit 乙太網卡。</span><span class="sxs-lookup"><span data-stu-id="c086a-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="c086a-190">增加前端伺服器的數目, 以進行負載平衡流量。</span><span class="sxs-lookup"><span data-stu-id="c086a-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="c086a-191">將 cap 放在任何一個通道所使用的最大頻寬, 限制 VbSS 和 RDP 所使用的頻寬 (位元速率)。</span><span class="sxs-lookup"><span data-stu-id="c086a-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="c086a-192">此表格中的數位會受到個別網路以及共用內容的影響。</span><span class="sxs-lookup"><span data-stu-id="c086a-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="c086a-193">請進行測試, 為您的網路或網路建立比較基準。</span><span class="sxs-lookup"><span data-stu-id="c086a-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="c086a-194">**1080p 內容**</span><span class="sxs-lookup"><span data-stu-id="c086a-194">**1080p Content**</span></span>|<span data-ttu-id="c086a-195">**RDP 平均值**</span><span class="sxs-lookup"><span data-stu-id="c086a-195">**RDP Average**</span></span>|<span data-ttu-id="c086a-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="c086a-196">**RDP Peak**</span></span>|<span data-ttu-id="c086a-197">**VbSS 平均值**</span><span class="sxs-lookup"><span data-stu-id="c086a-197">**VbSS Average**</span></span>|<span data-ttu-id="c086a-198">**VbSS 峰值**</span><span class="sxs-lookup"><span data-stu-id="c086a-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c086a-199">.PPT</span><span class="sxs-lookup"><span data-stu-id="c086a-199">PPT</span></span>  <br/> |<span data-ttu-id="c086a-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="c086a-200">200kbps</span></span>  <br/> |<span data-ttu-id="c086a-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-201">12mbps</span></span>  <br/> |<span data-ttu-id="c086a-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="c086a-202">100kbps</span></span>  <br/> |<span data-ttu-id="c086a-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="c086a-204">CAD</span><span class="sxs-lookup"><span data-stu-id="c086a-204">CAD</span></span>  <br/> |<span data-ttu-id="c086a-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-205">3mbps</span></span>  <br/> |<span data-ttu-id="c086a-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-206">7mbps</span></span>  <br/> |<span data-ttu-id="c086a-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-207">1mbps</span></span>  <br/> |<span data-ttu-id="c086a-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="c086a-209">顯示器</span><span class="sxs-lookup"><span data-stu-id="c086a-209">Video</span></span>  <br/> |<span data-ttu-id="c086a-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-210">5mbps</span></span>  <br/> |<span data-ttu-id="c086a-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-211">7mbps</span></span>  <br/> |<span data-ttu-id="c086a-212">1.3 mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="c086a-213">2.2 mbps</span><span class="sxs-lookup"><span data-stu-id="c086a-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="c086a-214">媒體流量的網路頻寬需求</span><span class="sxs-lookup"><span data-stu-id="c086a-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="c086a-215">VbSS 頻寬為:</span><span class="sxs-lookup"><span data-stu-id="c086a-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="c086a-216">**影片編碼解碼器**</span><span class="sxs-lookup"><span data-stu-id="c086a-216">**Video codec**</span></span>|<span data-ttu-id="c086a-217">**解析度和長寬比**</span><span class="sxs-lookup"><span data-stu-id="c086a-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="c086a-218">**最大視頻有效負載位元速率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="c086a-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="c086a-219">**最小視頻有效負載位元速率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="c086a-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c086a-220">H-p</span><span class="sxs-lookup"><span data-stu-id="c086a-220">H.264</span></span>  <br/> |<span data-ttu-id="c086a-221">1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="c086a-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="c086a-222">([長寬比] 視共用的監視器解析度而定, 並不會永遠為 16:9)</span><span class="sxs-lookup"><span data-stu-id="c086a-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="c086a-223">4000</span><span class="sxs-lookup"><span data-stu-id="c086a-223">4000</span></span>  <br/> |<span data-ttu-id="c086a-224">1500</span><span class="sxs-lookup"><span data-stu-id="c086a-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="c086a-225">用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="c086a-225">Clients and servers support</span></span>

<span data-ttu-id="c086a-226">以影片為基礎的螢幕共用需要商務用 Skype Server 2015 CU3 或更新版本, 以及適用于商務用 Skype 與[會議支援](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的行動[用戶端功能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中所列的支援用戶端目前版本。</span><span class="sxs-lookup"><span data-stu-id="c086a-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="c086a-227">在某些情況下, 螢幕共用會轉換為 RDP, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c086a-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="c086a-228">如果您的帳戶是託管在 ASMCU 不符合支援 VbSS 之最小組建的環境中。</span><span class="sxs-lookup"><span data-stu-id="c086a-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="c086a-229">如果有人使用較舊版本的商務用 Skype 用戶端加入您的會話, 例如任何使用低於16.0.6330.1000 的任何 Windows 用戶端版本、商務用 Skype 房間系統裝置或商務用 Skype 行動裝置 App。</span><span class="sxs-lookup"><span data-stu-id="c086a-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="c086a-230">如果使用者是從商務用 Skype Web App 共用。</span><span class="sxs-lookup"><span data-stu-id="c086a-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="c086a-231">如果有人使用 Mac 版商務用 Skype, 而不是託管于商務用 skype Online, 或使用7月、2018累計更新 (或更新版本) 的商務用 skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c086a-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="c086a-232">如果有人啟動任何程式/Windows 共用,</span><span class="sxs-lookup"><span data-stu-id="c086a-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="c086a-233">如果有人開始錄製會議。</span><span class="sxs-lookup"><span data-stu-id="c086a-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="c086a-234">如果有人在會話期間喚醒打電話給遠端螢幕控制。</span><span class="sxs-lookup"><span data-stu-id="c086a-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="c086a-235">超過250個參與者的會議 (目前不支援 VbSS)。</span><span class="sxs-lookup"><span data-stu-id="c086a-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="c086a-236">請注意, 一旦會話轉換為 RDP, 就不會轉換回 VbSS。</span><span class="sxs-lookup"><span data-stu-id="c086a-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="c086a-237">同樣地, 從 VbSS 轉場是無縫的, 而且在大多數情況下, 都不容易偵測到您的願望。</span><span class="sxs-lookup"><span data-stu-id="c086a-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c086a-238">在商務用 Skype 畫面共用中, 不支援封鎖或嘗試封鎖、從 VbSS 轉換為 RDP。</span><span class="sxs-lookup"><span data-stu-id="c086a-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="c086a-239">啟用、停用和設定 VbSS</span><span class="sxs-lookup"><span data-stu-id="c086a-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="c086a-240">最重要的是, 一旦您安裝商務用 Skype Server 2015 累計更新 3 (CU3) 或更新版本之後, 您的所有使用者預設都會啟用1到1和多方 VbSS。</span><span class="sxs-lookup"><span data-stu-id="c086a-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="c086a-241">如果您有理由讓所有使用者都無法使用此功能, 這可能會給您帶來問題。</span><span class="sxs-lookup"><span data-stu-id="c086a-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="c086a-242">在這種情況下, 您可以使用這些步驟來停用使用者 ([啟用使用者] 步驟如下所示):</span><span class="sxs-lookup"><span data-stu-id="c086a-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="c086a-243">如何從 VbSS 停用使用者</span><span class="sxs-lookup"><span data-stu-id="c086a-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="c086a-244">您可以在商務用 Skype 管理主控台中執行此 Cmdlet 來指派不允許 VbSS 使用 VbSS 的使用者原則 (將 [PolicyName] 取代為您所執行的原則):</span><span class="sxs-lookup"><span data-stu-id="c086a-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="c086a-245">您也可以更新全域會議原則, 這將會影響所有沒有指派原則的使用者:</span><span class="sxs-lookup"><span data-stu-id="c086a-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="c086a-246">如需此命令的詳細資訊, 請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c086a-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="c086a-247">如果您需要完全關閉 VbSS, 您可以執行此命令:</span><span class="sxs-lookup"><span data-stu-id="c086a-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="c086a-248">如需此命令的詳細資訊, 請參閱[設定 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c086a-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c086a-249">在多方商務用 Skype 會議中, 所有用戶端端點都會遵循會議召集人的原則設定。</span><span class="sxs-lookup"><span data-stu-id="c086a-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="c086a-250">如何讓使用者使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="c086a-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="c086a-251">您可以在商務用 Skype 管理主控台中執行此 Cmdlet 來指派允許 VbSS 使用 VbSS 的特定使用者原則 (將 [PolicyName] 取代為您所執行的原則):</span><span class="sxs-lookup"><span data-stu-id="c086a-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="c086a-252">您也可以更新全域會議原則, 這將會影響所有沒有指派原則的使用者:</span><span class="sxs-lookup"><span data-stu-id="c086a-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="c086a-253">如需此命令的詳細資訊, 請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c086a-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="c086a-254">如果您需要在關閉後再開啟 VbSS (預設為開啟), 您可以執行這個命令:</span><span class="sxs-lookup"><span data-stu-id="c086a-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="c086a-255">如需此命令的詳細資訊, 請參閱[設定 CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c086a-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c086a-256">在多方商務用 Skype 會議中, 所有用戶端端點都會遵循會議召集人的原則設定。</span><span class="sxs-lookup"><span data-stu-id="c086a-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c086a-257">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c086a-257">See also</span></span>

[<span data-ttu-id="c086a-258">商務用 Skype Server 2015 累計更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="c086a-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[<span data-ttu-id="c086a-259">商務用 Skype Server 2015 提供影片畫面共用 (VBSS)</span><span class="sxs-lookup"><span data-stu-id="c086a-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/en-us/kb/3170163)
