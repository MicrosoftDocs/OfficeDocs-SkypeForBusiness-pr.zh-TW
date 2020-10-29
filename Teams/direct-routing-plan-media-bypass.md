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
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790655"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="69bbb-103">媒體旁路搭配直接路由方案</span><span class="sxs-lookup"><span data-stu-id="69bbb-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="69bbb-104">關於直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="69bbb-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="69bbb-105">[媒體旁路] 可讓您縮短媒體流量的路徑，並減少傳輸中的跳躍數，以獲得更佳的效能。</span><span class="sxs-lookup"><span data-stu-id="69bbb-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="69bbb-106">在媒體旁路的情況下，媒體會保留在會話邊界控制器 (SBC) 與用戶端，而不是透過 Microsoft Phone 系統傳送。</span><span class="sxs-lookup"><span data-stu-id="69bbb-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="69bbb-107">若要設定媒體旁路，SBC 與用戶端必須位於同一個位置或網路上。</span><span class="sxs-lookup"><span data-stu-id="69bbb-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="69bbb-108">您可以使用 **設定 CSOnlinePSTNGateway** 命令，並將 **-MediaBypass** 參數設定為 true 或 false，以控制每個 SBC 的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="69bbb-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="69bbb-109">如果您啟用 [媒體旁路]，這並不表示所有媒體流量都會留在公司網路內。</span><span class="sxs-lookup"><span data-stu-id="69bbb-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="69bbb-110">本文將說明不同案例中的通話流程。</span><span class="sxs-lookup"><span data-stu-id="69bbb-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="69bbb-111">下圖說明通話流程中的差異，以及不使用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="69bbb-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="69bbb-112">若沒有媒體旁路，當用戶端撥打或接聽來電時，在 SBC、Microsoft Phone 系統和團隊用戶端之間的信號與媒體流程，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="69bbb-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-113">![顯示沒有媒體旁路的信號和媒體流程](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="69bbb-114">但假設使用者與 SBC 在相同的大樓或 network 中。</span><span class="sxs-lookup"><span data-stu-id="69bbb-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="69bbb-115">例如，假設在 Frankfurt 中建立的使用者撥打電話給 PSTN 使用者：</span><span class="sxs-lookup"><span data-stu-id="69bbb-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="69bbb-116">如果 **沒有媒體旁路** ，媒體會透過阿姆斯特丹或都柏林 (，在 Microsoft 資料中心部署) 並回到 SBC Frankfurt。</span><span class="sxs-lookup"><span data-stu-id="69bbb-116">**Without media bypass** , media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="69bbb-117">之所以選取 [歐洲資料中心]，是因為 SBC 是在歐洲，而 Microsoft 使用最接近 SBC 的資料中心。</span><span class="sxs-lookup"><span data-stu-id="69bbb-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="69bbb-118">雖然這種方法不會影響通話品質，因為在大部分地區內的 Microsoft 網路中的流量流程已優化，但通信量卻有不必要的迴圈。</span><span class="sxs-lookup"><span data-stu-id="69bbb-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="69bbb-119">在 **媒體旁路** 的情況下，媒體會直接保留在團隊使用者與 SBC 之間，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="69bbb-119">**With media bypass** , the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="69bbb-120">![顯示使用媒體旁路的信號及媒體流程](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="69bbb-121">媒體旁路利用名為「互動式連線」的通訊協定，在 SBC 上 (ICE) 在團隊用戶端和 ICE lite 中。</span><span class="sxs-lookup"><span data-stu-id="69bbb-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="69bbb-122">這些通訊協定可讓直接路由使用最直接的媒體路徑來獲得最佳品質。</span><span class="sxs-lookup"><span data-stu-id="69bbb-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="69bbb-123">冰與冰 Lite 是 WebRTC 的標準。</span><span class="sxs-lookup"><span data-stu-id="69bbb-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="69bbb-124">如需這些通訊協定的詳細資訊，請參閱 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="69bbb-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="69bbb-125">通話流程與防火牆規劃</span><span class="sxs-lookup"><span data-stu-id="69bbb-125">Call flow and firewall planning</span></span>

<span data-ttu-id="69bbb-126">通話流程和防火牆規劃取決於使用者是否能直接存取 SBC 的公用 IP 位址，以及使用者是否在網路內或外部。</span><span class="sxs-lookup"><span data-stu-id="69bbb-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="69bbb-127">如果使用者可以直接存取 SBC 的公用 IP 位址，就可以進行通話流程</span><span class="sxs-lookup"><span data-stu-id="69bbb-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="69bbb-128">如果使用者可以直接存取 SBC 的公用 IP 位址，則呼叫流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="69bbb-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="69bbb-129">針對媒體旁路，小組用戶端必須能夠存取 SBC 的公用 IP 位址（即使是來自內部網路）。</span><span class="sxs-lookup"><span data-stu-id="69bbb-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="69bbb-130">如果不想要直接媒體，媒體可以透過傳輸中繼流過。</span><span class="sxs-lookup"><span data-stu-id="69bbb-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="69bbb-131">當使用者與 SBC 在相同的建築物和/或網路中時，建議使用這項方案：從媒體路徑中移除 Microsoft 雲端元件。</span><span class="sxs-lookup"><span data-stu-id="69bbb-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="69bbb-132">通知總是透過 Microsoft 雲端傳送流程。</span><span class="sxs-lookup"><span data-stu-id="69bbb-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="69bbb-133">下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為內部，且用戶端可以取得 SBC 的公用 IP 位址 (直接媒體) ：</span><span class="sxs-lookup"><span data-stu-id="69bbb-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="69bbb-134">路徑的箭號和數值是依照 [Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)的依據。</span><span class="sxs-lookup"><span data-stu-id="69bbb-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="69bbb-135">SIP 信號會根據流量) 的方向，一直採用路徑4和4的 (。</span><span class="sxs-lookup"><span data-stu-id="69bbb-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="69bbb-136">媒體保持在本機，並採用路徑5b。</span><span class="sxs-lookup"><span data-stu-id="69bbb-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-137">![顯示已啟用媒體旁路的通話流程，用戶端是內部的](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="69bbb-138">如果使用者無法存取 SBC 的公用 IP 位址，通話流程</span><span class="sxs-lookup"><span data-stu-id="69bbb-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="69bbb-139">如果使用者無法存取 SBC 的公用 IP 位址，下列說明通話流程。</span><span class="sxs-lookup"><span data-stu-id="69bbb-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="69bbb-140">例如，假設使用者是外部使用者，而租使用者系統管理員決定不要將 SBC 的公用 IP 位址開啟至網際網路中的每個人，但僅限 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="69bbb-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="69bbb-141">流量的內部元件可以透過團隊傳輸繼電器來流動。</span><span class="sxs-lookup"><span data-stu-id="69bbb-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="69bbb-142">請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="69bbb-142">Consider the following:</span></span>

- <span data-ttu-id="69bbb-143">使用團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="69bbb-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="69bbb-144">針對媒體旁路，Microsoft 使用的傳輸繼電器版本必須在團隊傳輸中繼器與 (SBC 之間開啟埠 50 000 至 59 999，我們打算移至只需要3478和3479埠) 的版本。</span><span class="sxs-lookup"><span data-stu-id="69bbb-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="69bbb-145">下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為外部，且用戶端無法取得會話邊界控制器的公用 IP 位址 (媒體是由小組傳輸中繼) 中繼。</span><span class="sxs-lookup"><span data-stu-id="69bbb-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="69bbb-146">路徑的箭號和數值是依照 [Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)的依據。</span><span class="sxs-lookup"><span data-stu-id="69bbb-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="69bbb-147">媒體是透過路徑3、3 '、4和4」進行中繼</span><span class="sxs-lookup"><span data-stu-id="69bbb-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-148">![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="69bbb-149">如果使用者在網路以外且能存取 SBC 的公用 IP，通話流程</span><span class="sxs-lookup"><span data-stu-id="69bbb-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="69bbb-150">這不是建議的設定，因為它不會利用團隊傳輸繼電器。</span><span class="sxs-lookup"><span data-stu-id="69bbb-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="69bbb-151">相反地，您應該考慮先前的情況，即使用者無法存取 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="69bbb-152">下列圖表顯示在啟用媒體旁路時的通話流程、用戶端為外部，且用戶端可以取得 SBC 的公用 IP 位址 (直接媒體) 。</span><span class="sxs-lookup"><span data-stu-id="69bbb-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="69bbb-153">路徑的箭號和數值是依照 [Microsoft 團隊通話流程](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 文章。</span><span class="sxs-lookup"><span data-stu-id="69bbb-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="69bbb-154">SIP 信號總是會採用路徑3和 3 ' (，視通信量的方向) 而定。</span><span class="sxs-lookup"><span data-stu-id="69bbb-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="69bbb-155">媒體流程使用路徑2。</span><span class="sxs-lookup"><span data-stu-id="69bbb-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-156">![顯示使用者無法存取 SBC 公用 IP 的通話流程](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="69bbb-157">媒體處理器與傳輸繼電器的用途</span><span class="sxs-lookup"><span data-stu-id="69bbb-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="69bbb-158">Microsoft 雲端中有兩個元件可位於媒體流量的路徑：媒體處理器和傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="69bbb-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="69bbb-159">媒體處理器是一個公開的元件，可在非旁路情況下處理媒體，並處理語音應用程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="69bbb-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="69bbb-160">媒體處理器一直在最終使用者未繞過呼叫的路徑中，但不會在回避通話的路徑中。</span><span class="sxs-lookup"><span data-stu-id="69bbb-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="69bbb-161">媒體處理器總是位於所有語音應用程式的路徑中，例如通話寄存、組織自動語音應答及通話佇列。</span><span class="sxs-lookup"><span data-stu-id="69bbb-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="69bbb-162">傳輸中繼是用來連線到最接近的傳輸服務，以傳送即時流量。</span><span class="sxs-lookup"><span data-stu-id="69bbb-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="69bbb-163">傳輸繼電器可能是或不在繞過通話的路徑中，也可能不是來源於或發給最終使用者--視使用者的位置和網路的設定方式而定。</span><span class="sxs-lookup"><span data-stu-id="69bbb-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="69bbb-164">下圖顯示兩個通話流程：一個啟用「媒體旁路」，而另一個停用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="69bbb-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="69bbb-165">注意：圖表只會說明源自--或發至端使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="69bbb-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="69bbb-166">媒體控制器是 Azure 中的 microservice，可指派媒體處理器並建立會話描述通訊協定 (SDP) 提供。</span><span class="sxs-lookup"><span data-stu-id="69bbb-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="69bbb-167">SIP Proxy 是一個元件，可將小組中使用的 HTTP REST 信號轉譯成 SIP。</span><span class="sxs-lookup"><span data-stu-id="69bbb-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-168">![顯示已啟用及停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="69bbb-169">下表摘要列出媒體處理器與傳輸中繼之間的差異。</span><span class="sxs-lookup"><span data-stu-id="69bbb-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="69bbb-170">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="69bbb-170">Media Processors</span></span> | <span data-ttu-id="69bbb-171">傳輸繼電器</span><span class="sxs-lookup"><span data-stu-id="69bbb-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="69bbb-172">在媒體路徑中，讓使用者無法避開來電</span><span class="sxs-lookup"><span data-stu-id="69bbb-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="69bbb-173">總會</span><span class="sxs-lookup"><span data-stu-id="69bbb-173">Always</span></span> | <span data-ttu-id="69bbb-174">任何</span><span class="sxs-lookup"><span data-stu-id="69bbb-174">Never</span></span> | 
<span data-ttu-id="69bbb-175">在媒體路徑中，讓使用者略過來電</span><span class="sxs-lookup"><span data-stu-id="69bbb-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="69bbb-176">任何</span><span class="sxs-lookup"><span data-stu-id="69bbb-176">Never</span></span> | <span data-ttu-id="69bbb-177">如果用戶端無法在公用 IP 位址上到達 SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="69bbb-178">在語音應用程式的媒體路徑中</span><span class="sxs-lookup"><span data-stu-id="69bbb-178">In media path for voice applications</span></span> | <span data-ttu-id="69bbb-179">總會</span><span class="sxs-lookup"><span data-stu-id="69bbb-179">Always</span></span> | <span data-ttu-id="69bbb-180">任何</span><span class="sxs-lookup"><span data-stu-id="69bbb-180">Never</span></span> | 
<span data-ttu-id="69bbb-181">可以執行 (B2BUA) 的轉碼 \*</span><span class="sxs-lookup"><span data-stu-id="69bbb-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="69bbb-182">是</span><span class="sxs-lookup"><span data-stu-id="69bbb-182">Yes</span></span> | <span data-ttu-id="69bbb-183">否，只在端點之間中繼音訊</span><span class="sxs-lookup"><span data-stu-id="69bbb-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="69bbb-184">全球和位置的實例數</span><span class="sxs-lookup"><span data-stu-id="69bbb-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="69bbb-185">總共10個：美國東部和西部2在阿姆斯特丹和都柏林中為2，2在香港與新加坡中;在日本是 2;在澳大利亞東與東南部中的2</span><span class="sxs-lookup"><span data-stu-id="69bbb-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="69bbb-186">條</span><span class="sxs-lookup"><span data-stu-id="69bbb-186">Multiple</span></span>

<span data-ttu-id="69bbb-187">IP 範圍包括：</span><span class="sxs-lookup"><span data-stu-id="69bbb-187">The IP ranges are:</span></span>
- <span data-ttu-id="69bbb-188">52.112.0.0/14 (從52.112.0.1 至52.115.255.254 的 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="69bbb-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="69bbb-189">52.120.0.0/14 (從52.120.0.1 至52.123.255.254 的 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="69bbb-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="69bbb-190">\* 轉碼說明：</span><span class="sxs-lookup"><span data-stu-id="69bbb-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="69bbb-191">媒體處理常式是 B2BUA，這表示它可以變更編解碼器 (例如，從 [團隊用戶端] 到 [MP] 和 [711] 之間的絞絲與 [SBC]) 。</span><span class="sxs-lookup"><span data-stu-id="69bbb-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="69bbb-192">傳輸中繼並非 B2BUA，這表示在用戶端與 SBC 之間不會變更編解碼器，即使流量透過中繼流程也一樣。</span><span class="sxs-lookup"><span data-stu-id="69bbb-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="69bbb-193">如果將幹線設定為媒體旁路，則使用團隊媒體處理器</span><span class="sxs-lookup"><span data-stu-id="69bbb-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="69bbb-194">團隊媒體處理器在下列情況下，會一直插入媒體路徑：</span><span class="sxs-lookup"><span data-stu-id="69bbb-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="69bbb-195">從1:1 升級到群組通話的通話</span><span class="sxs-lookup"><span data-stu-id="69bbb-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="69bbb-196">通話會傳送給聯盟團隊使用者</span><span class="sxs-lookup"><span data-stu-id="69bbb-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="69bbb-197">通話是轉寄或轉接至商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="69bbb-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="69bbb-198">請確定您的 SBC 有權存取媒體處理器與傳輸中繼範圍，如下所述。</span><span class="sxs-lookup"><span data-stu-id="69bbb-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="69bbb-199">SIP 信號： Fqdn</span><span class="sxs-lookup"><span data-stu-id="69bbb-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="69bbb-200">針對 SIP 信號，FQDN 和防火牆需求與非繞過案例相同。</span><span class="sxs-lookup"><span data-stu-id="69bbb-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="69bbb-201">在下列 Microsoft 365 或 Office 365 環境中提供直接路由：</span><span class="sxs-lookup"><span data-stu-id="69bbb-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="69bbb-202">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="69bbb-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="69bbb-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="69bbb-203">Office 365 GCC</span></span>
- <span data-ttu-id="69bbb-204">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="69bbb-204">Office 365 GCC High</span></span>
- <span data-ttu-id="69bbb-205">Office 365 DoD 進一步瞭解 [office 365 和美國政府環境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) （例如 GCC、gcc 高和 DoD）。</span><span class="sxs-lookup"><span data-stu-id="69bbb-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="69bbb-206">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="69bbb-207">直接路由的連接點是下列三個 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="69bbb-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="69bbb-208">**sip.pstnhub.microsoft.com** –全域 FQDN-必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="69bbb-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="69bbb-209">當 SBC 傳送要求來解析此名稱時，Microsoft Azure DNS 伺服器會傳回指向指派給 SBC 之主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="69bbb-210">作業是以資料中心的效能指標，以及與 SBC 有關的地理位置為基礎。</span><span class="sxs-lookup"><span data-stu-id="69bbb-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="69bbb-211">傳回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="69bbb-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="69bbb-212">**sip2.pstnhub.microsoft.com** –次要 FQDN-地理位置對應至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="69bbb-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="69bbb-213">**sip3.pstnhub.microsoft.com** –三元 FQDN-[地理位置] 對應至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="69bbb-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="69bbb-214">您必須將這三個 Fqdn 放在一起，才能：</span><span class="sxs-lookup"><span data-stu-id="69bbb-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="69bbb-215">透過查詢第一個 FQDN) ，提供 (較小且最接近所指派 SBC 資料中心的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="69bbb-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="69bbb-216">在來自 SBC 的連線建立至遇到暫時問題的資料中心時，提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="69bbb-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="69bbb-217">如需詳細資訊，請參閱下方的容錯移轉機制。</span><span class="sxs-lookup"><span data-stu-id="69bbb-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="69bbb-218">Fqdn **sip.pstnhub.microsoft.com** 、 **sip2.pstnhub.microsoft.com** 和 **sip3.pstnhub.microsoft.com** 將解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="69bbb-218">The FQDNs **sip.pstnhub.microsoft.com** , **sip2.pstnhub.microsoft.com** , and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="69bbb-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="69bbb-219">52.114.148.0</span></span>
- <span data-ttu-id="69bbb-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="69bbb-220">52.114.132.46</span></span>
- <span data-ttu-id="69bbb-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="69bbb-221">52.114.16.74</span></span>
- <span data-ttu-id="69bbb-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="69bbb-222">52.114.20.29</span></span>
- <span data-ttu-id="69bbb-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="69bbb-223">52.114.75.24</span></span>
- <span data-ttu-id="69bbb-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="69bbb-224">52.114.76.76</span></span>
- <span data-ttu-id="69bbb-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="69bbb-225">52.114.7.24</span></span>
- <span data-ttu-id="69bbb-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="69bbb-226">52.114.14.70</span></span>

<span data-ttu-id="69bbb-227">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="69bbb-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="69bbb-228">如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="69bbb-229">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="69bbb-230">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="69bbb-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="69bbb-231">**sip.pstnhub.dod.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="69bbb-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="69bbb-232">因為 Office 365 DoD 環境僅存在於美國資料中心，所以沒有次要和第三個 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="69bbb-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="69bbb-233">Fqdn – sip.pstnhub.dod.teams.microsoft.us 將會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="69bbb-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="69bbb-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="69bbb-234">52.127.64.33</span></span>
- <span data-ttu-id="69bbb-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="69bbb-235">52.127.68.34</span></span>

<span data-ttu-id="69bbb-236">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="69bbb-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="69bbb-237">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="69bbb-238">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="69bbb-239">直接路由的連接點是下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="69bbb-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="69bbb-240">**sip.pstnhub.gov.teams.microsoft.us** –全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="69bbb-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="69bbb-241">由於 GCC 的高環境僅存在於美國資料中心，因此沒有副及三元 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="69bbb-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="69bbb-242">Fqdn – sip.pstnhub.gov.teams.microsoft.us 將會解析成下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="69bbb-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="69bbb-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="69bbb-243">52.127.88.59</span></span>
- <span data-ttu-id="69bbb-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="69bbb-244">52.127.92.64</span></span>

<span data-ttu-id="69bbb-245">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許傳入及傳出流量進出位址來傳送信號。</span><span class="sxs-lookup"><span data-stu-id="69bbb-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="69bbb-246">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us 會解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="69bbb-247">SIP 信號：埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="69bbb-248">對於所有提供直接路由的 Office 365 環境而言，埠需求都是相同的：</span><span class="sxs-lookup"><span data-stu-id="69bbb-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="69bbb-249">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="69bbb-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="69bbb-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="69bbb-250">Office 365 GCC</span></span>
- <span data-ttu-id="69bbb-251">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="69bbb-251">Office 365 GCC High</span></span>
- <span data-ttu-id="69bbb-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="69bbb-252">Office 365 DoD</span></span>

<span data-ttu-id="69bbb-253">您必須使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="69bbb-253">You must use the following ports:</span></span>

| <span data-ttu-id="69bbb-254">頻寬</span><span class="sxs-lookup"><span data-stu-id="69bbb-254">Traffic</span></span> | <span data-ttu-id="69bbb-255">從</span><span class="sxs-lookup"><span data-stu-id="69bbb-255">From</span></span> | <span data-ttu-id="69bbb-256">自</span><span class="sxs-lookup"><span data-stu-id="69bbb-256">To</span></span> | <span data-ttu-id="69bbb-257">來源埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-257">Source port</span></span> | <span data-ttu-id="69bbb-258">目的地埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="69bbb-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="69bbb-259">SIP/TLS</span></span>| <span data-ttu-id="69bbb-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="69bbb-260">SIP Proxy</span></span> | <span data-ttu-id="69bbb-261">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-261">SBC</span></span> | <span data-ttu-id="69bbb-262">1024-65535</span><span class="sxs-lookup"><span data-stu-id="69bbb-262">1024 - 65535</span></span> | <span data-ttu-id="69bbb-263">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-263">Defined on the SBC</span></span> |
| <span data-ttu-id="69bbb-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="69bbb-264">SIP/TLS</span></span> | <span data-ttu-id="69bbb-265">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-265">SBC</span></span> | <span data-ttu-id="69bbb-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="69bbb-266">SIP Proxy</span></span> | <span data-ttu-id="69bbb-267">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-267">Defined on the SBC</span></span> | <span data-ttu-id="69bbb-268">5061</span><span class="sxs-lookup"><span data-stu-id="69bbb-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="69bbb-269">媒體流量： IP 與埠範圍</span><span class="sxs-lookup"><span data-stu-id="69bbb-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="69bbb-270">如果用戶端無法使用公用 IP 位址到達 SBC，則在 SBC 與團隊用戶端之間的媒體流量會流動（如果有直接連線）或透過團隊傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="69bbb-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="69bbb-271">團隊用戶端與 SBC 之間 (直接媒體流量的需求) </span><span class="sxs-lookup"><span data-stu-id="69bbb-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="69bbb-272">用戶端必須擁有指定埠的存取權 (請參閱 SBC 之公用 IP 位址上的表格) 。</span><span class="sxs-lookup"><span data-stu-id="69bbb-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="69bbb-273">注意：如果用戶端在內部網路中，則媒體會流向 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="69bbb-274">您可以在您的 NAT 裝置上設定頭髮釘選，這樣通信量就不會離開商業網路裝置。</span><span class="sxs-lookup"><span data-stu-id="69bbb-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="69bbb-275">頻寬</span><span class="sxs-lookup"><span data-stu-id="69bbb-275">Traffic</span></span> | <span data-ttu-id="69bbb-276">從</span><span class="sxs-lookup"><span data-stu-id="69bbb-276">From</span></span> | <span data-ttu-id="69bbb-277">自</span><span class="sxs-lookup"><span data-stu-id="69bbb-277">To</span></span> | <span data-ttu-id="69bbb-278">來源埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-278">Source port</span></span> | <span data-ttu-id="69bbb-279">目的地埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="69bbb-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-280">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-281">用戶端</span><span class="sxs-lookup"><span data-stu-id="69bbb-281">Client</span></span> | <span data-ttu-id="69bbb-282">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-282">SBC</span></span> | <span data-ttu-id="69bbb-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="69bbb-283">50 000 – 50 019</span></span>  | <span data-ttu-id="69bbb-284">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-284">Defined on the SBC</span></span> |
| <span data-ttu-id="69bbb-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-285">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-286">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-286">SBC</span></span> | <span data-ttu-id="69bbb-287">用戶端</span><span class="sxs-lookup"><span data-stu-id="69bbb-287">Client</span></span> | <span data-ttu-id="69bbb-288">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-288">Defined on the SBC</span></span> | <span data-ttu-id="69bbb-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="69bbb-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="69bbb-290">如果您的網路裝置會轉譯用戶端的來源埠，請確定已在網路設備與 SBC 之間開啟已轉換的埠。</span><span class="sxs-lookup"><span data-stu-id="69bbb-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="69bbb-291">使用傳輸繼電器的需求</span><span class="sxs-lookup"><span data-stu-id="69bbb-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="69bbb-292">對於非旁路情況) ，傳輸繼電器與媒體處理器 (的範圍相同：</span><span class="sxs-lookup"><span data-stu-id="69bbb-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="69bbb-293">Microsoft 365、Office 365 及 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="69bbb-294">52.112.0.0/14 (從52.112.0.1 至52.115.255.254 的 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="69bbb-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="69bbb-295">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="69bbb-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="69bbb-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="69bbb-297">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="69bbb-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="69bbb-298">52.127.88.0/21</span></span>


<span data-ttu-id="69bbb-299">[小組傳輸中繼] 的埠範圍 (適用于所有環境) ，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="69bbb-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="69bbb-300">頻寬</span><span class="sxs-lookup"><span data-stu-id="69bbb-300">Traffic</span></span> | <span data-ttu-id="69bbb-301">從</span><span class="sxs-lookup"><span data-stu-id="69bbb-301">From</span></span> | <span data-ttu-id="69bbb-302">自</span><span class="sxs-lookup"><span data-stu-id="69bbb-302">To</span></span> | <span data-ttu-id="69bbb-303">來源埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-303">Source port</span></span> | <span data-ttu-id="69bbb-304">目的地埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="69bbb-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-305">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-306">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="69bbb-306">Transport Relay</span></span> | <span data-ttu-id="69bbb-307">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-307">SBC</span></span> | <span data-ttu-id="69bbb-308">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="69bbb-308">50 000 -59 999</span></span>    | <span data-ttu-id="69bbb-309">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-309">Defined on the SBC</span></span> |
| <span data-ttu-id="69bbb-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-310">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-311">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-311">SBC</span></span> | <span data-ttu-id="69bbb-312">傳輸中繼</span><span class="sxs-lookup"><span data-stu-id="69bbb-312">Transport Relay</span></span> | <span data-ttu-id="69bbb-313">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-313">Defined on the SBC</span></span> | <span data-ttu-id="69bbb-314">50 000 – 59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="69bbb-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="69bbb-315">Microsoft 建議在 SBC 上每個併發呼叫至少有兩個埠。</span><span class="sxs-lookup"><span data-stu-id="69bbb-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="69bbb-316">因為 Microsoft 有兩個版本的傳輸繼電器，所以需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="69bbb-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="69bbb-317">v4，只能與埠範圍 50 000 搭配 59 999</span><span class="sxs-lookup"><span data-stu-id="69bbb-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="69bbb-318">v6 是與埠3478、3479搭配使用</span><span class="sxs-lookup"><span data-stu-id="69bbb-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="69bbb-319">目前，媒體旁路只支援 v4 版的傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="69bbb-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="69bbb-320">我們會在未來推出 v6 支援。</span><span class="sxs-lookup"><span data-stu-id="69bbb-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="69bbb-321">您需要開啟埠3478和3479以進行轉換。</span><span class="sxs-lookup"><span data-stu-id="69bbb-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="69bbb-322">當 Microsoft 使用媒體旁路支援 v6 傳輸中繼時，您就不需要重新設定您的網路設備或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="69bbb-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="69bbb-323">使用媒體處理器的需求</span><span class="sxs-lookup"><span data-stu-id="69bbb-323">Requirements for using media processors</span></span>

<span data-ttu-id="69bbb-324">媒體處理器總是位於語音應用程式和 Web 用戶端的媒體路徑中 (例如，Edge 或 Google Chrome 中的團隊用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="69bbb-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="69bbb-325">其需求與非旁路設定相同。</span><span class="sxs-lookup"><span data-stu-id="69bbb-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="69bbb-326">媒體流量的 IP 範圍是</span><span class="sxs-lookup"><span data-stu-id="69bbb-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="69bbb-327">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="69bbb-328">52.112.0.0/14 (從52.112.0.1 至52.115.255.254 的 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="69bbb-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="69bbb-329">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="69bbb-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="69bbb-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="69bbb-331">Office 365 GCC 高環境</span><span class="sxs-lookup"><span data-stu-id="69bbb-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="69bbb-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="69bbb-332">52.127.88.0/21</span></span>

<span data-ttu-id="69bbb-333">媒體處理器的埠範圍 (適用于所有環境) ，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="69bbb-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="69bbb-334">頻寬</span><span class="sxs-lookup"><span data-stu-id="69bbb-334">Traffic</span></span> | <span data-ttu-id="69bbb-335">從</span><span class="sxs-lookup"><span data-stu-id="69bbb-335">From</span></span> | <span data-ttu-id="69bbb-336">自</span><span class="sxs-lookup"><span data-stu-id="69bbb-336">To</span></span> | <span data-ttu-id="69bbb-337">來源埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-337">Source port</span></span> | <span data-ttu-id="69bbb-338">目的地埠</span><span class="sxs-lookup"><span data-stu-id="69bbb-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="69bbb-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-339">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-340">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="69bbb-340">Media Processor</span></span> | <span data-ttu-id="69bbb-341">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-341">SBC</span></span> | <span data-ttu-id="69bbb-342">3478、3479和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="69bbb-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="69bbb-343">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-343">Defined on the SBC</span></span> |
| <span data-ttu-id="69bbb-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="69bbb-344">UDP/SRTP</span></span> | <span data-ttu-id="69bbb-345">SBC</span><span class="sxs-lookup"><span data-stu-id="69bbb-345">SBC</span></span> | <span data-ttu-id="69bbb-346">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="69bbb-346">Media Processor</span></span> | <span data-ttu-id="69bbb-347">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="69bbb-347">Defined on the SBC</span></span> | <span data-ttu-id="69bbb-348">3478、3479和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="69bbb-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="69bbb-349">針對媒體旁路和非媒體旁路設定個別 trunks</span><span class="sxs-lookup"><span data-stu-id="69bbb-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="69bbb-350">如果您是從非媒體旁路移植到媒體旁路，且想要在將所有使用方式移植到媒體旁路之前確認功能，您可以建立個別的主幹及個別的線上語音路由原則，以路由到媒體旁路幹線並指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="69bbb-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="69bbb-351">高層次的設定步驟：</span><span class="sxs-lookup"><span data-stu-id="69bbb-351">High-level configuration steps:</span></span>

- <span data-ttu-id="69bbb-352">識別要測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="69bbb-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="69bbb-353">使用不同的 Fqdn 建立兩個不同的 trunks：一個為媒體略過啟用;另一種是。</span><span class="sxs-lookup"><span data-stu-id="69bbb-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="69bbb-354">兩個 trunks 都指向同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="69bbb-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="69bbb-355">TLS SIP 信號的埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="69bbb-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="69bbb-356">媒體埠必須相同。</span><span class="sxs-lookup"><span data-stu-id="69bbb-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="69bbb-357">建立新的線上語音路由策略，並將媒體旁路主幹指派給與此原則之 PSTN 使用相關聯的對應路由。</span><span class="sxs-lookup"><span data-stu-id="69bbb-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="69bbb-358">將新的線上語音路由策略指派給已識別用來測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="69bbb-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="69bbb-359">下列範例說明這個邏輯。</span><span class="sxs-lookup"><span data-stu-id="69bbb-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="69bbb-360">使用者組</span><span class="sxs-lookup"><span data-stu-id="69bbb-360">Set of users</span></span> | <span data-ttu-id="69bbb-361">使用者數量</span><span class="sxs-lookup"><span data-stu-id="69bbb-361">Number of users</span></span> | <span data-ttu-id="69bbb-362">在 OVRP 中指派中繼 FQDN</span><span class="sxs-lookup"><span data-stu-id="69bbb-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="69bbb-363">已啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="69bbb-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="69bbb-364">非媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="69bbb-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="69bbb-365">980</span><span class="sxs-lookup"><span data-stu-id="69bbb-365">980</span></span> | <span data-ttu-id="69bbb-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="69bbb-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="69bbb-367">滿足</span><span class="sxs-lookup"><span data-stu-id="69bbb-367">true</span></span>
<span data-ttu-id="69bbb-368">具有媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="69bbb-368">Users with media bypass trunk</span></span> | <span data-ttu-id="69bbb-369">20</span><span class="sxs-lookup"><span data-stu-id="69bbb-369">20</span></span> | <span data-ttu-id="69bbb-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="69bbb-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="69bbb-371">虛假</span><span class="sxs-lookup"><span data-stu-id="69bbb-371">false</span></span> | 

<span data-ttu-id="69bbb-372">兩個 trunks 都可以指向相同的同一個 SBC，且具有相同的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="69bbb-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="69bbb-373">SBC 上的 TLS 信號埠必須不同，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="69bbb-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="69bbb-374">注意：您必須確認您的憑證同時支援這兩個 trunks。</span><span class="sxs-lookup"><span data-stu-id="69bbb-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="69bbb-375">在 SAN 中，您必須使用兩個名稱 ( **sbc1.contoso.com** 和 **sbc2.contoso.com** ) 或擁有萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="69bbb-375">In SAN, you need to have two names ( **sbc1.contoso.com** and **sbc2.contoso.com** ) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69bbb-376">![顯示兩個 trunks 可以指向同一個公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="69bbb-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="69bbb-377">如需如何在同一個 SBC 上設定兩個 trunks 的相關資訊，請參閱您的 SBC 轉銷商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="69bbb-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="69bbb-378">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="69bbb-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="69bbb-379">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="69bbb-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="69bbb-380">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="69bbb-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="69bbb-381">TE-系統 (anynode) 部署檔</span><span class="sxs-lookup"><span data-stu-id="69bbb-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="69bbb-382">媒體略過支援的用戶端端點</span><span class="sxs-lookup"><span data-stu-id="69bbb-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="69bbb-383">所有獨立團隊桌面用戶端、Android 和 iOS 用戶端與團隊手機裝置支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="69bbb-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="69bbb-384">對於不支援媒體旁路的所有其他端點，我們會將呼叫轉換為非旁路，即使它是繞過撥號通話。</span><span class="sxs-lookup"><span data-stu-id="69bbb-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="69bbb-385">這會自動發生，不需要系統管理員執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="69bbb-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="69bbb-386">這包括商務用 Skype 3PIP 手機，以及支援直接路由 (呼叫的小組網頁用戶端，這些用戶端是在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上執行的 WebRTC 用戶端。</span><span class="sxs-lookup"><span data-stu-id="69bbb-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="69bbb-387">另請參閱</span><span class="sxs-lookup"><span data-stu-id="69bbb-387">See also</span></span>

[<span data-ttu-id="69bbb-388">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="69bbb-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


