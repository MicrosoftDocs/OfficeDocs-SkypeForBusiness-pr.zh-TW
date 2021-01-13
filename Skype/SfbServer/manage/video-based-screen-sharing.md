---
title: 商務用 Skype Server 視訊的螢幕畫面分享
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: '商務用 Skype Server 的規劃和設定資訊，以影片的螢幕共用 (VbSS) '
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832763"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="43394-103">商務用 Skype Server 視訊的螢幕畫面分享</span><span class="sxs-lookup"><span data-stu-id="43394-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="43394-104">在商務用 Skype Server 2015 中，影片的畫面 (VbSS) 現在可供下載： [商務用 Skype server 2015 累計更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。</span><span class="sxs-lookup"><span data-stu-id="43394-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="43394-105">VbSS 隨附于商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="43394-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="43394-106">以影片為基礎的螢幕共用或 VbSS，會成長至 Lync 螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="43394-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="43394-107">VbSS 與傳統畫面共用之間的差異，必須與所用的基礎通訊協定及 excel 的定義相同。</span><span class="sxs-lookup"><span data-stu-id="43394-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="43394-108">螢幕共用使用遠端桌面通訊協定 (RDP) ，它非常適合在人員的電腦之間建立數千個1對1會話。</span><span class="sxs-lookup"><span data-stu-id="43394-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="43394-109">更新的技術 VbSS 會使用使用者資料包通訊協定 (UDP) 。</span><span class="sxs-lookup"><span data-stu-id="43394-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="43394-110">商務用 Skype 伺服器想要提升人員的1對1，以及他們的一對多 (多方) 交談和會議經驗。</span><span class="sxs-lookup"><span data-stu-id="43394-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="43394-111">VbSS 會利用以 UDP 為基礎通訊協定) 的媒體平臺 (，其目的是為了縮短影片的開始時間，在您所觀賞的情況下，您所看到的內容的觀賞品質 (尤其是在您所觀賞的情況下，您所看到的內容的) 速度和整體可靠性。</span><span class="sxs-lookup"><span data-stu-id="43394-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="43394-112">改善螢幕共用的目的之一是，在 VbSS 和 RDP 之間的轉變會盡可能順利進行。</span><span class="sxs-lookup"><span data-stu-id="43394-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="43394-113">因為 VbSS 是用於商務用 Skype Server 之螢幕共用中所用的基礎技術更新，所以除非您在網路流量中查看 SIP 詳細資料，或是要共用快移或立體的內容，否則可能很難偵測出您要使用的技術。</span><span class="sxs-lookup"><span data-stu-id="43394-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="43394-114">例如，如果您的工作場所有許多舊版用戶端，則 RDP 仍可作為您的會議和交談的安全。</span><span class="sxs-lookup"><span data-stu-id="43394-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="43394-115">商務用 Skype Server 使用內部邏輯來決定兩種方法中的哪一種 (VbSS 或傳統的螢幕共用) 在用戶端連線時套用。</span><span class="sxs-lookup"><span data-stu-id="43394-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="43394-116">當情況呼叫它時，RDP 可以和會取代 VbSS，因此您的觀賞體驗不會中斷。</span><span class="sxs-lookup"><span data-stu-id="43394-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="43394-117">規劃</span><span class="sxs-lookup"><span data-stu-id="43394-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="43394-118">VbSS 優點和缺點</span><span class="sxs-lookup"><span data-stu-id="43394-118">VbSS pros and cons</span></span>

<span data-ttu-id="43394-119">切換至 VbSS 旨在進行三項重要改進：</span><span class="sxs-lookup"><span data-stu-id="43394-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="43394-120">將螢幕共用 (高達5% 的 ) 比獨立于 RDP 更可靠。</span><span class="sxs-lookup"><span data-stu-id="43394-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="43394-121">將會話設定和影片體驗與 RDP 個別相較于 RDP (安裝程式的速度提高了一半，6:1 但每秒幀數的) 都會提高。</span><span class="sxs-lookup"><span data-stu-id="43394-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="43394-122">即使在共用高運動內容時（例如立體圖形），在低頻寬條件下，它的運作方式要好于 RDP。</span><span class="sxs-lookup"><span data-stu-id="43394-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="43394-123">請記住，這些數位取決於您網路的健康情況和適當效能調整，如果您的用戶端在行動裝置上，可能會包含您自己的網路。</span><span class="sxs-lookup"><span data-stu-id="43394-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="43394-124">您也應該知道，共用內容的一些逼真度/crispness 已針對可靠性、速度和效能而提高效益。</span><span class="sxs-lookup"><span data-stu-id="43394-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="43394-125">在大多數情況下，使用者不會看到這種情況。</span><span class="sxs-lookup"><span data-stu-id="43394-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="43394-126">連接埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="43394-126">Ports and protocols</span></span>

<span data-ttu-id="43394-127">**必要的伺服器埠**</span><span class="sxs-lookup"><span data-stu-id="43394-127">**Required server ports**</span></span>

|<span data-ttu-id="43394-128">**伺服器角色**</span><span class="sxs-lookup"><span data-stu-id="43394-128">**Server role**</span></span>|<span data-ttu-id="43394-129">**服務名稱**</span><span class="sxs-lookup"><span data-stu-id="43394-129">**Service name**</span></span>|<span data-ttu-id="43394-130">**埠或埠範圍**</span><span class="sxs-lookup"><span data-stu-id="43394-130">**Port or port range**</span></span>|<span data-ttu-id="43394-131">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="43394-131">**Protocol**</span></span>|<span data-ttu-id="43394-132">**附註**</span><span class="sxs-lookup"><span data-stu-id="43394-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43394-133">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="43394-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="43394-134">商務用 Skype Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="43394-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="43394-135">5065</span><span class="sxs-lookup"><span data-stu-id="43394-135">5065</span></span>  <br/> |<span data-ttu-id="43394-136">TCP</span><span class="sxs-lookup"><span data-stu-id="43394-136">TCP</span></span>  <br/> |<span data-ttu-id="43394-137">用於應用程式共用的傳入 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="43394-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="43394-138">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="43394-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="43394-139">商務用 Skype Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="43394-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="43394-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="43394-140">49152-65535</span></span>  <br/> |<span data-ttu-id="43394-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43394-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="43394-142">用於應用程式共用的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="43394-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="43394-143">**必要的用戶端埠**</span><span class="sxs-lookup"><span data-stu-id="43394-143">**Required client ports**</span></span>

|<span data-ttu-id="43394-144">**元件**</span><span class="sxs-lookup"><span data-stu-id="43394-144">**Component**</span></span>|<span data-ttu-id="43394-145">**連接埠範圍**</span><span class="sxs-lookup"><span data-stu-id="43394-145">**Port range**</span></span>|<span data-ttu-id="43394-146">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="43394-146">**Protocol**</span></span>|<span data-ttu-id="43394-147">**附註**</span><span class="sxs-lookup"><span data-stu-id="43394-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43394-148">用戶端</span><span class="sxs-lookup"><span data-stu-id="43394-148">Clients</span></span>  <br/> |<span data-ttu-id="43394-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="43394-149">1024-65535</span></span>  <br/> |<span data-ttu-id="43394-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="43394-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="43394-151">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="43394-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="43394-152">如果已啟用下列媒體埠的 QoS，而且 VbSS 也已啟用，則在包含桌面共用的會議期間，您的畫面共用流量會使用以粗體顯示的影片埠設定。</span><span class="sxs-lookup"><span data-stu-id="43394-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="43394-153">這些設定為特殊案例，在同時執行這兩種功能時，必須使用這些設定。</span><span class="sxs-lookup"><span data-stu-id="43394-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="43394-154">這會覆寫 [QoS 檔](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)中的其他建議設定。</span><span class="sxs-lookup"><span data-stu-id="43394-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="43394-155">針對應用程式共用，除了定義這些埠值之外，還需要在 QoS GPO 中指定 ASMCUSVC.exe。</span><span class="sxs-lookup"><span data-stu-id="43394-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="43394-156">**Application Server QoS/VbSS 必要設定**</span><span class="sxs-lookup"><span data-stu-id="43394-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="43394-157">**屬性**</span><span class="sxs-lookup"><span data-stu-id="43394-157">**Property**</span></span>|<span data-ttu-id="43394-158">**埠值**</span><span class="sxs-lookup"><span data-stu-id="43394-158">**Port value**</span></span>|<span data-ttu-id="43394-159">**Protocol** (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="43394-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="43394-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="43394-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="43394-161">49152</span><span class="sxs-lookup"><span data-stu-id="43394-161">49152</span></span>  <br/> |<span data-ttu-id="43394-162">Udp</span><span class="sxs-lookup"><span data-stu-id="43394-162">UDP</span></span>  <br/> |
|<span data-ttu-id="43394-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="43394-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="43394-164">8348</span><span class="sxs-lookup"><span data-stu-id="43394-164">8348</span></span>  <br/> |<span data-ttu-id="43394-165">Udp</span><span class="sxs-lookup"><span data-stu-id="43394-165">UDP</span></span>  <br/> |
|<span data-ttu-id="43394-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="43394-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="43394-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="43394-167">**57501**</span></span> <br/> |<span data-ttu-id="43394-168">Udp</span><span class="sxs-lookup"><span data-stu-id="43394-168">UDP</span></span>  <br/> |
|<span data-ttu-id="43394-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="43394-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="43394-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="43394-170">**8034**</span></span> <br/> |<span data-ttu-id="43394-171">Udp</span><span class="sxs-lookup"><span data-stu-id="43394-171">UDP</span></span>  <br/> |
|<span data-ttu-id="43394-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="43394-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="43394-173">40803</span><span class="sxs-lookup"><span data-stu-id="43394-173">40803</span></span>  <br/> |<span data-ttu-id="43394-174">TCP</span><span class="sxs-lookup"><span data-stu-id="43394-174">TCP</span></span>  <br/> |
|<span data-ttu-id="43394-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="43394-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="43394-176">8348</span><span class="sxs-lookup"><span data-stu-id="43394-176">8348</span></span>  <br/> |<span data-ttu-id="43394-177">TCP</span><span class="sxs-lookup"><span data-stu-id="43394-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="43394-178">容量規劃</span><span class="sxs-lookup"><span data-stu-id="43394-178">Capacity planning</span></span>

<span data-ttu-id="43394-179">每個執行商務用 Skype Server 2015 累計更新 2 (CU2) 或更新版本375可支援使用 RDP (的畫面共用，但僅限250每個會議) 。</span><span class="sxs-lookup"><span data-stu-id="43394-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="43394-180">當引進和使用 VbSS 時，此容量不會變更 CU3 後的容量。</span><span class="sxs-lookup"><span data-stu-id="43394-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="43394-181">也就是說，我們已在實驗室中完成效能和應力測試，而且也應視您的部署 (考慮，視) 的使用方式而定，也應考慮下列度量。</span><span class="sxs-lookup"><span data-stu-id="43394-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="43394-182">假設：</span><span class="sxs-lookup"><span data-stu-id="43394-182">Assuming:</span></span>
  
- <span data-ttu-id="43394-183">您使用的是商務用 Skype Server 2015 CU2 或更新版本的部署。</span><span class="sxs-lookup"><span data-stu-id="43394-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="43394-184">商務用 Skype 伺服器環境中的所有使用者的畫面解析度都高於1920x1080。</span><span class="sxs-lookup"><span data-stu-id="43394-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="43394-185">在上面所述的完整容量 (（如以上所述）為每個前端伺服器的375螢幕共用參與者總數，雖然每個會議只有 250) ，但您的前端伺服器可能會使用大約 1 Gb 網路卡的89%。</span><span class="sxs-lookup"><span data-stu-id="43394-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="43394-186">這是因為商務用 Skype Server CU2 中的現有螢幕共用技術 (RDP) 會以原生解析度在簡報者的電腦上，以原生解析度傳送螢幕上的內容。</span><span class="sxs-lookup"><span data-stu-id="43394-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="43394-187">因此，在中所述的螢幕解析度越高，您可能會遇到與商務用 Skype Server 2015 CU2 的畫面共用的網路瓶頸。</span><span class="sxs-lookup"><span data-stu-id="43394-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="43394-188">為了緩解這種情況，下列一或多個選項可能很有用：</span><span class="sxs-lookup"><span data-stu-id="43394-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="43394-189">將前端伺服器從 1 Gb 的網卡升級為 10 Gb 的乙太網卡。</span><span class="sxs-lookup"><span data-stu-id="43394-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="43394-190">增加前端伺服器數目，以進行負載平衡流量。</span><span class="sxs-lookup"><span data-stu-id="43394-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="43394-191">將 cap 置於任一通道所使用的最大頻寬上，以限制 VbSS 和 RDP 所用的頻寬 (位元速率) 。</span><span class="sxs-lookup"><span data-stu-id="43394-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="43394-192">此表格中的數位會受到個別網路及共用內容的影響。</span><span class="sxs-lookup"><span data-stu-id="43394-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="43394-193">請測試以建立網路或網路的基準。</span><span class="sxs-lookup"><span data-stu-id="43394-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="43394-194">**1080p 內容**</span><span class="sxs-lookup"><span data-stu-id="43394-194">**1080p Content**</span></span>|<span data-ttu-id="43394-195">**RDP 平均**</span><span class="sxs-lookup"><span data-stu-id="43394-195">**RDP Average**</span></span>|<span data-ttu-id="43394-196">**RDP 峰值**</span><span class="sxs-lookup"><span data-stu-id="43394-196">**RDP Peak**</span></span>|<span data-ttu-id="43394-197">**平均 VbSS**</span><span class="sxs-lookup"><span data-stu-id="43394-197">**VbSS Average**</span></span>|<span data-ttu-id="43394-198">**VbSS 峰**</span><span class="sxs-lookup"><span data-stu-id="43394-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43394-199">Ppt</span><span class="sxs-lookup"><span data-stu-id="43394-199">PPT</span></span>  <br/> |<span data-ttu-id="43394-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="43394-200">200kbps</span></span>  <br/> |<span data-ttu-id="43394-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="43394-201">12mbps</span></span>  <br/> |<span data-ttu-id="43394-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="43394-202">100kbps</span></span>  <br/> |<span data-ttu-id="43394-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="43394-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="43394-204">Cad</span><span class="sxs-lookup"><span data-stu-id="43394-204">CAD</span></span>  <br/> |<span data-ttu-id="43394-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="43394-205">3mbps</span></span>  <br/> |<span data-ttu-id="43394-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="43394-206">7mbps</span></span>  <br/> |<span data-ttu-id="43394-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="43394-207">1mbps</span></span>  <br/> |<span data-ttu-id="43394-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="43394-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="43394-209">影片</span><span class="sxs-lookup"><span data-stu-id="43394-209">Video</span></span>  <br/> |<span data-ttu-id="43394-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="43394-210">5mbps</span></span>  <br/> |<span data-ttu-id="43394-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="43394-211">7mbps</span></span>  <br/> |<span data-ttu-id="43394-212">1.3 mbps</span><span class="sxs-lookup"><span data-stu-id="43394-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="43394-213">2.2 mbps</span><span class="sxs-lookup"><span data-stu-id="43394-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="43394-214">媒體流量的網路頻寬需求</span><span class="sxs-lookup"><span data-stu-id="43394-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="43394-215">VbSS 頻寬如下：</span><span class="sxs-lookup"><span data-stu-id="43394-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="43394-216">**視訊轉碼器**</span><span class="sxs-lookup"><span data-stu-id="43394-216">**Video codec**</span></span>|<span data-ttu-id="43394-217">**解析度和外觀比例**</span><span class="sxs-lookup"><span data-stu-id="43394-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="43394-218">**最大影片負載位元速率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="43394-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="43394-219">**最小影片負載位元速率 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="43394-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43394-220">H-p</span><span class="sxs-lookup"><span data-stu-id="43394-220">H.264</span></span>  <br/> |<span data-ttu-id="43394-221">1920x1080 (16:9) </span><span class="sxs-lookup"><span data-stu-id="43394-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="43394-222"> (的方位比例取決於共用者的監視器解析度，而且不一定會是 16:9) </span><span class="sxs-lookup"><span data-stu-id="43394-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="43394-223">4000</span><span class="sxs-lookup"><span data-stu-id="43394-223">4000</span></span>  <br/> |<span data-ttu-id="43394-224">1500</span><span class="sxs-lookup"><span data-stu-id="43394-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="43394-225">用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="43394-225">Clients and servers support</span></span>

<span data-ttu-id="43394-226">以影片為基礎的螢幕共用需要商務用 Skype Server 2015 CU3 或更新版本，以及適用于商務用 Skype 和[會議支援](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的行動[用戶端功能比較](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中列出的目前支援用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="43394-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="43394-227">在某些情況下，螢幕共用會轉換為 RDP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43394-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="43394-228">如果您的帳戶主控于 ASMCU 未符合支援 VbSS 的最低組建的環境中。</span><span class="sxs-lookup"><span data-stu-id="43394-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="43394-229">如果使用舊版商務用 Skype 用戶端的人員加入您的會話，例如，使用任何 Windows 用戶端版本低於16.0.6330.1000、商務用 Skype 會議室系統裝置或商務用 Skype 行動應用程式的人員。</span><span class="sxs-lookup"><span data-stu-id="43394-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="43394-230">如果使用者是從商務用 Skype Web App 共用。</span><span class="sxs-lookup"><span data-stu-id="43394-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="43394-231">如果有人在 Mac 上使用商務用 Skype，而非位於7月、2018累計更新 (或更新) 版本的 skype Online 或商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="43394-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="43394-232">如果有人啟動任何程式/Windows 共用。</span><span class="sxs-lookup"><span data-stu-id="43394-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="43394-233">如果有人開始記錄會話。</span><span class="sxs-lookup"><span data-stu-id="43394-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="43394-234">如果有人在會話期間呼叫遠端螢幕控制。</span><span class="sxs-lookup"><span data-stu-id="43394-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="43394-235">超過250位參與者的會議 (目前不支援 VbSS) 。</span><span class="sxs-lookup"><span data-stu-id="43394-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="43394-236">請注意，一旦會話轉換至 RDP，它就不會轉換回 VbSS。</span><span class="sxs-lookup"><span data-stu-id="43394-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="43394-237">同樣地，從 VbSS 的過渡是指無縫的，而且在大多數情況下，使用願望也不會偵測到。</span><span class="sxs-lookup"><span data-stu-id="43394-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="43394-238">在商務用 Skype 螢幕共用中，不支援封鎖或嘗試封鎖、從 VbSS 轉換為 RDP。</span><span class="sxs-lookup"><span data-stu-id="43394-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="43394-239">啟用、停用及設定 VbSS</span><span class="sxs-lookup"><span data-stu-id="43394-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="43394-240">最棒的是，當您已安裝商務用 Skype Server 2015 累計更新 3 (CU3) 或更新版本之後，預設會為1對1和多方 VbSS 啟用所有使用者。</span><span class="sxs-lookup"><span data-stu-id="43394-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="43394-241">如果您有理由不讓所有使用者啟用此功能，這可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="43394-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="43394-242">在此情況下，您可以使用這些步驟來停用使用者 (啟用使用者的步驟將遵循) ：</span><span class="sxs-lookup"><span data-stu-id="43394-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="43394-243">如何使用 VbSS 來停用使用者</span><span class="sxs-lookup"><span data-stu-id="43394-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="43394-244">您可以在商務用 Skype 管理主控台中執行此指令程式，以將不允許 VbSS 的使用者原則指派給不允許 VbSS 的任何使用者， (取代 [PolicyName] 以進行) 的原則：</span><span class="sxs-lookup"><span data-stu-id="43394-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="43394-245">您也可以更新全域會議原則，此原則會影響所有未指派原則的使用者：</span><span class="sxs-lookup"><span data-stu-id="43394-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="43394-246">如需此命令的詳細資訊，請參閱 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="43394-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="43394-247">如果您需要完全關閉 VbSS，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="43394-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="43394-248">如需此命令的詳細資訊，請參閱 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="43394-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="43394-249">在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。</span><span class="sxs-lookup"><span data-stu-id="43394-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="43394-250">如何讓使用者能夠使用 VbSS</span><span class="sxs-lookup"><span data-stu-id="43394-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="43394-251">您可以在商務用 Skype 管理主控台中執行此指令程式，以指定特定的使用者原則，以 VbSS 允許任何需要使用 VbSS 的使用者， (取代 [PolicyName] 以進行) 的原則：</span><span class="sxs-lookup"><span data-stu-id="43394-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="43394-252">您也可以更新全域會議原則，此原則會影響所有未指派原則的使用者：</span><span class="sxs-lookup"><span data-stu-id="43394-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="43394-253">如需此命令的詳細資訊，請參閱 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="43394-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="43394-254">如果您需要在關閉 VbSS 後再開啟它 () 預設為開啟狀態，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="43394-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="43394-255">如需此命令的詳細資訊，請參閱 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="43394-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="43394-256">在多方商務用 Skype 會議中，所有用戶端端點都會遵循會議召集人的原則設定。</span><span class="sxs-lookup"><span data-stu-id="43394-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="43394-257">另請參閱</span><span class="sxs-lookup"><span data-stu-id="43394-257">See also</span></span>

[<span data-ttu-id="43394-258">商務用 Skype Server 2015 累計更新 KB3061064</span><span class="sxs-lookup"><span data-stu-id="43394-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="43394-259">在商務用 Skype Server 2015 中可使用以影片為基礎的螢幕共用 (VBSS) </span><span class="sxs-lookup"><span data-stu-id="43394-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)
