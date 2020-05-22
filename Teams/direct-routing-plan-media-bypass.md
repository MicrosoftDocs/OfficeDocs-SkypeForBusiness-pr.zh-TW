---
title: 媒體旁路搭配直接路由方案
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何使用 [電話系統直接路由] 規劃媒體旁路，這可讓您縮短媒體流量的路徑，並改善效能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a4f8995c3972da8fd2d060b7083edb61138b97ac
ms.sourcegitcommit: f63cf7fdde333a7cb36c39e9b6cdc33afd2b4601
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2020
ms.locfileid: "44338243"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="c3e5f-103">媒體旁路搭配直接路由方案</span><span class="sxs-lookup"><span data-stu-id="c3e5f-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="c3e5f-104">關於直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="c3e5f-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="c3e5f-105">[媒體旁路] 可讓您縮短媒體流量的路徑，並減少傳輸中的跳躍數，以獲得更佳的效能。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="c3e5f-106">在媒體旁路的情況下，媒體會保留在會話邊界控制器（SBC）和用戶端之間，而不是透過 Microsoft Phone 系統傳送。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="c3e5f-107">若要設定媒體旁路，SBC 與用戶端必須位於同一個位置或網路上。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="c3e5f-108">您可以使用**設定 CSOnlinePSTNGateway**命令，並將 **-MediaBypass**參數設定為 true 或 false，以控制每個 SBC 的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="c3e5f-109">如果您啟用 [媒體旁路]，這並不表示所有媒體流量都會留在公司網路內。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="c3e5f-110">本文將說明不同案例中的通話流程。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="c3e5f-111">下圖說明通話流程中的差異，以及不使用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="c3e5f-112">若沒有媒體旁路，當用戶端撥打或接聽來電時，在 SBC、Microsoft Phone 系統和團隊用戶端之間的信號與媒體流程，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![顯示沒有媒體旁路的信號和媒體流程](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="c3e5f-114">但假設使用者與 SBC 在相同的大樓或 network 中。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="c3e5f-115">例如，假設在 Frankfurt 中建立的使用者撥打電話給 PSTN 使用者：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="c3e5f-116">如果**沒有媒體旁路**，媒體會透過阿姆斯特丹或都柏林（在 Microsoft 資料中心的部署位置），並回到 Frankfurt 中的 SBC 來流動。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="c3e5f-117">之所以選取 [歐洲資料中心]，是因為 SBC 是在歐洲，而 Microsoft 使用最接近 SBC 的資料中心。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="c3e5f-118">雖然這種方法不會影響通話品質，因為在大部分地區內的 Microsoft 網路中的流量流程已優化，但通信量卻有不必要的迴圈。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="c3e5f-119">在**媒體旁路**的情況下，媒體會直接保留在團隊使用者與 SBC 之間，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![顯示使用媒體旁路的信號及媒體流程](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="c3e5f-121">媒體旁路利用在 SBC 上的團隊用戶端和 ICE lite 上稱為互動式連線建立（ICE）的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="c3e5f-122">這些通訊協定可讓直接路由使用最直接的媒體路徑來獲得最佳品質。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="c3e5f-123">冰與冰 Lite 是 WebRTC 的標準。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="c3e5f-124">如需這些通訊協定的詳細資訊，請參閱 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="c3e5f-125">通話流程與防火牆規劃</span><span class="sxs-lookup"><span data-stu-id="c3e5f-125">Call flow and firewall planning</span></span>

<span data-ttu-id="c3e5f-126">通話流程和防火牆規劃取決於使用者是否能直接存取 SBC 的公用 IP 位址，以及使用者是否在網路內或外部。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="c3e5f-127">如果使用者可以直接存取 SBC 的公用 IP 位址，就可以進行通話流程</span><span class="sxs-lookup"><span data-stu-id="c3e5f-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="c3e5f-128">如果使用者可以直接存取 SBC 的公用 IP 位址，則呼叫流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="c3e5f-129">針對媒體旁路，小組用戶端必須能夠存取 SBC 的公用 IP 位址（即使是來自內部網路）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="c3e5f-130">如果不想要直接媒體，媒體可以透過傳輸中繼流過。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="c3e5f-131">當使用者與 SBC 在相同的建築物和/或網路中時，建議使用這項方案：從媒體路徑中移除 Microsoft 雲端元件。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="c3e5f-132">通知總是透過 Microsoft 雲端傳送流程。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="c3e5f-133">下圖顯示啟用媒體旁路時的通話流程、用戶端為內部，且用戶端可以取得 SBC 的公用 IP 位址（直接媒體）：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="c3e5f-134">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c3e5f-135">SIP 信號總是會採用路徑4和 4 ' （視通信量的方向而定）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="c3e5f-136">媒體保持在本機，並採用路徑5b。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-136">Media stays local and takes path 5b.</span></span>

![顯示已啟用媒體旁路的通話流程，用戶端是內部的](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="c3e5f-138">如果使用者無法存取 SBC 的公用 IP 位址，通話流程</span><span class="sxs-lookup"><span data-stu-id="c3e5f-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="c3e5f-139">如果使用者無法存取 SBC 的公用 IP 位址，下列說明通話流程。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="c3e5f-140">例如，假設使用者是外部使用者，而租使用者系統管理員決定不要將 SBC 的公用 IP 位址開啟至網際網路中的每個人，但僅限 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="c3e5f-141">流量的內部元件可以透過團隊傳輸繼電器來流動。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="c3e5f-142">這是商業網路以外的使用者的建議配置。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="c3e5f-143">請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-143">Consider the following:</span></span>

- <span data-ttu-id="c3e5f-144">使用團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="c3e5f-145">針對媒體旁路，Microsoft 使用的傳輸繼電器版本必須在團隊傳輸中繼器與 SBC 之間開啟埠 50 000 至 59 999 （將來我們打算移至只需要3478和3479埠的版本）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="c3e5f-146">針對媒體優化用途，Microsoft 建議您只開啟 SBC 的公用 IP 位址至團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="c3e5f-147">對於公司網路以外的用戶端，Microsoft 建議使用傳輸中繼，而不是直接到達 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="c3e5f-148">下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為外部，且用戶端無法取得會話邊界控制器的公用 IP 位址（媒體是由小組傳輸轉接傳送來中繼）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="c3e5f-149">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c3e5f-150">媒體是透過路徑3、3 '、4和4」進行中繼</span><span class="sxs-lookup"><span data-stu-id="c3e5f-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="c3e5f-152">如果使用者在網路以外且能存取 SBC 的公用 IP，通話流程</span><span class="sxs-lookup"><span data-stu-id="c3e5f-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="c3e5f-153">這不是建議的設定，因為它不會利用團隊傳輸繼電器。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="c3e5f-154">相反地，您應該考慮先前的情況，即使用者無法存取 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="c3e5f-155">下圖顯示啟用媒體旁路時的通話流程、用戶端為外部，且用戶端可以取得 SBC （直接媒體）的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="c3e5f-156">路徑的箭號和數值是依照[Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c3e5f-157">SIP 信號通常會採用路徑3和 3 ' （視流量方向而定）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-157">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="c3e5f-158">媒體流程使用路徑2。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-158">Media flows using path 2.</span></span>

![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="c3e5f-160">媒體處理器與傳輸繼電器的用途</span><span class="sxs-lookup"><span data-stu-id="c3e5f-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="c3e5f-161">Microsoft 雲端中有兩個元件可位於媒體流量的路徑：媒體處理器和傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="c3e5f-162">媒體處理器是一個公開的元件，可在非旁路情況下處理媒體，並處理語音應用程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="c3e5f-163">媒體處理器一直在最終使用者未繞過呼叫的路徑中，但不會在回避通話的路徑中。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="c3e5f-164">媒體處理器總是位於所有語音應用程式的路徑中，例如通話寄存、組織自動語音應答及通話佇列。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="c3e5f-165">傳輸中繼是用來連線到最接近的傳輸服務，以傳送即時流量。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="c3e5f-166">傳輸繼電器可能是或不在繞過通話的路徑中，也可能不是來源於或發給最終使用者--視使用者的位置和網路的設定方式而定。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="c3e5f-167">下圖顯示兩個通話流程：一個啟用「媒體旁路」，而另一個停用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="c3e5f-168">注意：圖表只會說明源自--或發至端使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="c3e5f-169">媒體控制器是 Azure 中的 microservice，可指派媒體處理器並建立會話描述通訊協定（SDP）提供的功能。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="c3e5f-170">SIP Proxy 是一個元件，可將小組中使用的 HTTP REST 信號轉譯成 SIP。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![顯示已啟用及停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="c3e5f-172">下表摘要列出媒體處理器與傳輸中繼之間的差異。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="c3e5f-173">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="c3e5f-173">Media Processors</span></span> | <span data-ttu-id="c3e5f-174">傳輸繼電器</span><span class="sxs-lookup"><span data-stu-id="c3e5f-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="c3e5f-175">在媒體路徑中，讓使用者無法避開來電</span><span class="sxs-lookup"><span data-stu-id="c3e5f-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="c3e5f-176">總會</span><span class="sxs-lookup"><span data-stu-id="c3e5f-176">Always</span></span> | <span data-ttu-id="c3e5f-177">任何</span><span class="sxs-lookup"><span data-stu-id="c3e5f-177">Never</span></span> | 
<span data-ttu-id="c3e5f-178">在媒體路徑中，讓使用者略過來電</span><span class="sxs-lookup"><span data-stu-id="c3e5f-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="c3e5f-179">任何</span><span class="sxs-lookup"><span data-stu-id="c3e5f-179">Never</span></span> | <span data-ttu-id="c3e5f-180">如果用戶端無法在公用 IP 位址上到達 SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="c3e5f-181">在語音應用程式的媒體路徑中</span><span class="sxs-lookup"><span data-stu-id="c3e5f-181">In media path for voice applications</span></span> | <span data-ttu-id="c3e5f-182">總會</span><span class="sxs-lookup"><span data-stu-id="c3e5f-182">Always</span></span> | <span data-ttu-id="c3e5f-183">任何</span><span class="sxs-lookup"><span data-stu-id="c3e5f-183">Never</span></span> | 
<span data-ttu-id="c3e5f-184">可以執行轉碼（B2BUA）\*</span><span class="sxs-lookup"><span data-stu-id="c3e5f-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="c3e5f-185">是</span><span class="sxs-lookup"><span data-stu-id="c3e5f-185">Yes</span></span> | <span data-ttu-id="c3e5f-186">否，只在端點之間中繼音訊</span><span class="sxs-lookup"><span data-stu-id="c3e5f-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="c3e5f-187">全球和位置的實例數</span><span class="sxs-lookup"><span data-stu-id="c3e5f-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="c3e5f-188">總共8個：美國東和西部為2。在阿姆斯特丹和都柏林中為2，2在香港與新加坡中;日文中的2</span><span class="sxs-lookup"><span data-stu-id="c3e5f-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="c3e5f-189">條</span><span class="sxs-lookup"><span data-stu-id="c3e5f-189">Multiple</span></span>

<span data-ttu-id="c3e5f-190">IP 範圍包括：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-190">The IP ranges are:</span></span>
- <span data-ttu-id="c3e5f-191">52.112.0.0/14 （從52.112.0.1 到52.115.255.254 的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="c3e5f-191">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="c3e5f-192">52.120.0.0/14 （從52.120.0.1 到52.123.255.254 的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="c3e5f-192">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="c3e5f-193">\*轉碼說明：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-193">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="c3e5f-194">媒體處理常式是 B2BUA，這表示它可以變更編解碼器（例如，從 [團隊用戶端] 到 [MP] 和 [在 MP 與 SBC 之間 711] 的絞絲）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-194">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="c3e5f-195">傳輸中繼並非 B2BUA，這表示在用戶端與 SBC 之間不會變更編解碼器，即使流量透過中繼流程也一樣。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-195">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="c3e5f-196">如果將幹線設定為媒體旁路，則使用團隊媒體處理器</span><span class="sxs-lookup"><span data-stu-id="c3e5f-196">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="c3e5f-197">團隊媒體處理器在下列情況下，會一直插入媒體路徑：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-197">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="c3e5f-198">從1:1 升級到群組通話的通話</span><span class="sxs-lookup"><span data-stu-id="c3e5f-198">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="c3e5f-199">通話會傳送給聯盟團隊使用者</span><span class="sxs-lookup"><span data-stu-id="c3e5f-199">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="c3e5f-200">通話是轉寄或轉接至商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="c3e5f-200">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="c3e5f-201">請確定您的 SBC 有權存取媒體處理器與傳輸中繼範圍，如下所述。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-201">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="c3e5f-202">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="c3e5f-202">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="c3e5f-203">針對 SIP 信號，FQDN 和防火牆需求與非繞過案例相同。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-203">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="c3e5f-204">在下列 Office 365 環境中提供直接路由：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-204">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="c3e5f-205">Office 365</span><span class="sxs-lookup"><span data-stu-id="c3e5f-205">Office 365</span></span>
- <span data-ttu-id="c3e5f-206">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-206">Office 365 GCC</span></span>
- <span data-ttu-id="c3e5f-207">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="c3e5f-207">Office 365 GCC High</span></span>
- <span data-ttu-id="c3e5f-208">Office 365 DoD 進一步瞭解[office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（例如 GCC、gcc 高和 DoD）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-208">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c3e5f-209">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-209">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="c3e5f-210">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-210">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="c3e5f-211">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-211">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="c3e5f-212">當 SBC 傳送要求來解析此名稱時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-212">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="c3e5f-213">作業是以資料中心的效能指標，以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-213">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="c3e5f-214">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-214">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="c3e5f-215">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-215">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="c3e5f-216">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-216">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="c3e5f-217">您必須將這三個 Fqdn 放在一起，才能：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-217">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="c3e5f-218">提供最佳的使用體驗（在所指派的 SBC 資料中心較少且最接近的情況下，由查詢第一個 FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-218">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="c3e5f-219">在來自 SBC 的連線建立至遇到暫時問題的資料中心時，提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-219">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="c3e5f-220">如需詳細資訊，請參閱下方的容錯移轉機制。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-220">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="c3e5f-221">Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**和**sip3.pstnhub.microsoft.com**將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-221">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="c3e5f-222">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="c3e5f-222">52.114.148.0</span></span>
- <span data-ttu-id="c3e5f-223">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="c3e5f-223">52.114.132.46</span></span>
- <span data-ttu-id="c3e5f-224">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="c3e5f-224">52.114.75.24</span></span>
- <span data-ttu-id="c3e5f-225">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="c3e5f-225">52.114.76.76</span></span>
- <span data-ttu-id="c3e5f-226">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="c3e5f-226">52.114.7.24</span></span>
- <span data-ttu-id="c3e5f-227">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="c3e5f-227">52.114.14.70</span></span>

<span data-ttu-id="c3e5f-228">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-228">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="c3e5f-229">如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com**會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-229">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c3e5f-230">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-230">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="c3e5f-231">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-231">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c3e5f-232">**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-232">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c3e5f-233">因為 Office 365 DoD 環境僅存在於美國資料中心，所以沒有次要和第三個 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-233">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c3e5f-234">Fqdn – sip.pstnhub.dod.teams.microsoft.us 將會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-234">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c3e5f-235">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="c3e5f-235">52.127.64.33</span></span>
- <span data-ttu-id="c3e5f-236">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="c3e5f-236">52.127.68.34</span></span>

<span data-ttu-id="c3e5f-237">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-237">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c3e5f-238">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c3e5f-239">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-239">Office 365 GCC High environment</span></span>

<span data-ttu-id="c3e5f-240">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-240">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c3e5f-241">**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-241">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c3e5f-242">由於 GCC 的高環境僅存在於美國資料中心，因此沒有副及三元 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-242">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c3e5f-243">Fqdn – sip.pstnhub.gov.teams.microsoft.us 將會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-243">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c3e5f-244">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="c3e5f-244">52.127.88.59</span></span>
- <span data-ttu-id="c3e5f-245">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="c3e5f-245">52.127.92.64</span></span>

<span data-ttu-id="c3e5f-246">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-246">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c3e5f-247">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-247">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="c3e5f-248">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-248">SIP Signaling: Ports</span></span>

<span data-ttu-id="c3e5f-249">對於所有提供直接路由的 Office 365 環境而言，埠需求都是相同的：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-249">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="c3e5f-250">Office 365</span><span class="sxs-lookup"><span data-stu-id="c3e5f-250">Office 365</span></span>
- <span data-ttu-id="c3e5f-251">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-251">Office 365 GCC</span></span>
- <span data-ttu-id="c3e5f-252">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="c3e5f-252">Office 365 GCC High</span></span>
- <span data-ttu-id="c3e5f-253">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="c3e5f-253">Office 365 DoD</span></span>

<span data-ttu-id="c3e5f-254">您必須使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-254">You must use the following ports:</span></span>

| <span data-ttu-id="c3e5f-255">頻寬</span><span class="sxs-lookup"><span data-stu-id="c3e5f-255">Traffic</span></span> | <span data-ttu-id="c3e5f-256">從</span><span class="sxs-lookup"><span data-stu-id="c3e5f-256">From</span></span> | <span data-ttu-id="c3e5f-257">自</span><span class="sxs-lookup"><span data-stu-id="c3e5f-257">To</span></span> | <span data-ttu-id="c3e5f-258">來源埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-258">Source port</span></span> | <span data-ttu-id="c3e5f-259">目的地埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-259">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c3e5f-260">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c3e5f-260">SIP/TLS</span></span>| <span data-ttu-id="c3e5f-261">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="c3e5f-261">SIP Proxy</span></span> | <span data-ttu-id="c3e5f-262">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-262">SBC</span></span> | <span data-ttu-id="c3e5f-263">1024-65535</span><span class="sxs-lookup"><span data-stu-id="c3e5f-263">1024 - 65535</span></span> | <span data-ttu-id="c3e5f-264">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-264">Defined on the SBC</span></span> |
| <span data-ttu-id="c3e5f-265">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c3e5f-265">SIP/TLS</span></span> | <span data-ttu-id="c3e5f-266">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-266">SBC</span></span> | <span data-ttu-id="c3e5f-267">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="c3e5f-267">SIP Proxy</span></span> | <span data-ttu-id="c3e5f-268">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-268">Defined on the SBC</span></span> | <span data-ttu-id="c3e5f-269">5061</span><span class="sxs-lookup"><span data-stu-id="c3e5f-269">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="c3e5f-270">媒體流量： IP 與埠範圍</span><span class="sxs-lookup"><span data-stu-id="c3e5f-270">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="c3e5f-271">如果用戶端無法使用公用 IP 位址到達 SBC，則在 SBC 與團隊用戶端之間的媒體流量會流動（如果有直接連線）或透過團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-271">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="c3e5f-272">直接媒體流量的需求（在團隊用戶端與 SBC 之間）</span><span class="sxs-lookup"><span data-stu-id="c3e5f-272">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="c3e5f-273">用戶端必須能夠存取指定的埠（請參閱 table）至 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-273">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="c3e5f-274">注意：如果用戶端在內部網路中，則媒體會流向 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-274">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="c3e5f-275">您可以在您的 NAT 裝置上設定頭髮釘選，這樣通信量就不會離開商業網路裝置。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-275">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="c3e5f-276">頻寬</span><span class="sxs-lookup"><span data-stu-id="c3e5f-276">Traffic</span></span> | <span data-ttu-id="c3e5f-277">從</span><span class="sxs-lookup"><span data-stu-id="c3e5f-277">From</span></span> | <span data-ttu-id="c3e5f-278">自</span><span class="sxs-lookup"><span data-stu-id="c3e5f-278">To</span></span> | <span data-ttu-id="c3e5f-279">來源埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-279">Source port</span></span> | <span data-ttu-id="c3e5f-280">目的地埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-280">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c3e5f-281">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-281">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-282">用戶端</span><span class="sxs-lookup"><span data-stu-id="c3e5f-282">Client</span></span> | <span data-ttu-id="c3e5f-283">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-283">SBC</span></span> | <span data-ttu-id="c3e5f-284">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="c3e5f-284">50 000 – 50 019</span></span>  | <span data-ttu-id="c3e5f-285">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-285">Defined on the SBC</span></span> |
| <span data-ttu-id="c3e5f-286">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-286">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-287">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-287">SBC</span></span> | <span data-ttu-id="c3e5f-288">用戶端</span><span class="sxs-lookup"><span data-stu-id="c3e5f-288">Client</span></span> | <span data-ttu-id="c3e5f-289">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-289">Defined on the SBC</span></span> | <span data-ttu-id="c3e5f-290">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="c3e5f-290">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="c3e5f-291">如果您的網路裝置會轉譯用戶端的來源埠，請確定已在網路設備與 SBC 之間開啟已轉換的埠。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-291">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="c3e5f-292">使用傳輸繼電器的需求</span><span class="sxs-lookup"><span data-stu-id="c3e5f-292">Requirements for using Transport Relays</span></span>

<span data-ttu-id="c3e5f-293">傳輸繼電器與媒體處理器在同一個範圍內（適用于非旁路情況）：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-293">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c3e5f-294">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-294">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="c3e5f-295">52.112.0.0/14 （從52.112.0.1 到52.115.255.254 的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="c3e5f-295">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c3e5f-296">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-296">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="c3e5f-297">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="c3e5f-297">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c3e5f-298">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-298">Office 365 GCC High environment</span></span>

- <span data-ttu-id="c3e5f-299">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="c3e5f-299">52.127.88.0/21</span></span>


<span data-ttu-id="c3e5f-300">[小組傳輸中繼] 的埠範圍（適用于所有環境）如下表所示：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-300">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="c3e5f-301">頻寬</span><span class="sxs-lookup"><span data-stu-id="c3e5f-301">Traffic</span></span> | <span data-ttu-id="c3e5f-302">從</span><span class="sxs-lookup"><span data-stu-id="c3e5f-302">From</span></span> | <span data-ttu-id="c3e5f-303">自</span><span class="sxs-lookup"><span data-stu-id="c3e5f-303">To</span></span> | <span data-ttu-id="c3e5f-304">來源埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-304">Source port</span></span> | <span data-ttu-id="c3e5f-305">目的地埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-305">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c3e5f-306">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-306">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-307">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="c3e5f-307">Transport Relay</span></span> | <span data-ttu-id="c3e5f-308">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-308">SBC</span></span> | <span data-ttu-id="c3e5f-309">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="c3e5f-309">50 000 -59 999</span></span>    | <span data-ttu-id="c3e5f-310">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-310">Defined on the SBC</span></span> |
| <span data-ttu-id="c3e5f-311">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-311">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-312">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-312">SBC</span></span> | <span data-ttu-id="c3e5f-313">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="c3e5f-313">Transport Relay</span></span> | <span data-ttu-id="c3e5f-314">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-314">Defined on the SBC</span></span> | <span data-ttu-id="c3e5f-315">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="c3e5f-315">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="c3e5f-316">Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-316">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="c3e5f-317">因為 Microsoft 有兩個版本的傳輸繼電器，所以需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-317">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="c3e5f-318">v4，只能與埠範圍 50 000 搭配 59 999</span><span class="sxs-lookup"><span data-stu-id="c3e5f-318">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="c3e5f-319">v6 是與埠3478、3479搭配使用</span><span class="sxs-lookup"><span data-stu-id="c3e5f-319">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="c3e5f-320">目前，媒體旁路只支援 v4 版的傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-320">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="c3e5f-321">我們會在未來推出 v6 支援。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-321">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="c3e5f-322">您需要開啟埠3478和3479以進行轉換。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-322">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="c3e5f-323">當 Microsoft 使用媒體旁路支援 v6 傳輸中繼時，您就不需要重新設定您的網路設備或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-323">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="c3e5f-324">使用媒體處理器的需求</span><span class="sxs-lookup"><span data-stu-id="c3e5f-324">Requirements for using media processors</span></span>

<span data-ttu-id="c3e5f-325">媒體處理器總是位於語音應用程式及網頁用戶端的媒體路徑中（例如，Edge 或 Google Chrome 中的團隊用戶端）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-325">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="c3e5f-326">其需求與非旁路設定相同。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-326">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="c3e5f-327">媒體流量的 IP 範圍是</span><span class="sxs-lookup"><span data-stu-id="c3e5f-327">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c3e5f-328">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-328">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="c3e5f-329">52.112.0.0/14 （從52.112.0.1 到52.115.255.254 的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="c3e5f-329">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c3e5f-330">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-330">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="c3e5f-331">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="c3e5f-331">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c3e5f-332">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="c3e5f-332">Office 365 GCC High environment</span></span>

- <span data-ttu-id="c3e5f-333">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="c3e5f-333">52.127.88.0/21</span></span>

<span data-ttu-id="c3e5f-334">媒體處理器的埠範圍（適用于所有環境）如下表所示：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-334">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="c3e5f-335">頻寬</span><span class="sxs-lookup"><span data-stu-id="c3e5f-335">Traffic</span></span> | <span data-ttu-id="c3e5f-336">從</span><span class="sxs-lookup"><span data-stu-id="c3e5f-336">From</span></span> | <span data-ttu-id="c3e5f-337">自</span><span class="sxs-lookup"><span data-stu-id="c3e5f-337">To</span></span> | <span data-ttu-id="c3e5f-338">來源埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-338">Source port</span></span> | <span data-ttu-id="c3e5f-339">目的地埠</span><span class="sxs-lookup"><span data-stu-id="c3e5f-339">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c3e5f-340">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-340">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-341">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="c3e5f-341">Media Processor</span></span> | <span data-ttu-id="c3e5f-342">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-342">SBC</span></span> | <span data-ttu-id="c3e5f-343">3478、3479和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="c3e5f-343">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="c3e5f-344">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-344">Defined on the SBC</span></span> |
| <span data-ttu-id="c3e5f-345">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c3e5f-345">UDP/SRTP</span></span> | <span data-ttu-id="c3e5f-346">SBC</span><span class="sxs-lookup"><span data-stu-id="c3e5f-346">SBC</span></span> | <span data-ttu-id="c3e5f-347">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="c3e5f-347">Media Processor</span></span> | <span data-ttu-id="c3e5f-348">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="c3e5f-348">Defined on the SBC</span></span> | <span data-ttu-id="c3e5f-349">3478、3479和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="c3e5f-349">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="c3e5f-350">針對媒體旁路和非媒體旁路設定個別 trunks</span><span class="sxs-lookup"><span data-stu-id="c3e5f-350">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="c3e5f-351">如果您是從非媒體旁路移植到媒體旁路，且想要在將所有使用方式移植到媒體旁路之前確認功能，您可以建立個別的主幹及個別的線上語音路由原則，以路由到媒體旁路幹線並指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-351">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="c3e5f-352">高層次的設定步驟：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-352">High-level configuration steps:</span></span>

- <span data-ttu-id="c3e5f-353">識別要測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-353">Identify users to test media bypass.</span></span>

- <span data-ttu-id="c3e5f-354">使用不同的 Fqdn 建立兩個不同的 trunks：一個為媒體略過啟用;另一種是。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-354">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="c3e5f-355">兩個 trunks 都指向同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-355">Both trunks point to the same SBC.</span></span> <span data-ttu-id="c3e5f-356">TLS SIP 信號的埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-356">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="c3e5f-357">媒體埠必須相同。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-357">The ports for media must be the same.</span></span>

- <span data-ttu-id="c3e5f-358">建立新的線上語音路由策略，並將媒體旁路主幹指派給與此原則之 PSTN 使用相關聯的對應路由。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-358">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="c3e5f-359">將新的線上語音路由策略指派給已識別用來測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-359">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="c3e5f-360">下列範例說明這個邏輯。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-360">The example below illustrates this logic.</span></span>

| <span data-ttu-id="c3e5f-361">使用者組</span><span class="sxs-lookup"><span data-stu-id="c3e5f-361">Set of users</span></span> | <span data-ttu-id="c3e5f-362">使用者數量</span><span class="sxs-lookup"><span data-stu-id="c3e5f-362">Number of users</span></span> | <span data-ttu-id="c3e5f-363">在 OVRP 中指派中繼 FQDN</span><span class="sxs-lookup"><span data-stu-id="c3e5f-363">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="c3e5f-364">已啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="c3e5f-364">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="c3e5f-365">非媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="c3e5f-365">Users with non-media bypass trunk</span></span> | <span data-ttu-id="c3e5f-366">980</span><span class="sxs-lookup"><span data-stu-id="c3e5f-366">980</span></span> | <span data-ttu-id="c3e5f-367">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="c3e5f-367">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="c3e5f-368">滿足</span><span class="sxs-lookup"><span data-stu-id="c3e5f-368">true</span></span>
<span data-ttu-id="c3e5f-369">具有媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="c3e5f-369">Users with media bypass trunk</span></span> | <span data-ttu-id="c3e5f-370">20</span><span class="sxs-lookup"><span data-stu-id="c3e5f-370">20</span></span> | <span data-ttu-id="c3e5f-371">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="c3e5f-371">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="c3e5f-372">虛假</span><span class="sxs-lookup"><span data-stu-id="c3e5f-372">false</span></span> | 

<span data-ttu-id="c3e5f-373">兩個 trunks 都可以指向相同的同一個 SBC，且具有相同的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-373">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="c3e5f-374">SBC 上的 TLS 信號埠必須不同，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-374">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="c3e5f-375">注意：您必須確認您的憑證同時支援這兩個 trunks。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-375">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="c3e5f-376">在 SAN 中，您必須有兩個名稱（**sbc1.contoso.com**和**sbc2.contoso.com**），或是擁有萬用字元證書。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-376">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![顯示兩個 trunks 可以指向同一個公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="c3e5f-378">如需如何在同一個 SBC 上設定兩個 trunks 的相關資訊，請參閱您的 SBC 轉銷商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="c3e5f-378">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="c3e5f-379">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="c3e5f-379">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="c3e5f-380">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="c3e5f-380">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="c3e5f-381">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="c3e5f-381">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="c3e5f-382">TE-系統（anynode）部署檔</span><span class="sxs-lookup"><span data-stu-id="c3e5f-382">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="c3e5f-383">媒體略過支援的用戶端端點</span><span class="sxs-lookup"><span data-stu-id="c3e5f-383">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="c3e5f-384">所有團隊桌面用戶端和團隊手機裝置都支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-384">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="c3e5f-385">對於不支援媒體旁路的所有其他端點，我們會將呼叫轉換成非旁路，即使它是繞過的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-385">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="c3e5f-386">這會自動發生，不需要系統管理員執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-386">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="c3e5f-387">這包括商務用 Skype 3PIP 手機以及支援直接路由呼叫的小組網頁用戶端（根據 Chromium、Google Chrome、Mozilla Firefox 的新 Microsoft Edge）。</span><span class="sxs-lookup"><span data-stu-id="c3e5f-387">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="c3e5f-388">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3e5f-388">See also</span></span>

[<span data-ttu-id="c3e5f-389">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="c3e5f-389">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



