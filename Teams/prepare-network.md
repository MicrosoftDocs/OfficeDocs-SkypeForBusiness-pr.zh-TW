---
title: 為 Microsoft 團隊準備貴組織的網路
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: 瞭解如何準備及管理您的 Microsoft 團隊網路。 資訊包括網路需求、頻寬需求, 以及其他考慮。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 041c391f202ac42b782ffc200db9ad495961fa52
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207149"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="30724-104">為 Microsoft 團隊準備貴組織的網路</span><span class="sxs-lookup"><span data-stu-id="30724-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="30724-105">團隊結合三種形式的流量:</span><span class="sxs-lookup"><span data-stu-id="30724-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="30724-106">Office 365 線上環境與團隊用戶端之間的資料流量 ([通知]、[目前狀態]、[聊天]、檔案上傳和下載、OneNote 同步處理)。</span><span class="sxs-lookup"><span data-stu-id="30724-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="30724-107">對等即時通訊流量 (音訊、影片、桌面共用)。</span><span class="sxs-lookup"><span data-stu-id="30724-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="30724-108">會議即時通訊流量 (音訊、影片、桌面共用)。</span><span class="sxs-lookup"><span data-stu-id="30724-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="30724-109">這會影響兩個層次上的網路: 流量會直接在 Microsoft 團隊用戶端與對等案例之間流動, 且流量將在 Office 365 環境與 Microsoft 團隊用戶端之間流動, 以進行會議案例。</span><span class="sxs-lookup"><span data-stu-id="30724-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="30724-110">為確保最佳流量流程, 必須允許流量在內部網路區段 (例如, 在 WAN 之間的網站之間) 以及網路網站與 Office 365 之間流動。</span><span class="sxs-lookup"><span data-stu-id="30724-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="30724-111">無法開啟正確的埠或主動封鎖特定的埠, 可能會造成降級的體驗。</span><span class="sxs-lookup"><span data-stu-id="30724-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="30724-112">IOS 和 Android 行動裝置支援會議。</span><span class="sxs-lookup"><span data-stu-id="30724-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="30724-113">若要在 Microsoft 團隊中取得即時媒體的最佳體驗, 您的網路必須符合 Office 365 的網路需求。</span><span class="sxs-lookup"><span data-stu-id="30724-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="30724-114">如需詳細資訊, 請參閱[商務用 Skype Online 的媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。</span><span class="sxs-lookup"><span data-stu-id="30724-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="30724-115">針對這兩個定義網段 (用戶端到 microsoft edge, 以及客戶邊緣至 Microsoft Edge), 請考慮下列建議。</span><span class="sxs-lookup"><span data-stu-id="30724-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="30724-116">值</span><span class="sxs-lookup"><span data-stu-id="30724-116">Value</span></span>  |<span data-ttu-id="30724-117">用戶端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30724-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="30724-118">客戶邊緣到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30724-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="30724-119">**延遲 (一種方式)**\*</span><span class="sxs-lookup"><span data-stu-id="30724-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="30724-120">< 50ms</span><span class="sxs-lookup"><span data-stu-id="30724-120">< 50ms</span></span>          |<span data-ttu-id="30724-121">< 30ms</span><span class="sxs-lookup"><span data-stu-id="30724-121">< 30ms</span></span>         |
|<span data-ttu-id="30724-122">**延遲 (RTT 或往返時間)**\*</span><span class="sxs-lookup"><span data-stu-id="30724-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="30724-123">< 100ms</span><span class="sxs-lookup"><span data-stu-id="30724-123">< 100ms</span></span>   |<span data-ttu-id="30724-124">< 60ms</span><span class="sxs-lookup"><span data-stu-id="30724-124">< 60ms</span></span> |
|<span data-ttu-id="30724-125">**突發資料包遺失**</span><span class="sxs-lookup"><span data-stu-id="30724-125">**Burst packet loss**</span></span>    |<span data-ttu-id="30724-126">在任何200ms 間隔期間, <10%</span><span class="sxs-lookup"><span data-stu-id="30724-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="30724-127">在任何200ms 間隔期間, <1%</span><span class="sxs-lookup"><span data-stu-id="30724-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="30724-128">**資料包遺失**</span><span class="sxs-lookup"><span data-stu-id="30724-128">**Packet loss**</span></span>     |<span data-ttu-id="30724-129">在任何15s 間隔期間, <1%</span><span class="sxs-lookup"><span data-stu-id="30724-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="30724-130">在任何15s 間隔期間, <0.1%</span><span class="sxs-lookup"><span data-stu-id="30724-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="30724-131">**資料包內部到達抖動**</span><span class="sxs-lookup"><span data-stu-id="30724-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="30724-132">在任何15s 間隔期間 <30ms</span><span class="sxs-lookup"><span data-stu-id="30724-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="30724-133">在任何15s 間隔期間 <15ms</span><span class="sxs-lookup"><span data-stu-id="30724-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="30724-134">**資料包重新排序**</span><span class="sxs-lookup"><span data-stu-id="30724-134">**Packet reorder**</span></span>    |<span data-ttu-id="30724-135"><0.05% 的順序外資料包</span><span class="sxs-lookup"><span data-stu-id="30724-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="30724-136"><0.01% 的順序外資料包</span><span class="sxs-lookup"><span data-stu-id="30724-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="30724-137">\*延遲量度目標假設您的公司網站或網站, 而且 Microsoft 邊緣位於同一個洲上。</span><span class="sxs-lookup"><span data-stu-id="30724-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="30724-138">您的 Microsoft 網路 edge 的公司網站連線包含第一個躍點網路存取, 這可以是 WiFi 或其他無線技術。</span><span class="sxs-lookup"><span data-stu-id="30724-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="30724-139">網路效能目標會採用適當的頻寬與/或[QoS 規劃](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="30724-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="30724-140">換句話說, 當網路連線達到峰值負載時, 這些需求會直接套用至團隊即時媒體流量。</span><span class="sxs-lookup"><span data-stu-id="30724-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="30724-141">如需針對團隊準備網路的詳細說明, 請參閱[網路 Planner](https://docs.microsoft.com/microsoftteams/network-planner)。</span><span class="sxs-lookup"><span data-stu-id="30724-141">For more help with preparing your network for Teams, check out [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="30724-142">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="30724-142">Bandwidth requirements</span></span>
<span data-ttu-id="30724-143">無論您的網路狀況為何, Microsoft 團隊都能提供最佳的音訊、影片和內容共用體驗。</span><span class="sxs-lookup"><span data-stu-id="30724-143">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="30724-144">有了可變的編解碼器, 就可以在有限的頻寬環境中協商媒體, 且影響極小。</span><span class="sxs-lookup"><span data-stu-id="30724-144">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="30724-145">但在頻寬不是一個重要問題時, 體驗可以針對品質進行優化, 包括最高解析度 (含1080p 解析度), 最多30fps 影片和15fps 內容, 以及高保真音訊。</span><span class="sxs-lookup"><span data-stu-id="30724-145">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="30724-146">其他網路考慮</span><span class="sxs-lookup"><span data-stu-id="30724-146">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="30724-147">外部名稱解析</span><span class="sxs-lookup"><span data-stu-id="30724-147">External Name Resolution</span></span>

