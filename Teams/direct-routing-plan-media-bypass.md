---
title: 使用直接路由規劃媒體旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 請閱讀本主題, 以瞭解如何使用手機系統直接路由規劃媒體旁路。
ms.openlocfilehash: db236b1fadb4dcb13d5405402f469afee9eb2dac
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236596"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="0b003-103">使用直接路由規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b003-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="0b003-104">關於直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b003-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="0b003-105">[媒體旁路] 可讓您縮短媒體流量的路徑, 並減少傳輸中的跳躍數, 以獲得更佳的效能。</span><span class="sxs-lookup"><span data-stu-id="0b003-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="0b003-106">在媒體旁路的情況下, 媒體會保留在會話邊界控制器 (SBC) 和用戶端之間, 而不是透過 Microsoft Phone 系統傳送。</span><span class="sxs-lookup"><span data-stu-id="0b003-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="0b003-107">若要設定媒體旁路, SBC 與用戶端必須位於同一個位置或網路上。</span><span class="sxs-lookup"><span data-stu-id="0b003-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="0b003-108">您可以使用**設定 CSOnlinePSTNGateway**命令, 並將 **-MediaBypass**參數設定為 true 或 false, 以控制每個 SBC 的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0b003-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="0b003-109">如果您啟用 [媒體旁路], 這並不表示所有媒體流量都會留在公司網路內。</span><span class="sxs-lookup"><span data-stu-id="0b003-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="0b003-110">本文將說明不同案例中的通話流程。</span><span class="sxs-lookup"><span data-stu-id="0b003-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="0b003-111">下圖說明通話流程中的差異, 以及不使用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="0b003-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="0b003-112">若沒有媒體旁路, 當用戶端撥打或接聽來電時, 在 SBC、Microsoft Phone 系統和團隊用戶端之間的信號與媒體流程, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="0b003-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![顯示沒有媒體旁路的信號和媒體流程](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="0b003-114">但假設使用者與 SBC 在相同的大樓或 network 中。</span><span class="sxs-lookup"><span data-stu-id="0b003-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="0b003-115">例如, 假設在 Frankfurt 中建立的使用者撥打電話給 PSTN 使用者:</span><span class="sxs-lookup"><span data-stu-id="0b003-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="0b003-116">如果**沒有媒體旁路**, 媒體會透過阿姆斯特丹或都柏林 (在 Microsoft 資料中心的部署位置), 並回到 Frankfurt 中的 SBC 來流動。</span><span class="sxs-lookup"><span data-stu-id="0b003-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="0b003-117">之所以選取 [歐洲資料中心], 是因為 SBC 是在歐洲, 而 Microsoft 使用最接近 SBC 的資料中心。</span><span class="sxs-lookup"><span data-stu-id="0b003-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="0b003-118">雖然這種方法不會影響通話品質, 因為在大部分地區內的 Microsoft 網路中的流量流程已優化, 但通信量卻有不必要的迴圈。</span><span class="sxs-lookup"><span data-stu-id="0b003-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="0b003-119">在**媒體旁路**的情況下, 媒體會直接保留在團隊使用者與 SBC 之間, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="0b003-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![顯示使用媒體旁路的信號及媒體流程](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="0b003-121">媒體旁路利用在 SBC 上的團隊用戶端和 ICE lite 上稱為互動式連線建立 (ICE) 的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="0b003-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="0b003-122">這些通訊協定可讓直接路由使用最直接的媒體路徑來獲得最佳品質。</span><span class="sxs-lookup"><span data-stu-id="0b003-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="0b003-123">冰與冰 Lite 是 WebRTC 的標準。</span><span class="sxs-lookup"><span data-stu-id="0b003-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="0b003-124">如需這些通訊協定的詳細資訊, 請參閱 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="0b003-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="0b003-125">通話流程與防火牆規劃</span><span class="sxs-lookup"><span data-stu-id="0b003-125">Call flow and firewall planning</span></span>

<span data-ttu-id="0b003-126">通話流程和防火牆規劃取決於使用者是否能直接存取 SBC 的公用 IP 位址, 以及使用者是否在網路內或外部。</span><span class="sxs-lookup"><span data-stu-id="0b003-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="0b003-127">如果使用者可以直接存取 SBC 的公用 IP 位址, 就可以進行通話流程</span><span class="sxs-lookup"><span data-stu-id="0b003-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="0b003-128">如果使用者可以直接存取 SBC 的公用 IP 位址, 則呼叫流程如下所示:</span><span class="sxs-lookup"><span data-stu-id="0b003-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="0b003-129">針對媒體旁路, 小組用戶端必須能夠存取 SBC 的公用 IP 位址 (即使是來自內部網路)。</span><span class="sxs-lookup"><span data-stu-id="0b003-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="0b003-130">如果不想要直接媒體, 媒體可以透過傳輸中繼流過。</span><span class="sxs-lookup"><span data-stu-id="0b003-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="0b003-131">當使用者與 SBC 在相同的建築物和/或網路中時, 建議使用這項方案: 從媒體路徑中移除 Microsoft 雲端元件。</span><span class="sxs-lookup"><span data-stu-id="0b003-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="0b003-132">通知總是透過 Microsoft 雲端傳送流程。</span><span class="sxs-lookup"><span data-stu-id="0b003-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="0b003-133">下圖顯示啟用媒體旁路時的通話流程、用戶端為內部, 且用戶端可以取得 SBC 的公用 IP 位址 (直接媒體):</span><span class="sxs-lookup"><span data-stu-id="0b003-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="0b003-134">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="0b003-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="0b003-135">SIP 信號總是會採用路徑4和 4 ' (視通信量的方向而定)。</span><span class="sxs-lookup"><span data-stu-id="0b003-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="0b003-136">媒體保持在本機, 並採用路徑5b。</span><span class="sxs-lookup"><span data-stu-id="0b003-136">Media stays local and takes path 5b.</span></span>

![顯示已啟用媒體旁路的通話流程, 用戶端是內部的](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="0b003-138">如果使用者無法存取 SBC 的公用 IP 位址, 通話流程</span><span class="sxs-lookup"><span data-stu-id="0b003-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="0b003-139">如果使用者無法存取 SBC 的公用 IP 位址, 下列說明通話流程。</span><span class="sxs-lookup"><span data-stu-id="0b003-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="0b003-140">例如, 假設使用者是外部使用者, 而租使用者系統管理員決定不要將 SBC 的公用 IP 位址開啟至網際網路中的每個人, 但僅限 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="0b003-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="0b003-141">流量的內部元件可以透過團隊傳輸繼電器來流動。</span><span class="sxs-lookup"><span data-stu-id="0b003-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="0b003-142">這是商業網路以外的使用者的建議配置。</span><span class="sxs-lookup"><span data-stu-id="0b003-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="0b003-143">請考慮下列事項:</span><span class="sxs-lookup"><span data-stu-id="0b003-143">Consider the following:</span></span>

- <span data-ttu-id="0b003-144">使用團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="0b003-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="0b003-145">針對媒體旁路, Microsoft 使用的傳輸繼電器版本必須在團隊傳輸中繼器與 SBC 之間開啟埠 50 000 至 59 999 (將來我們打算移至只需要3478和3479埠的版本)。</span><span class="sxs-lookup"><span data-stu-id="0b003-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="0b003-146">針對媒體優化用途, Microsoft 建議您只開啟 SBC 的公用 IP 位址至團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="0b003-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="0b003-147">對於公司網路以外的用戶端, Microsoft 建議使用傳輸中繼, 而不是直接到達 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="0b003-148">下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為外部, 且用戶端無法取得會話邊界控制器的公用 IP 位址 (媒體是由小組傳輸轉接傳送來中繼)。</span><span class="sxs-lookup"><span data-stu-id="0b003-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="0b003-149">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="0b003-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="0b003-150">媒體是透過路徑3、3 '、4和4」進行中繼</span><span class="sxs-lookup"><span data-stu-id="0b003-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="0b003-152">如果使用者在網路以外且能存取 SBC 的公用 IP, 通話流程</span><span class="sxs-lookup"><span data-stu-id="0b003-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="0b003-153">這不是建議的設定, 因為它不會利用團隊傳輸繼電器。</span><span class="sxs-lookup"><span data-stu-id="0b003-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="0b003-154">相反地, 您應該考慮先前的情況, 即使用者無法存取 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="0b003-155">下圖顯示啟用媒體旁路時的通話流程、用戶端為外部, 且用戶端可以取得 SBC (直接媒體) 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="0b003-156">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="0b003-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="0b003-157">SIP 信號通常會採用路徑3和 3 ' (視流量方向而定)。</span><span class="sxs-lookup"><span data-stu-id="0b003-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="0b003-158">媒體流程使用路徑2。</span><span class="sxs-lookup"><span data-stu-id="0b003-158">Media flows using path 2.</span></span>

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="0b003-160">媒體處理器與傳輸繼電器的用途</span><span class="sxs-lookup"><span data-stu-id="0b003-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="0b003-161">Microsoft 雲端中有兩個元件可位於媒體流量的路徑: 媒體處理器和傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="0b003-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="0b003-162">媒體處理器是一個公開的元件, 可在非旁路情況下處理媒體, 並處理語音應用程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="0b003-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="0b003-163">媒體處理器一直在最終使用者未繞過呼叫的路徑中, 但不會在回避通話的路徑中。</span><span class="sxs-lookup"><span data-stu-id="0b003-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="0b003-164">媒體處理器總是位於所有語音應用程式的路徑中, 例如通話寄存、組織自動語音應答及通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0b003-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="0b003-165">傳輸中繼是用來連線到最接近的傳輸服務, 以傳送即時流量。</span><span class="sxs-lookup"><span data-stu-id="0b003-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="0b003-166">傳輸繼電器可能是或不在繞過通話的路徑中, 也可能不是來源於或發給最終使用者--視使用者的位置和網路的設定方式而定。</span><span class="sxs-lookup"><span data-stu-id="0b003-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="0b003-167">下圖顯示兩個通話流程: 一個啟用「媒體旁路」, 而另一個停用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="0b003-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="0b003-168">注意: 圖表只會說明源自--或發至端使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="0b003-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="0b003-169">媒體控制器是 Azure 中的 microservice, 可指派媒體處理器並建立會話描述通訊協定 (SDP) 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="0b003-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="0b003-170">SIP Proxy 是一個元件, 可將小組中使用的 HTTP REST 信號轉譯成 SIP。</span><span class="sxs-lookup"><span data-stu-id="0b003-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![顯示已啟用及停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="0b003-172">下表摘要列出媒體處理器與傳輸中繼之間的差異。</span><span class="sxs-lookup"><span data-stu-id="0b003-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="0b003-173">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="0b003-173">Media Processors</span></span> | <span data-ttu-id="0b003-174">傳輸繼電器</span><span class="sxs-lookup"><span data-stu-id="0b003-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="0b003-175">在媒體路徑中, 讓使用者無法避開來電</span><span class="sxs-lookup"><span data-stu-id="0b003-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="0b003-176">總會</span><span class="sxs-lookup"><span data-stu-id="0b003-176">Always</span></span> | <span data-ttu-id="0b003-177">任何</span><span class="sxs-lookup"><span data-stu-id="0b003-177">Never</span></span> | 
<span data-ttu-id="0b003-178">在媒體路徑中, 讓使用者略過來電</span><span class="sxs-lookup"><span data-stu-id="0b003-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="0b003-179">任何</span><span class="sxs-lookup"><span data-stu-id="0b003-179">Never</span></span> | <span data-ttu-id="0b003-180">如果用戶端無法在公用 IP 位址上到達 SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="0b003-181">在語音應用程式的媒體路徑中</span><span class="sxs-lookup"><span data-stu-id="0b003-181">In media path for voice applications</span></span> | <span data-ttu-id="0b003-182">總會</span><span class="sxs-lookup"><span data-stu-id="0b003-182">Always</span></span> | <span data-ttu-id="0b003-183">任何</span><span class="sxs-lookup"><span data-stu-id="0b003-183">Never</span></span> | 
<span data-ttu-id="0b003-184">可以執行轉碼 (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="0b003-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="0b003-185">是的</span><span class="sxs-lookup"><span data-stu-id="0b003-185">Yes</span></span> | <span data-ttu-id="0b003-186">否, 只在端點之間中繼音訊</span><span class="sxs-lookup"><span data-stu-id="0b003-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="0b003-187">全球和位置的實例數</span><span class="sxs-lookup"><span data-stu-id="0b003-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="0b003-188">總共8個: 美國東和西部為2。在阿姆斯特丹和都柏林中為 2,2在香港與新加坡中;日本中的 2 (在 Q1CY2019 中新增)</span><span class="sxs-lookup"><span data-stu-id="0b003-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="0b003-189">條</span><span class="sxs-lookup"><span data-stu-id="0b003-189">Multiple</span></span>

<span data-ttu-id="0b003-190">IP 範圍是 52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="0b003-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="0b003-191">\*轉碼說明:</span><span class="sxs-lookup"><span data-stu-id="0b003-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="0b003-192">媒體處理常式是 B2BUA, 這表示它可以變更編解碼器 (例如, 從 [團隊用戶端] 到 [MP] 和 [在 MP 與 SBC 之間 711] 的絞絲)。</span><span class="sxs-lookup"><span data-stu-id="0b003-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="0b003-193">傳輸中繼並非 B2BUA, 這表示在用戶端與 SBC 之間不會變更編解碼器, 即使流量透過中繼流程也一樣。</span><span class="sxs-lookup"><span data-stu-id="0b003-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="0b003-194">如果已針對媒體旁路設定幹線, 在問題上報案例中使用團隊傳輸繼電器</span><span class="sxs-lookup"><span data-stu-id="0b003-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="0b003-195">在下列案例中, 小組傳輸繼電器永遠都在媒體路徑中:</span><span class="sxs-lookup"><span data-stu-id="0b003-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="0b003-196">從1:1 升級到群組通話的通話</span><span class="sxs-lookup"><span data-stu-id="0b003-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="0b003-197">通話會傳送給聯盟團隊使用者</span><span class="sxs-lookup"><span data-stu-id="0b003-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="0b003-198">通話是轉寄或轉接至商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="0b003-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="0b003-199">請確定您的 SBC 能夠存取傳輸繼電器, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="0b003-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a><span data-ttu-id="0b003-200">SIP 信號: Fqdn 和防火牆埠</span><span class="sxs-lookup"><span data-stu-id="0b003-200">SIP Signaling: FQDNs and firewall ports</span></span>

<span data-ttu-id="0b003-201">針對 SIP 信號, FQDN 和防火牆需求與非繞過案例相同。</span><span class="sxs-lookup"><span data-stu-id="0b003-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="0b003-202">直接路由的連接點是下列三個 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="0b003-202">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="0b003-203">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="0b003-203">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="0b003-204">當 SBC 傳送要求來解析此名稱時, Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-204">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="0b003-205">作業是以資料中心的效能指標, 以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="0b003-205">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="0b003-206">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b003-206">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="0b003-207">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="0b003-207">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="0b003-208">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="0b003-208">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="0b003-209">您必須將這三個 Fqdn 放在一起, 才能:</span><span class="sxs-lookup"><span data-stu-id="0b003-209">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="0b003-210">提供最佳的使用體驗 (在所指派的 SBC 資料中心較少且最接近的情況下, 由查詢第一個 FQDN)。</span><span class="sxs-lookup"><span data-stu-id="0b003-210">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="0b003-211">在來自 SBC 的連線建立至遇到暫時問題的資料中心時, 提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="0b003-211">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="0b003-212">如需詳細資訊, 請參閱下方的容錯移轉機制。</span><span class="sxs-lookup"><span data-stu-id="0b003-212">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="0b003-213">Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**和**sip3.pstnhub.microsoft.com**將解析成下列其中一個 IP 位址:</span><span class="sxs-lookup"><span data-stu-id="0b003-213">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="0b003-214">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="0b003-214">52.114.148.0</span></span>
- <span data-ttu-id="0b003-215">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="0b003-215">52.114.132.46</span></span>
- <span data-ttu-id="0b003-216">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="0b003-216">52.114.75.24</span></span>
- <span data-ttu-id="0b003-217">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="0b003-217">52.114.76.76</span></span>
- <span data-ttu-id="0b003-218">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="0b003-218">52.114.7.24</span></span>
- <span data-ttu-id="0b003-219">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="0b003-219">52.114.14.70</span></span>

<span data-ttu-id="0b003-220">您將需要在防火牆中開啟所有這些 IP 位址的埠, 以允許傳入和傳出流量進出位址以進行寄件者。</span><span class="sxs-lookup"><span data-stu-id="0b003-220">You will need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="0b003-221">如果您的防火牆支援 DNS 名稱, FQDN **sip-all.pstnhub.microsoft.com**會解析為上述所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-221">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all the IP addresses above.</span></span> <span data-ttu-id="0b003-222">您必須使用下列埠:</span><span class="sxs-lookup"><span data-stu-id="0b003-222">You must use the following ports:</span></span>

| <span data-ttu-id="0b003-223">頻寬</span><span class="sxs-lookup"><span data-stu-id="0b003-223">Traffic</span></span> | <span data-ttu-id="0b003-224">從</span><span class="sxs-lookup"><span data-stu-id="0b003-224">From</span></span> | <span data-ttu-id="0b003-225">自</span><span class="sxs-lookup"><span data-stu-id="0b003-225">To</span></span> | <span data-ttu-id="0b003-226">來源埠</span><span class="sxs-lookup"><span data-stu-id="0b003-226">Source port</span></span> | <span data-ttu-id="0b003-227">目的地埠</span><span class="sxs-lookup"><span data-stu-id="0b003-227">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="0b003-228">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="0b003-228">SIP/TLS</span></span>| <span data-ttu-id="0b003-229">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="0b003-229">SIP Proxy</span></span> | <span data-ttu-id="0b003-230">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-230">SBC</span></span> | <span data-ttu-id="0b003-231">1024-65535</span><span class="sxs-lookup"><span data-stu-id="0b003-231">1024 - 65535</span></span> | <span data-ttu-id="0b003-232">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-232">Defined on the SBC</span></span> |
| <span data-ttu-id="0b003-233">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="0b003-233">SIP/TLS</span></span> | <span data-ttu-id="0b003-234">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-234">SBC</span></span> | <span data-ttu-id="0b003-235">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="0b003-235">SIP Proxy</span></span> | <span data-ttu-id="0b003-236">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-236">Defined on the SBC</span></span> | <span data-ttu-id="0b003-237">5061</span><span class="sxs-lookup"><span data-stu-id="0b003-237">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="0b003-238">媒體流量: IP 與埠範圍</span><span class="sxs-lookup"><span data-stu-id="0b003-238">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="0b003-239">如果用戶端無法使用公用 IP 位址到達 SBC, 則在 SBC 與團隊用戶端之間的媒體流量會流動 (如果有直接連線) 或透過團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="0b003-239">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="0b003-240">直接媒體流量的需求 (在團隊用戶端與 SBC 之間)</span><span class="sxs-lookup"><span data-stu-id="0b003-240">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="0b003-241">用戶端必須能夠存取指定的埠 (請參閱 table) 至 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-241">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="0b003-242">注意: 如果用戶端在內部網路中, 則媒體會流向 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-242">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="0b003-243">您可以在您的 NAT 裝置上設定 hairpinning, 讓交通永不離開商業網路裝置。</span><span class="sxs-lookup"><span data-stu-id="0b003-243">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="0b003-244">頻寬</span><span class="sxs-lookup"><span data-stu-id="0b003-244">Traffic</span></span> | <span data-ttu-id="0b003-245">從</span><span class="sxs-lookup"><span data-stu-id="0b003-245">From</span></span> | <span data-ttu-id="0b003-246">自</span><span class="sxs-lookup"><span data-stu-id="0b003-246">To</span></span> | <span data-ttu-id="0b003-247">來源埠</span><span class="sxs-lookup"><span data-stu-id="0b003-247">Source port</span></span> | <span data-ttu-id="0b003-248">目的地埠</span><span class="sxs-lookup"><span data-stu-id="0b003-248">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="0b003-249">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-249">UDP/SRTP</span></span> | <span data-ttu-id="0b003-250">端</span><span class="sxs-lookup"><span data-stu-id="0b003-250">Client</span></span> | <span data-ttu-id="0b003-251">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-251">SBC</span></span> | <span data-ttu-id="0b003-252">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="0b003-252">50 000 – 50 019</span></span>  | <span data-ttu-id="0b003-253">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-253">Defined on the SBC</span></span> |
| <span data-ttu-id="0b003-254">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-254">UDP/SRTP</span></span> | <span data-ttu-id="0b003-255">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-255">SBC</span></span> | <span data-ttu-id="0b003-256">端</span><span class="sxs-lookup"><span data-stu-id="0b003-256">Client</span></span> | <span data-ttu-id="0b003-257">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-257">Defined on the SBC</span></span> | <span data-ttu-id="0b003-258">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="0b003-258">50 000 – 50 019</span></span>  |


<span data-ttu-id="0b003-259">注意: 如果您的網路裝置會轉譯用戶端的來源埠, 請確定已在網路設備與 SBC 之間開啟已轉換的埠。</span><span class="sxs-lookup"><span data-stu-id="0b003-259">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="0b003-260">使用傳輸繼電器的需求</span><span class="sxs-lookup"><span data-stu-id="0b003-260">Requirements for using Transport Relays</span></span>

<span data-ttu-id="0b003-261">傳輸繼電器與媒體處理器在同一個範圍內 (針對非旁路情況): 52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="0b003-261">Transport Relays are in the same range as Media Processors (for non-bypass cases):  52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="0b003-262">小組傳輸繼電器的埠範圍如下表所示:</span><span class="sxs-lookup"><span data-stu-id="0b003-262">The port range of the Teams Transport Relays is shown in the following table:</span></span>


| <span data-ttu-id="0b003-263">頻寬</span><span class="sxs-lookup"><span data-stu-id="0b003-263">Traffic</span></span> | <span data-ttu-id="0b003-264">從</span><span class="sxs-lookup"><span data-stu-id="0b003-264">From</span></span> | <span data-ttu-id="0b003-265">自</span><span class="sxs-lookup"><span data-stu-id="0b003-265">To</span></span> | <span data-ttu-id="0b003-266">來源埠</span><span class="sxs-lookup"><span data-stu-id="0b003-266">Source port</span></span> | <span data-ttu-id="0b003-267">目的地埠</span><span class="sxs-lookup"><span data-stu-id="0b003-267">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="0b003-268">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-268">UDP/SRTP</span></span> | <span data-ttu-id="0b003-269">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="0b003-269">Transport Relay</span></span> | <span data-ttu-id="0b003-270">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-270">SBC</span></span> | <span data-ttu-id="0b003-271">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="0b003-271">50 000 -59 999</span></span>    | <span data-ttu-id="0b003-272">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-272">Defined on the SBC</span></span> |
| <span data-ttu-id="0b003-273">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-273">UDP/SRTP</span></span> | <span data-ttu-id="0b003-274">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-274">SBC</span></span> | <span data-ttu-id="0b003-275">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="0b003-275">Transport Relay</span></span> | <span data-ttu-id="0b003-276">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-276">Defined on the SBC</span></span> | <span data-ttu-id="0b003-277">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="0b003-277">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="0b003-278">注意: Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="0b003-278">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="0b003-279">因為 Microsoft 有兩個版本的傳輸繼電器, 所以需要下列各項:</span><span class="sxs-lookup"><span data-stu-id="0b003-279">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="0b003-280">v4, 只能與埠範圍 50 000 搭配 59 999</span><span class="sxs-lookup"><span data-stu-id="0b003-280">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="0b003-281">v6 是與埠3478、3479搭配使用</span><span class="sxs-lookup"><span data-stu-id="0b003-281">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="0b003-282">目前, 媒體旁路只支援 v4 版的傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="0b003-282">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="0b003-283">我們會在未來推出 v6 支援。</span><span class="sxs-lookup"><span data-stu-id="0b003-283">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="0b003-284">您需要開啟埠3478和3479以進行轉換。</span><span class="sxs-lookup"><span data-stu-id="0b003-284">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="0b003-285">當 Microsoft 使用媒體旁路支援 v6 傳輸中繼時, 您就不需要重新設定您的網路設備或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="0b003-285">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="0b003-286">使用媒體處理器的需求</span><span class="sxs-lookup"><span data-stu-id="0b003-286">Requirements for using media processors</span></span>

<span data-ttu-id="0b003-287">媒體處理器總是位於語音應用程式和網路 cleints 的媒體路徑中 (適用于 exampe, 小組 cleint 是 Edge 或 Google Chrome)。</span><span class="sxs-lookup"><span data-stu-id="0b003-287">Media Processors are always in the media path for voice applications and for Web cleints (for exampe, Teams cleint in Edge or Google Chrome).</span></span> <span data-ttu-id="0b003-288">其需求與非旁路設定相同。</span><span class="sxs-lookup"><span data-stu-id="0b003-288">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="0b003-289">媒體流量的 IP 範圍是 52.112.0.0/14 (從52.112.0.1 到52.115.255.254 的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="0b003-289">The IP range for media traffic is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="0b003-290">媒體處理器的埠範圍如下表所示:</span><span class="sxs-lookup"><span data-stu-id="0b003-290">The port range of the Media Processors is shown in the following table:</span></span>

| <span data-ttu-id="0b003-291">頻寬</span><span class="sxs-lookup"><span data-stu-id="0b003-291">Traffic</span></span> | <span data-ttu-id="0b003-292">從</span><span class="sxs-lookup"><span data-stu-id="0b003-292">From</span></span> | <span data-ttu-id="0b003-293">自</span><span class="sxs-lookup"><span data-stu-id="0b003-293">To</span></span> | <span data-ttu-id="0b003-294">來源埠</span><span class="sxs-lookup"><span data-stu-id="0b003-294">Source port</span></span> | <span data-ttu-id="0b003-295">目的地埠</span><span class="sxs-lookup"><span data-stu-id="0b003-295">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="0b003-296">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-296">UDP/SRTP</span></span> | <span data-ttu-id="0b003-297">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="0b003-297">Media Processor</span></span> | <span data-ttu-id="0b003-298">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-298">SBC</span></span> | <span data-ttu-id="0b003-299">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="0b003-299">49 152 – 53 247</span></span>    | <span data-ttu-id="0b003-300">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-300">Defined on the SBC</span></span> |
| <span data-ttu-id="0b003-301">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="0b003-301">UDP/SRTP</span></span> | <span data-ttu-id="0b003-302">SBC</span><span class="sxs-lookup"><span data-stu-id="0b003-302">SBC</span></span> | <span data-ttu-id="0b003-303">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="0b003-303">Media Processor</span></span> | <span data-ttu-id="0b003-304">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="0b003-304">Defined on the SBC</span></span> | <span data-ttu-id="0b003-305">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="0b003-305">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="0b003-306">如果您在網路上有商務用 Skype 電話, 請考慮</span><span class="sxs-lookup"><span data-stu-id="0b003-306">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="0b003-307">如果您的網路中有任何使用 [直接傳送] 的商務用 Skype 端點 (例如, 小組使用者可以擁有以商務用 Skype 用戶端為基礎的3PIP 電話), 則必須關閉為這些使用者提供服務的主幹上的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0b003-307">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="0b003-308">您可以為這些使用者建立單獨的幹線, 並將其指派為線上語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="0b003-308">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="0b003-309">高層次的設定步驟:</span><span class="sxs-lookup"><span data-stu-id="0b003-309">High-level configuration steps:</span></span>

- <span data-ttu-id="0b003-310">依類型分割使用者-視使用者是否有3PIP 電話而定。</span><span class="sxs-lookup"><span data-stu-id="0b003-310">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="0b003-311">使用不同的 Fqdn 建立兩個不同的 trunks: 一個為媒體略過啟用;另一種是。</span><span class="sxs-lookup"><span data-stu-id="0b003-311">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="0b003-312">兩個 trunks 都指向同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="0b003-312">Both trunks point to the same SBC.</span></span> <span data-ttu-id="0b003-313">TLS SIP 信號的埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="0b003-313">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="0b003-314">媒體埠必須相同。</span><span class="sxs-lookup"><span data-stu-id="0b003-314">The ports for media must be the same.</span></span>

- <span data-ttu-id="0b003-315">根據線上語音路由策略中的使用者類型, 指派正確的主幹。</span><span class="sxs-lookup"><span data-stu-id="0b003-315">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="0b003-316">下列範例說明這個邏輯。</span><span class="sxs-lookup"><span data-stu-id="0b003-316">The example below illustrates this logic.</span></span>

| <span data-ttu-id="0b003-317">使用者組</span><span class="sxs-lookup"><span data-stu-id="0b003-317">Set of users</span></span> | <span data-ttu-id="0b003-318">使用者數量</span><span class="sxs-lookup"><span data-stu-id="0b003-318">Number of users</span></span> | <span data-ttu-id="0b003-319">在 OVRP 中指派中繼 FQDN</span><span class="sxs-lookup"><span data-stu-id="0b003-319">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="0b003-320">已啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b003-320">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="0b003-321">擁有團隊用戶端與3PIP 手機的使用者</span><span class="sxs-lookup"><span data-stu-id="0b003-321">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="0b003-322">20</span><span class="sxs-lookup"><span data-stu-id="0b003-322">20</span></span> | <span data-ttu-id="0b003-323">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="0b003-323">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="0b003-324">虛假</span><span class="sxs-lookup"><span data-stu-id="0b003-324">false</span></span> | 
<span data-ttu-id="0b003-325">只有團隊結束點的使用者 (包括為小組認證的新電話)</span><span class="sxs-lookup"><span data-stu-id="0b003-325">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="0b003-326">980</span><span class="sxs-lookup"><span data-stu-id="0b003-326">980</span></span> | <span data-ttu-id="0b003-327">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="0b003-327">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="0b003-328">滿足</span><span class="sxs-lookup"><span data-stu-id="0b003-328">true</span></span>

<span data-ttu-id="0b003-329">兩個 trunks 都可以指向相同的同一個 SBC, 且具有相同的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0b003-329">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="0b003-330">SBC 上的 TLS 信號埠必須不同, 如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="0b003-330">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="0b003-331">注意: 您必須確認您的憑證同時支援這兩個 trunks。</span><span class="sxs-lookup"><span data-stu-id="0b003-331">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="0b003-332">在 SAN 中, 您必須有兩個名稱 (**sbc1.contoso.com**和**sbc2.contoso.com**), 或是擁有萬用字元證書。</span><span class="sxs-lookup"><span data-stu-id="0b003-332">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![顯示兩個 trunks 可以指向同一個公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="0b003-334">如需如何在同一個 SBC 上設定兩個 trunks 的相關資訊, 請參閱您的 SBC 轉銷商提供的檔:</span><span class="sxs-lookup"><span data-stu-id="0b003-334">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="0b003-335">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="0b003-335">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="0b003-336">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="0b003-336">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="0b003-337">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="0b003-337">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="0b003-338">TE-系統 (anynode) 部署檔</span><span class="sxs-lookup"><span data-stu-id="0b003-338">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="0b003-339">媒體略過支援的用戶端端點</span><span class="sxs-lookup"><span data-stu-id="0b003-339">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="0b003-340">所有團隊端點都支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0b003-340">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="0b003-341">Webcleints (Microsoft Edge、Google Chrome 或 Mozilla Firefox) 中的 [團隊網頁應用程式], 我們會將呼叫轉換成非旁路, 即使它是繞過通話。</span><span class="sxs-lookup"><span data-stu-id="0b003-341">Note for webcleints (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even of it started as a bypass call.</span></span> <span data-ttu-id="0b003-342">這會自動發生, 不需要系統管理員執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="0b003-342">This happens automatically and does not require any actions on the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="0b003-343">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b003-343">See also</span></span>

[<span data-ttu-id="0b003-344">使用直接路由來設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0b003-344">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



