---
title: 規劃雲端連接器版中的媒體旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 請閱讀本主題, 以瞭解使用雲端連接器版本2.0 和更新版本來實現媒體旁路的規劃考慮。 如需有關部署媒體旁路的資訊, 請參閱在雲端連接器版本中部署媒體旁路。
ms.openlocfilehash: 00f700880e26f12da3aa6c2d791e4f15bfe9a90b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190720"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="5636f-104">規劃雲端連接器版中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="5636f-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="5636f-105">請閱讀本主題, 以瞭解使用雲端連接器版本2.0 和更新版本來實現媒體旁路的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="5636f-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="5636f-106">如需有關部署媒體旁路的資訊, 請參閱[在雲端連接器版本中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5636f-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="5636f-107">「媒體旁路」可讓用戶端直接傳送媒體至公用交換式電話網絡 (PSTN) 的下一個躍點 (閘道或會話邊界控制器 (SBC)), 並從媒體路徑中消除雲端連接器版本元件。</span><span class="sxs-lookup"><span data-stu-id="5636f-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="5636f-108">媒體旁路可減少延遲、造成資料包遺失的可能性, 以及可能失敗的點數, 以改善語音品質。</span><span class="sxs-lookup"><span data-stu-id="5636f-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="5636f-109">取消繞過呼叫的媒體處理會減少雲端連接器上的負載, 這可讓您獲得較高的併發通話次數, 而且可以改善可伸縮性。</span><span class="sxs-lookup"><span data-stu-id="5636f-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="5636f-110">從媒體處理工作中釋放雲端連接器可能會減少基礎結構所需的雲端連接器裝置數目, 因此您應該盡可能啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="5636f-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="5636f-111">媒體旁路如何影響媒體與信號路徑</span><span class="sxs-lookup"><span data-stu-id="5636f-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="5636f-112">當信號使用相同的路徑, 或沒有媒體旁路時, 媒體流程會有所不同。</span><span class="sxs-lookup"><span data-stu-id="5636f-112">While signaling takes the same path with or without media bypass, the media flow will differ.</span></span> <span data-ttu-id="5636f-113">下列圖表顯示拓撲中的媒體與信號路徑, 以及不使用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="5636f-113">The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="5636f-114">例如, 在下列拓撲 (不會使用媒體旁路) 中, 商務用 Skype 用戶端會將 PSTN 呼叫加入外部號碼、SIP 信號傳送到 Office 365, 而 Office 365 則會根據最終使用者的語音指示信號流量原則.</span><span class="sxs-lookup"><span data-stu-id="5636f-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Office 365, and Office 365 then directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="5636f-115">若是雲端連接器使用者, 語音原則會將信號流量導向雲端連接器 Edge 伺服器, 然後透過雲端連接器轉送伺服器將信號流量路由到 PSTN 會話邊界控制器 (SBC) 或閘道。</span><span class="sxs-lookup"><span data-stu-id="5636f-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="5636f-116">媒體從商務用 Skype 用戶端傳送到雲端連接器中繼伺服器, 然後移至 SBC 或閘道, 如下列圖表所示:</span><span class="sxs-lookup"><span data-stu-id="5636f-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5636f-117">**沒有媒體旁路的媒體與信號路徑**</span><span class="sxs-lookup"><span data-stu-id="5636f-117">**Media and signaling pathways without media bypass**</span></span>