<span data-ttu-id="30724-148">請確定執行團隊用戶端的所有用戶端電腦都可以解析外部 DNS 查詢, 以探索 Office 365 提供的服務, 而且您的防火牆無法防止存取。</span><span class="sxs-lookup"><span data-stu-id="30724-148">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="30724-149">如需設定防火牆埠的相關資訊, 請移至[Office 365 url 與 IP 範圍](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="30724-149">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="30724-150">NAT 池子大小</span><span class="sxs-lookup"><span data-stu-id="30724-150">NAT Pool Size</span></span>

<span data-ttu-id="30724-151">當多個使用者/裝置使用網路位址轉譯 (NAT) 或埠位址轉換 (PAT) 存取 Office 365 時, 您必須確保隱藏在每個公開路由的 IP 位址後面的裝置不會超過支援的號碼。</span><span class="sxs-lookup"><span data-stu-id="30724-151">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="30724-152">若要緩解此風險, 請確保已將充足的公用 IP 位址指派給 NAT 池, 以避免埠耗盡。</span><span class="sxs-lookup"><span data-stu-id="30724-152">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="30724-153">埠耗盡會導致內部使用者和裝置在連線至 Office 365 服務時面臨問題。</span><span class="sxs-lookup"><span data-stu-id="30724-153">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="30724-154">如需詳細資訊, 請參閱[Office 365 的 NAT 支援](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。</span><span class="sxs-lookup"><span data-stu-id="30724-154">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="30724-155">**入侵偵測與防範指導方針**</span><span class="sxs-lookup"><span data-stu-id="30724-155">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="30724-156">如果您的環境針對外部連線安全層級部署了入侵偵測及/或防護系統 (IDS/IPS), 請確定任何具有目的地至 Office 365 Url 的流量都是白名單。</span><span class="sxs-lookup"><span data-stu-id="30724-156">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="30724-157">網路狀況判斷</span><span class="sxs-lookup"><span data-stu-id="30724-157">Network health determination</span></span>
-----------------

<span data-ttu-id="30724-158">規劃您網路中的 Microsoft 團隊實施時, 您必須確保您具備所需的頻寬, 您可以存取所有必要的 IP 位址、已開啟正確的埠, 以及滿足即時媒體的效能需求.</span><span class="sxs-lookup"><span data-stu-id="30724-158">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="30724-159">如果您知道您不符合這些準則, 您的使用者將無法在通話和會議期間因品質差而從小組獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="30724-159">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="30724-160">如果您不符合這些準則, 這是考慮暫停專案以確保您在繼續之前符合準則的時間。</span><span class="sxs-lookup"><span data-stu-id="30724-160">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![代表決策點的圖示](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="30724-162">決策點</span><span class="sxs-lookup"><span data-stu-id="30724-162">Decision Point</span></span>         |<span data-ttu-id="30724-163">您是否已評估您的網路功能以支援即時媒體？</span><span class="sxs-lookup"><span data-stu-id="30724-163">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="30724-164">如果您的網路未正確評定, 或是您知道它不支援即時媒體, 您會停用影片和螢幕共用功能來減少網路影響與不佳的團隊體驗嗎？</span><span class="sxs-lookup"><span data-stu-id="30724-164">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![代表後續步驟的圖示](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="30724-166">後續步驟</span><span class="sxs-lookup"><span data-stu-id="30724-166">Next Steps</span></span>         |<span data-ttu-id="30724-167">網路品質未知: 執行網路就緒評估, 以判斷您的網路是否已準備好使用即時媒體。</span><span class="sxs-lookup"><span data-stu-id="30724-167">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="30724-168">網路品質差: 執行網路修正步驟, 為高品質即時媒體提供適當的環境。</span><span class="sxs-lookup"><span data-stu-id="30724-168">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="30724-169">網路滿意: 確保所有 IP 位址和埠都能正確存取。</span><span class="sxs-lookup"><span data-stu-id="30724-169">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="30724-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="30724-170">Related Topics</span></span>

[<span data-ttu-id="30724-171">影片: 網路規劃</span><span class="sxs-lookup"><span data-stu-id="30724-171">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