![沒有媒體旁路的信號](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="5636f-119">從 PSTN 撥入電話會以相反的方向使用相同的傳送信號路徑。</span><span class="sxs-lookup"><span data-stu-id="5636f-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="5636f-120">對於內部使用者, 媒體仍會在商務用 Skype 用戶端和雲端連接器中繼伺服器以及 SBC 或閘道之間最終流動。</span><span class="sxs-lookup"><span data-stu-id="5636f-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="5636f-121">在下一個拓朴中 (這會採用媒體旁路), 信號會採用相同的路徑, 但媒體會直接在商務用 Skype 用戶端與 SBC 或閘道之間流動, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="5636f-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5636f-122">**使用媒體旁路的媒體與信號路徑**</span><span class="sxs-lookup"><span data-stu-id="5636f-122">**Media and signaling pathways with media bypass**</span></span>

![使用媒體旁路進行信號](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="5636f-124">多網站案例和媒體旁路</span><span class="sxs-lookup"><span data-stu-id="5636f-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="5636f-125">如果您想要使用單一雲端連接器裝置將電話語音提供給多個網站, 則媒體旁路也很有用。</span><span class="sxs-lookup"><span data-stu-id="5636f-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="5636f-126">因為雲端連接器無法根據來源或目的地號碼來傳送呼叫, 所以大部分的企業都會將 SBC 或閘道部署在雲端連接器背後, 以作出路由決定。</span><span class="sxs-lookup"><span data-stu-id="5636f-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="5636f-127">在這種情況下, 媒體旁路會消除用戶端與中央 SBC 或閘道之間的跳躍, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="5636f-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5636f-128">**多網站應用程式**</span><span class="sxs-lookup"><span data-stu-id="5636f-128">**Multi-site application**</span></span>

![雲端連接器多網站範例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="5636f-130">SIP 流量會從蘇黎世中的使用者流向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5636f-130">The SIP traffic flows from the user in Zurich to Office 365.</span></span>
    
2. <span data-ttu-id="5636f-131">然後, 通訊會按照使用者語音路由策略中指定的阿姆斯特丹, 路由到雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="5636f-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="5636f-132">[阿姆斯特丹] 中的雲端連接器裝置會將 SIP 流量, 以阿姆斯特丹傳送給中央閘道。</span><span class="sxs-lookup"><span data-stu-id="5636f-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="5636f-133">[阿姆斯特丹] 中的中央閘道會建立適當的路由決定, 然後將流量傳送到蘇黎世中的 SBC 或閘道, 而媒體則會直接在商務用 Skype 用戶端和 SBC 或閘道的阿姆斯特丹之間流動。</span><span class="sxs-lookup"><span data-stu-id="5636f-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="5636f-134">這個方法可讓您在每一個雲端連接器部署中, 以多個使用者為中心介面提供更多使用者。</span><span class="sxs-lookup"><span data-stu-id="5636f-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="5636f-135">即使已從媒體路徑中消除雲端連接器, 在集中式多網站案例中, 媒體仍可能會根據所需的兩倍來進行, 以流過集中的 SBC 或閘道。</span><span class="sxs-lookup"><span data-stu-id="5636f-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="5636f-136">如果用戶端位於公司網路外部的外部通話中, 媒體流量會透過來自于雲端連接器的邊緣和轉送伺服器以及蘇黎世與阿姆斯特丹之間的 WAN 連結來流動, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="5636f-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![雲端連接器多網站範例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="5636f-138">媒體略過支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="5636f-138">Supported clients for media bypass</span></span>

<span data-ttu-id="5636f-139">在第一次使用媒體旁路的情況下, 唯一支援的用戶端就是 Office 365 專業增強版、版本16.0.7870.2020 或更新版本中的商務用 Skype 2016 Windows 用戶端。</span><span class="sxs-lookup"><span data-stu-id="5636f-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Office 365 ProPlus, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="5636f-140">客戶可以使用任何通道: [目前]、[已推遲] 或 [第一次發行]。</span><span class="sxs-lookup"><span data-stu-id="5636f-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5636f-141">如果您使用的是用戶端 VPN 解決方案與商務用 Skype 用戶端, 則只有 VPN 分割隧道設定支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="5636f-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="5636f-142">如需發行通道的詳細資訊, 請參閱[Office 365 專業增強版更新通道的概覽](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="5636f-142">For more information about the release channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="5636f-143">針對不同通道中的目前發行版本用戶端, 請參閱[Office 365 專業增強版更新的版本資訊](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="5636f-143">For the current release version of the clients in different channels, see [Release information for updates to Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="5636f-144">媒體略過的雲端連接器容量考慮</span><span class="sxs-lookup"><span data-stu-id="5636f-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="5636f-145">如果沒有媒體旁路, 且視硬體而定, 雲端連接器裝置可以處理從50到500同時進行的呼叫, 需要透過中繼伺服器傳送媒體。</span><span class="sxs-lookup"><span data-stu-id="5636f-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="5636f-146">如需詳細資訊, 請參閱[規劃商務用 Skype 雲端連接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5636f-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="5636f-147">在啟用媒體旁路的情況下, 支援的版本上的內部用戶端不使用中繼伺服器, 因此內部用戶端數量可能會大幅增加。</span><span class="sxs-lookup"><span data-stu-id="5636f-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="5636f-148">如上所述, 外部用戶端或不受支援的用戶端將會使用雲端連接器邊緣和媒體的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5636f-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="5636f-149">計算網站中應該放置多少雲端連接器裝置的時間時, 您必須考慮來自外部使用者與不受支援之用戶端的使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="5636f-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="5636f-150">雲端連接器支援 Always 旁路模式</span><span class="sxs-lookup"><span data-stu-id="5636f-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="5636f-151">雲端連接器只支援 [總是略過模式]。</span><span class="sxs-lookup"><span data-stu-id="5636f-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="5636f-152">在內部部署環境中, 有兩種選項可供選擇: 總是略過並使用網站和區域資訊。</span><span class="sxs-lookup"><span data-stu-id="5636f-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="5636f-153">[永遠繞過] 表示系統會嘗試對內部用戶端的所有 PSTN 呼叫進行媒體略過, 成為來源或目的地點。</span><span class="sxs-lookup"><span data-stu-id="5636f-153">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point.</span></span> <span data-ttu-id="5636f-154">若要判斷用戶端是否為內部或外部用戶端, 則會使用中繼伺服器虛擬機器上的網站。</span><span class="sxs-lookup"><span data-stu-id="5636f-154">To determine if the client is internal or external, a web site on the mediation server virtual machine is used.</span></span> <span data-ttu-id="5636f-155">如果用戶端可以存取該網站, 就會將它視為內部, 並使用媒體略過。</span><span class="sxs-lookup"><span data-stu-id="5636f-155">If the client can reach the site, it is considered internal and media bypass is used.</span></span> <span data-ttu-id="5636f-156">如果用戶端無法存取該網站 (例如, 用戶端位於家用網路上), 則不會使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="5636f-156">If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="5636f-157">Always 旁路在使用者與 PSTN 網站內的 PSTN 閘道之間必須有障礙的連線性。</span><span class="sxs-lookup"><span data-stu-id="5636f-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="5636f-158">如需詳細資訊, 請參閱[規劃商務用 Skype 雲端連接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5636f-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="5636f-159">例如, 在下圖中, 歐洲使用者必須與三個會話邊界控制器 (SBCs) 以阿姆斯特丹的方式連接, 而我們的西部使用者必須在西雅圖的兩個半形中正確連接。</span><span class="sxs-lookup"><span data-stu-id="5636f-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="5636f-160">[良好連接] 表示它們位於與 SBCs 或閘道相同的網路網站, 或位於具備適當頻寬的 WAN 連結上。</span><span class="sxs-lookup"><span data-stu-id="5636f-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![雲端連接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="5636f-162">如果從蘇黎世的使用者移至西雅圖辦公室, 而您想要使用內部網路來傳送來自歐洲的旅遊使用者和閘道之間的媒體流量 (而不是透過網際網路), 您必須確認西雅圖辦公室和阿姆斯特丹歐洲的 [SBCs] 或 [閘道] 的 office 位於 [符合良好的連線]。</span><span class="sxs-lookup"><span data-stu-id="5636f-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="5636f-163">在媒體旁路中使用的編解碼器</span><span class="sxs-lookup"><span data-stu-id="5636f-163">Codecs used in media bypass</span></span>

<span data-ttu-id="5636f-164">在啟用媒體旁路的情況下, 用戶端與 SBC 或閘道之間的媒體流量會使用711編解碼器。</span><span class="sxs-lookup"><span data-stu-id="5636f-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5636f-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5636f-165">See also</span></span>

[<span data-ttu-id="5636f-166">在雲端連接器版本中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="5636f-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)
