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
description: 瞭解如何使用電話系統直接路由規劃媒體旁路，這可讓您縮短媒體流量的路徑並提升績效。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e21007c31dca540e4f659aad627911b4aec2e456
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460863"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="d996c-103">媒體旁路搭配直接路由方案</span><span class="sxs-lookup"><span data-stu-id="d996c-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="d996c-104">關於使用直接路由旁路的媒體</span><span class="sxs-lookup"><span data-stu-id="d996c-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="d996c-105">媒體旁路可讓您縮短媒體流量的路徑，並減少傳輸中的躍點數目，以提升績效。</span><span class="sxs-lookup"><span data-stu-id="d996c-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="d996c-106">媒體旁路時，媒體會保留在會話邊界控制器 (SBC) 與用戶端之間，而不是透過 Microsoft Phone System 傳送。</span><span class="sxs-lookup"><span data-stu-id="d996c-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="d996c-107">若要設定媒體旁路，SBC 和用戶端必須位於相同的位置或網路中。</span><span class="sxs-lookup"><span data-stu-id="d996c-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="d996c-108">您可以使用 **Set-CSOnlinePSTNGateway** 命令，將 **-MediaBypass** 參數設為 True 或 False，控制每個 SBC 的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="d996c-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="d996c-109">如果您啟用媒體旁路，並不表示所有媒體流量都會留在公司網路中。</span><span class="sxs-lookup"><span data-stu-id="d996c-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="d996c-110">本文將說明不同情況下的通話流程。</span><span class="sxs-lookup"><span data-stu-id="d996c-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="d996c-111">下圖說明通話流程與媒體旁路和不含媒體旁路的差異。</span><span class="sxs-lookup"><span data-stu-id="d996c-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="d996c-112">若沒有媒體旁路，當用戶端撥打或接聽電話時，SBC、Microsoft Phone System 和 Teams 用戶端之間的訊號和媒體流程，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="d996c-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-113">![顯示訊號與媒體流程，而不忽略媒體](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="d996c-114">但我們假設使用者與 SBC 位於相同的建築物或網路中。</span><span class="sxs-lookup"><span data-stu-id="d996c-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="d996c-115">例如，假設位於 [星展圖》 大樓的使用者撥打給 PSTN 使用者：</span><span class="sxs-lookup"><span data-stu-id="d996c-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="d996c-116">**媒體若不** 經由媒體旁路，將會透過 (布建 Microsoft 資料中心的) ，並回到位於卡特的 SBC。</span><span class="sxs-lookup"><span data-stu-id="d996c-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="d996c-117">由於 SBC 位於歐洲，而 Microsoft 使用離 SBC 最近的資料中心，因此會選取歐洲資料中心。</span><span class="sxs-lookup"><span data-stu-id="d996c-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="d996c-118">雖然這個方法不會因為 Microsoft 網路中大部分地區的流量優化而影響通話品質，但流量有不必要的迴圈。</span><span class="sxs-lookup"><span data-stu-id="d996c-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="d996c-119">**媒體旁** 路時，媒體會直接保留在 Teams 使用者與 SBC 之間，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="d996c-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d996c-120">![使用媒體旁路顯示訊號與媒體流程](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="d996c-121">媒體旁路會運用稱為互動式連接新 (ICE) Teams 用戶端上的通訊協定，以及 SBC 上的 ICE lite。</span><span class="sxs-lookup"><span data-stu-id="d996c-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="d996c-122">這些通訊協定可讓直接路由使用最直接的媒體路徑，以獲得最佳品質。</span><span class="sxs-lookup"><span data-stu-id="d996c-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="d996c-123">ICE 和 ICE Lite 是 WebRTC 標準。</span><span class="sxs-lookup"><span data-stu-id="d996c-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="d996c-124">有關這些通訊協定的詳細資訊，請參閱 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="d996c-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="d996c-125">通話流程與防火牆規劃</span><span class="sxs-lookup"><span data-stu-id="d996c-125">Call flow and firewall planning</span></span>

<span data-ttu-id="d996c-126">通話流程與防火牆規劃取決於使用者是否可以直接存取 SBC 的公用 IP 位址，以及使用者是否位於網路內外。</span><span class="sxs-lookup"><span data-stu-id="d996c-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="d996c-127">如果使用者可以直接存取 SBC 的公用 IP 位址，則通話流程</span><span class="sxs-lookup"><span data-stu-id="d996c-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="d996c-128">如果使用者可以直接存取 SBC 的公用 IP 位址，通話流程如下：</span><span class="sxs-lookup"><span data-stu-id="d996c-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="d996c-129">對於媒體旁路，Teams 用戶端必須能存取 SBC 的公用 IP 位址，即使從內部網路也一樣。</span><span class="sxs-lookup"><span data-stu-id="d996c-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="d996c-130">如果不需要直接媒體，媒體可以透過傳輸轉場流程。</span><span class="sxs-lookup"><span data-stu-id="d996c-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="d996c-131">當使用者與 SBC 位於同一棟大樓和/或網路中時，建議的解決方案是移除媒體路徑中的 Microsoft Cloud 元件。</span><span class="sxs-lookup"><span data-stu-id="d996c-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="d996c-132">訊號一直透過 Microsoft 雲端流動。</span><span class="sxs-lookup"><span data-stu-id="d996c-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="d996c-133">下圖顯示啟用媒體旁路時通話流程、用戶端在內部，且用戶端可以直接 (SBC 的公用 IP) ：</span><span class="sxs-lookup"><span data-stu-id="d996c-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="d996c-134">路徑的箭號和數值會與 Microsoft Teams 通話 [流量一樣](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)。</span><span class="sxs-lookup"><span data-stu-id="d996c-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="d996c-135">SIP 訊號一直採用 4' 和 4' 路徑 (視交通路線) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="d996c-136">媒體會保持為本地，並採用路徑 5b。</span><span class="sxs-lookup"><span data-stu-id="d996c-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-137">![顯示已啟用媒體旁路的通話流程，用戶端在內部](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="d996c-138">如果使用者無法存取 SBC 的公用 IP 位址，則通話流程</span><span class="sxs-lookup"><span data-stu-id="d996c-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="d996c-139">以下說明如果使用者無法存取 SBC 的公用 IP 位址，通話流程。</span><span class="sxs-lookup"><span data-stu-id="d996c-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="d996c-140">例如，假設使用者是外部使用者，而租使用者系統管理員決定不對網際網路中的每個人開啟 SBC 的公用 IP 位址，但只開放給 Microsoft Cloud。</span><span class="sxs-lookup"><span data-stu-id="d996c-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="d996c-141">流量的內部元件可以透過 Teams 傳輸轉場流程。</span><span class="sxs-lookup"><span data-stu-id="d996c-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="d996c-142">請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="d996c-142">Consider the following:</span></span>

- <span data-ttu-id="d996c-143">使用 Teams 傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="d996c-144">針對媒體旁路，Microsoft 使用的傳輸轉場版本需要在 Teams 傳輸轉場和 SBC (之間開啟埠 50 000 到 59 999 (，我們計畫未來移往只需要 3478 和 3479 個埠) 的版本。</span><span class="sxs-lookup"><span data-stu-id="d996c-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="d996c-145">下圖顯示啟用媒體旁路時通話流程、用戶端為外部，且用戶端無法到達會話框線控制器的公用 IP 位址 (媒體會由 Teams 傳輸轉場) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="d996c-146">路徑的箭號和數值會與 Microsoft Teams 通話 [流量一樣](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)。</span><span class="sxs-lookup"><span data-stu-id="d996c-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="d996c-147">媒體會透過路徑 3、3'、4 和 4' 進行轉場</span><span class="sxs-lookup"><span data-stu-id="d996c-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-148">![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="d996c-149">如果使用者位於網路外部，且可存取 SBC 的公用 IP，則通話流程</span><span class="sxs-lookup"><span data-stu-id="d996c-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="d996c-150">這不是建議的配置，因為它不會利用 Teams 傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="d996c-151">不過，您應該考慮先前使用者無法存取 SBC 公用 IP 位址的情況。</span><span class="sxs-lookup"><span data-stu-id="d996c-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="d996c-152">下圖顯示啟用媒體旁路、用戶端為外部，且用戶端可以到達 SBC 的公用 IP 位址 (直接媒體) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="d996c-153">路徑的箭號和數值符合 Microsoft Teams 通話 [流程一](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 文。</span><span class="sxs-lookup"><span data-stu-id="d996c-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="d996c-154">SIP 訊號一定採用路徑 3 和 3' (視交通路線) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="d996c-155">媒體會使用路徑 2 流動。</span><span class="sxs-lookup"><span data-stu-id="d996c-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-156">![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="d996c-157">媒體處理器與傳輸轉場的使用</span><span class="sxs-lookup"><span data-stu-id="d996c-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="d996c-158">Microsoft Cloud 有兩個元件可以在媒體流量的路徑中：媒體處理器和傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="d996c-159">媒體處理器是一種公開元件，可處理非旁路情況下的媒體，並處理語音應用程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="d996c-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="d996c-160">媒體處理器一直位於非旁路使用者通話的路徑中，但絕不會在旁路通話的路徑中。</span><span class="sxs-lookup"><span data-stu-id="d996c-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="d996c-161">媒體處理器永遠位於所有語音應用程式的路徑中，例如通話停駐、組織自動語音留言和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d996c-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="d996c-162">傳輸轉送是用來連接到最近的傳輸服務，以傳送即時流量。</span><span class="sxs-lookup"><span data-stu-id="d996c-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="d996c-163">傳輸轉會可能位於旁路的通話路徑中 ，這些通話來自或目的地是使用者，視使用者的目前位置及網路設置方式而不同。</span><span class="sxs-lookup"><span data-stu-id="d996c-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="d996c-164">下圖顯示兩個通話流程：一個已啟用媒體旁路，另一個已停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="d996c-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="d996c-165">請注意，此圖表只會說明來自或目的地使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="d996c-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="d996c-166">媒體控制器是 Azure 中的一種微型服務，可指派媒體處理器，並建立 SDP (會話描述) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d996c-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="d996c-167">SIP Proxy 是一個元件，將 Teams 中所使用的 HTTP REST 訊號轉換為 SIP。</span><span class="sxs-lookup"><span data-stu-id="d996c-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-168">![顯示啟用和停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="d996c-169">下表摘要列出媒體處理器與傳輸轉場的差異。</span><span class="sxs-lookup"><span data-stu-id="d996c-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="d996c-170">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="d996c-170">Media Processors</span></span> | <span data-ttu-id="d996c-171">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="d996c-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="d996c-172">使用者非旁路通話的媒體路徑</span><span class="sxs-lookup"><span data-stu-id="d996c-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="d996c-173">總是</span><span class="sxs-lookup"><span data-stu-id="d996c-173">Always</span></span> | <span data-ttu-id="d996c-174">如果用戶端無法直接到達媒體處理器</span><span class="sxs-lookup"><span data-stu-id="d996c-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="d996c-175">使用者旁路通話的媒體路徑</span><span class="sxs-lookup"><span data-stu-id="d996c-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="d996c-176">從來 沒有</span><span class="sxs-lookup"><span data-stu-id="d996c-176">Never</span></span> | <span data-ttu-id="d996c-177">如果用戶端無法到達公用 IP 位址上的 SBC</span><span class="sxs-lookup"><span data-stu-id="d996c-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="d996c-178">語音應用程式的媒體路徑</span><span class="sxs-lookup"><span data-stu-id="d996c-178">In media path for voice applications</span></span> | <span data-ttu-id="d996c-179">總是</span><span class="sxs-lookup"><span data-stu-id="d996c-179">Always</span></span> | <span data-ttu-id="d996c-180">從來 沒有</span><span class="sxs-lookup"><span data-stu-id="d996c-180">Never</span></span> | 
<span data-ttu-id="d996c-181">可以執行 B2BUA (轉) \*</span><span class="sxs-lookup"><span data-stu-id="d996c-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="d996c-182">是</span><span class="sxs-lookup"><span data-stu-id="d996c-182">Yes</span></span> | <span data-ttu-id="d996c-183">否，只會在端點之間轉傳音訊</span><span class="sxs-lookup"><span data-stu-id="d996c-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="d996c-184">全球實例數目和位置</span><span class="sxs-lookup"><span data-stu-id="d996c-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="d996c-185">總計 10 個：美國東部和西部 2 個;2 在荷蘭，在愛爾蘭及愛爾蘭;香港和新加坡有 2 個;日本為 2;2 位於澳洲東部及東南亞</span><span class="sxs-lookup"><span data-stu-id="d996c-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="d996c-186">多個</span><span class="sxs-lookup"><span data-stu-id="d996c-186">Multiple</span></span>

<span data-ttu-id="d996c-187">IP 範圍為：</span><span class="sxs-lookup"><span data-stu-id="d996c-187">The IP ranges are:</span></span>
- <span data-ttu-id="d996c-188">52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="d996c-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="d996c-189">2014/52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) </span><span class="sxs-lookup"><span data-stu-id="d996c-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="d996c-190">\* 轉碼說明：</span><span class="sxs-lookup"><span data-stu-id="d996c-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="d996c-191">媒體處理器是 B2BUA，這表示它可以在 MP 和 S) BC (之間將編解碼器變更為 (，從 Teams 用戶端變更為 MP 和 G.711。</span><span class="sxs-lookup"><span data-stu-id="d996c-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="d996c-192">傳輸轉場不是 B2BUA，這表示編解碼器不會在用戶端和 SBC 之間變更，即使流量是透過轉場進行。</span><span class="sxs-lookup"><span data-stu-id="d996c-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="d996c-193">如果系統已針對媒體旁路設置樹線，則使用 Teams 媒體處理器</span><span class="sxs-lookup"><span data-stu-id="d996c-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="d996c-194">在下列情況下，Teams 媒體處理器一直在媒體路徑中插入：</span><span class="sxs-lookup"><span data-stu-id="d996c-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="d996c-195">通話從 1：1 升級為群組通話</span><span class="sxs-lookup"><span data-stu-id="d996c-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="d996c-196">通話正要撥打到 Teams 的聯盟使用者</span><span class="sxs-lookup"><span data-stu-id="d996c-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="d996c-197">呼叫已轉接或轉接給商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="d996c-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="d996c-198">請確定您的 SBC 能夠存取媒體處理器和傳輸轉場範圍，如下所述。</span><span class="sxs-lookup"><span data-stu-id="d996c-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="d996c-199">SIP 訊號：FQDN</span><span class="sxs-lookup"><span data-stu-id="d996c-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="d996c-200">針對 SIP 訊號，FQDN 和防火牆需求與非旁路案例相同。</span><span class="sxs-lookup"><span data-stu-id="d996c-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="d996c-201">直接路由提供于下列 Microsoft 365 或 Office 365 環境：</span><span class="sxs-lookup"><span data-stu-id="d996c-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="d996c-202">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="d996c-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="d996c-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="d996c-203">Office 365 GCC</span></span>
- <span data-ttu-id="d996c-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="d996c-204">Office 365 GCC High</span></span>
- <span data-ttu-id="d996c-205">Office 365 DoD 深入瞭解 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 和美國政府環境，例如 GCC、GCC High 和 DoD。</span><span class="sxs-lookup"><span data-stu-id="d996c-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="d996c-206">Microsoft 365、Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="d996c-207">直接路由的連接點為下列三個 FQDN：</span><span class="sxs-lookup"><span data-stu-id="d996c-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="d996c-208">**sip.pstnhub.microsoft.com** 全域 FQDN – 必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="d996c-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="d996c-209">當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會回到指向指派給 SBC 的主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d996c-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="d996c-210">此工作分派是根據資料中心的績效計量，以及 SBC 的地理位置鄰近。</span><span class="sxs-lookup"><span data-stu-id="d996c-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="d996c-211">所回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d996c-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="d996c-212">**sip2.pstnhub.microsoft.com** - 次要 FQDN – 地理上會與第二個優先順序區域進行地圖。</span><span class="sxs-lookup"><span data-stu-id="d996c-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="d996c-213">**sip3.pstnhub.microsoft.com** 線 FQDN – 地理上會與第三個優先順序區域進行地圖。</span><span class="sxs-lookup"><span data-stu-id="d996c-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="d996c-214">您必須放置這三個 FQDN，才能：</span><span class="sxs-lookup"><span data-stu-id="d996c-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="d996c-215">查詢第一個 FQDN (，以提供最佳體驗，讓負載較少且最接近指派的 SBC 資料中心) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="d996c-216">從 SBC 建立與遇到暫時問題的資料中心的連接時，提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="d996c-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="d996c-217">詳細資訊請參閱下方的容錯移轉機制。</span><span class="sxs-lookup"><span data-stu-id="d996c-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="d996c-218">FQDNS **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com** 和sip3.pstnhub.microsoft.com **會解析** 為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="d996c-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="d996c-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="d996c-219">52.114.148.0</span></span>
- <span data-ttu-id="d996c-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="d996c-220">52.114.132.46</span></span>
- <span data-ttu-id="d996c-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="d996c-221">52.114.16.74</span></span>
- <span data-ttu-id="d996c-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="d996c-222">52.114.20.29</span></span>
- <span data-ttu-id="d996c-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="d996c-223">52.114.75.24</span></span>
- <span data-ttu-id="d996c-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="d996c-224">52.114.76.76</span></span>
- <span data-ttu-id="d996c-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="d996c-225">52.114.7.24</span></span>
- <span data-ttu-id="d996c-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="d996c-226">52.114.14.70</span></span>

<span data-ttu-id="d996c-227">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。</span><span class="sxs-lookup"><span data-stu-id="d996c-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="d996c-228">如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d996c-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="d996c-229">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="d996c-230">直接路由的連接點為下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="d996c-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="d996c-231">**sip.pstnhub.dod.teams.microsoft.us** - 全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d996c-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="d996c-232">由於 Office 365 DoD 環境只存在於美國資料中心，因此沒有次要和環性 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d996c-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="d996c-233">FQDN – sip.pstnhub.dod.teams.microsoft.us會解析為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="d996c-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="d996c-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="d996c-234">52.127.64.33</span></span>
- <span data-ttu-id="d996c-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="d996c-235">52.127.68.34</span></span>

<span data-ttu-id="d996c-236">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。</span><span class="sxs-lookup"><span data-stu-id="d996c-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="d996c-237">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d996c-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="d996c-238">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="d996c-239">直接路由的連接點為下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="d996c-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="d996c-240">**sip.pstnhub.gov.teams.microsoft.us** - 全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d996c-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="d996c-241">由於 GCC High 環境只存在於美國資料中心，因此沒有次要和小費 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d996c-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="d996c-242">FQDN – sip.pstnhub.gov.teams.microsoft.us會解析為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="d996c-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="d996c-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="d996c-243">52.127.88.59</span></span>
- <span data-ttu-id="d996c-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="d996c-244">52.127.92.64</span></span>

<span data-ttu-id="d996c-245">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自該位址的訊號。</span><span class="sxs-lookup"><span data-stu-id="d996c-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="d996c-246">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d996c-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="d996c-247">SIP 訊號：埠</span><span class="sxs-lookup"><span data-stu-id="d996c-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="d996c-248">針對提供直接路由的所有 Office 365 環境，埠需求相同：</span><span class="sxs-lookup"><span data-stu-id="d996c-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="d996c-249">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="d996c-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="d996c-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="d996c-250">Office 365 GCC</span></span>
- <span data-ttu-id="d996c-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="d996c-251">Office 365 GCC High</span></span>
- <span data-ttu-id="d996c-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="d996c-252">Office 365 DoD</span></span>

<span data-ttu-id="d996c-253">您必須使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="d996c-253">You must use the following ports:</span></span>

| <span data-ttu-id="d996c-254">交通</span><span class="sxs-lookup"><span data-stu-id="d996c-254">Traffic</span></span> | <span data-ttu-id="d996c-255">從</span><span class="sxs-lookup"><span data-stu-id="d996c-255">From</span></span> | <span data-ttu-id="d996c-256">自</span><span class="sxs-lookup"><span data-stu-id="d996c-256">To</span></span> | <span data-ttu-id="d996c-257">來源埠</span><span class="sxs-lookup"><span data-stu-id="d996c-257">Source port</span></span> | <span data-ttu-id="d996c-258">目的地埠</span><span class="sxs-lookup"><span data-stu-id="d996c-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="d996c-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="d996c-259">SIP/TLS</span></span>| <span data-ttu-id="d996c-260">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="d996c-260">SIP Proxy</span></span> | <span data-ttu-id="d996c-261">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-261">SBC</span></span> | <span data-ttu-id="d996c-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="d996c-262">1024 - 65535</span></span> | <span data-ttu-id="d996c-263">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-263">Defined on the SBC</span></span> |
| <span data-ttu-id="d996c-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="d996c-264">SIP/TLS</span></span> | <span data-ttu-id="d996c-265">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-265">SBC</span></span> | <span data-ttu-id="d996c-266">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="d996c-266">SIP Proxy</span></span> | <span data-ttu-id="d996c-267">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-267">Defined on the SBC</span></span> | <span data-ttu-id="d996c-268">5061</span><span class="sxs-lookup"><span data-stu-id="d996c-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="d996c-269">媒體流量：IP 和埠範圍</span><span class="sxs-lookup"><span data-stu-id="d996c-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="d996c-270">媒體流量在 SBC 和 Teams 用戶端之間流動 ，如果可直接連接可以使用，或者如果用戶端無法使用公用 IP 位址到達 SBC，則媒體流量會透過 Teams 傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="d996c-271">Teams 用戶端與 SBC (之間的直接媒體流量) </span><span class="sxs-lookup"><span data-stu-id="d996c-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="d996c-272">用戶端必須能存取指定的埠 (請參閱) SBC 公用 IP 位址上的資料表。</span><span class="sxs-lookup"><span data-stu-id="d996c-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="d996c-273">注意：如果用戶端位於內部網路中，媒體會流向 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d996c-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="d996c-274">您可以在 NAT 裝置上設定美髮釘釘，讓流量不會離開商業網路設備。</span><span class="sxs-lookup"><span data-stu-id="d996c-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="d996c-275">交通</span><span class="sxs-lookup"><span data-stu-id="d996c-275">Traffic</span></span> | <span data-ttu-id="d996c-276">從</span><span class="sxs-lookup"><span data-stu-id="d996c-276">From</span></span> | <span data-ttu-id="d996c-277">自</span><span class="sxs-lookup"><span data-stu-id="d996c-277">To</span></span> | <span data-ttu-id="d996c-278">來源埠</span><span class="sxs-lookup"><span data-stu-id="d996c-278">Source port</span></span> | <span data-ttu-id="d996c-279">目的地埠</span><span class="sxs-lookup"><span data-stu-id="d996c-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="d996c-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-280">UDP/SRTP</span></span> | <span data-ttu-id="d996c-281">用戶端</span><span class="sxs-lookup"><span data-stu-id="d996c-281">Client</span></span> | <span data-ttu-id="d996c-282">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-282">SBC</span></span> | <span data-ttu-id="d996c-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="d996c-283">50 000 – 50 019</span></span>  | <span data-ttu-id="d996c-284">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-284">Defined on the SBC</span></span> |
| <span data-ttu-id="d996c-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-285">UDP/SRTP</span></span> | <span data-ttu-id="d996c-286">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-286">SBC</span></span> | <span data-ttu-id="d996c-287">用戶端</span><span class="sxs-lookup"><span data-stu-id="d996c-287">Client</span></span> | <span data-ttu-id="d996c-288">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-288">Defined on the SBC</span></span> | <span data-ttu-id="d996c-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="d996c-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="d996c-290">如果您有可轉換用戶端來源埠的網路裝置，請確定已翻譯的埠在網路設備和 SBC 之間開啟。</span><span class="sxs-lookup"><span data-stu-id="d996c-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="d996c-291">使用傳輸轉場的需求</span><span class="sxs-lookup"><span data-stu-id="d996c-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="d996c-292">傳輸轉場與媒體處理器的範圍相同， (非旁路情況下) ：</span><span class="sxs-lookup"><span data-stu-id="d996c-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="d996c-293">Microsoft 365、Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="d996c-294">52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="d996c-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="d996c-295">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="d996c-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="d996c-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="d996c-297">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="d996c-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="d996c-298">52.127.88.0/21</span></span>


<span data-ttu-id="d996c-299">適用于所有環境 (Teams 傳輸轉場) 如下表所示：</span><span class="sxs-lookup"><span data-stu-id="d996c-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="d996c-300">交通</span><span class="sxs-lookup"><span data-stu-id="d996c-300">Traffic</span></span> | <span data-ttu-id="d996c-301">從</span><span class="sxs-lookup"><span data-stu-id="d996c-301">From</span></span> | <span data-ttu-id="d996c-302">自</span><span class="sxs-lookup"><span data-stu-id="d996c-302">To</span></span> | <span data-ttu-id="d996c-303">來源埠</span><span class="sxs-lookup"><span data-stu-id="d996c-303">Source port</span></span> | <span data-ttu-id="d996c-304">目的地埠</span><span class="sxs-lookup"><span data-stu-id="d996c-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="d996c-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-305">UDP/SRTP</span></span> | <span data-ttu-id="d996c-306">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="d996c-306">Transport Relay</span></span> | <span data-ttu-id="d996c-307">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-307">SBC</span></span> | <span data-ttu-id="d996c-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="d996c-308">50 000 -59 999</span></span>    | <span data-ttu-id="d996c-309">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-309">Defined on the SBC</span></span> |
| <span data-ttu-id="d996c-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-310">UDP/SRTP</span></span> | <span data-ttu-id="d996c-311">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-311">SBC</span></span> | <span data-ttu-id="d996c-312">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="d996c-312">Transport Relay</span></span> | <span data-ttu-id="d996c-313">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-313">Defined on the SBC</span></span> | <span data-ttu-id="d996c-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="d996c-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="d996c-315">Microsoft 建議 SBC 上每個同時通話至少兩個埠。</span><span class="sxs-lookup"><span data-stu-id="d996c-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="d996c-316">由於 Microsoft 有兩個版本的傳輸轉場，因此需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="d996c-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="d996c-317">v4，只能使用埠範圍 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="d996c-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="d996c-318">v6，適用于埠 3478、3479</span><span class="sxs-lookup"><span data-stu-id="d996c-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="d996c-319">目前，媒體旁路僅支援 v4 版的傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="d996c-320">我們未來將會推出 v6 的支援。</span><span class="sxs-lookup"><span data-stu-id="d996c-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="d996c-321">您需要開啟埠 3478 和 3479 進行轉場。</span><span class="sxs-lookup"><span data-stu-id="d996c-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="d996c-322">當 Microsoft 推出 v6 傳輸轉場與媒體旁路的支援時，就不需要重新配置您的網路設備或 SBC。</span><span class="sxs-lookup"><span data-stu-id="d996c-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="d996c-323">使用媒體處理器的需求</span><span class="sxs-lookup"><span data-stu-id="d996c-323">Requirements for using media processors</span></span>

<span data-ttu-id="d996c-324">媒體處理器一直位於語音應用程式和網頁用戶端的媒體路徑中 (例如 Edge 或 Google Chrome 中的 Teams 用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="d996c-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="d996c-325">需求與非旁路組組相同。</span><span class="sxs-lookup"><span data-stu-id="d996c-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="d996c-326">媒體流量的 IP 範圍為</span><span class="sxs-lookup"><span data-stu-id="d996c-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="d996c-327">Office 365 和 Office 365 GCC 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="d996c-328">52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="d996c-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="d996c-329">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="d996c-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="d996c-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="d996c-331">Office 365 GCC High 環境</span><span class="sxs-lookup"><span data-stu-id="d996c-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="d996c-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="d996c-332">52.127.88.0/21</span></span>

<span data-ttu-id="d996c-333">適用于所有環境 (媒體處理器的) 範圍如下表所示：</span><span class="sxs-lookup"><span data-stu-id="d996c-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="d996c-334">交通</span><span class="sxs-lookup"><span data-stu-id="d996c-334">Traffic</span></span> | <span data-ttu-id="d996c-335">從</span><span class="sxs-lookup"><span data-stu-id="d996c-335">From</span></span> | <span data-ttu-id="d996c-336">自</span><span class="sxs-lookup"><span data-stu-id="d996c-336">To</span></span> | <span data-ttu-id="d996c-337">來源埠</span><span class="sxs-lookup"><span data-stu-id="d996c-337">Source port</span></span> | <span data-ttu-id="d996c-338">目的地埠</span><span class="sxs-lookup"><span data-stu-id="d996c-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="d996c-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-339">UDP/SRTP</span></span> | <span data-ttu-id="d996c-340">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="d996c-340">Media Processor</span></span> | <span data-ttu-id="d996c-341">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-341">SBC</span></span> | <span data-ttu-id="d996c-342">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="d996c-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="d996c-343">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-343">Defined on the SBC</span></span> |
| <span data-ttu-id="d996c-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="d996c-344">UDP/SRTP</span></span> | <span data-ttu-id="d996c-345">Sbc</span><span class="sxs-lookup"><span data-stu-id="d996c-345">SBC</span></span> | <span data-ttu-id="d996c-346">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="d996c-346">Media Processor</span></span> | <span data-ttu-id="d996c-347">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="d996c-347">Defined on the SBC</span></span> | <span data-ttu-id="d996c-348">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="d996c-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="d996c-349">設定媒體旁路和非媒體旁路的個別中繼</span><span class="sxs-lookup"><span data-stu-id="d996c-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="d996c-350">如果您要從非媒體旁路移至媒體旁路，並想要在所有使用方式移為媒體旁路之前確認功能，您可以建立個別的中繼和個別的線上語音路由策略，以路由至媒體旁路，並指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="d996c-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="d996c-351">高層級組組步驟：</span><span class="sxs-lookup"><span data-stu-id="d996c-351">High-level configuration steps:</span></span>

- <span data-ttu-id="d996c-352">識別要測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="d996c-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="d996c-353">使用不同的 FQDN 建立兩個不同的樹線：一個啟用媒體旁路;另一個不會。</span><span class="sxs-lookup"><span data-stu-id="d996c-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="d996c-354">兩個樹線都指向相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="d996c-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="d996c-355">TLS SIP 訊號的埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="d996c-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="d996c-356">媒體的埠必須相同。</span><span class="sxs-lookup"><span data-stu-id="d996c-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="d996c-357">建立新的線上語音路由策略，並將媒體旁路路由指派給與此政策 PSTN 使用量相關聯的對應路由。</span><span class="sxs-lookup"><span data-stu-id="d996c-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="d996c-358">將新的線上語音路由策略指派給已識別以測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="d996c-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="d996c-359">下列範例說明此邏輯。</span><span class="sxs-lookup"><span data-stu-id="d996c-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="d996c-360">一組使用者</span><span class="sxs-lookup"><span data-stu-id="d996c-360">Set of users</span></span> | <span data-ttu-id="d996c-361">使用者數目</span><span class="sxs-lookup"><span data-stu-id="d996c-361">Number of users</span></span> | <span data-ttu-id="d996c-362">以 OVRP 指派的中繼 FQDN</span><span class="sxs-lookup"><span data-stu-id="d996c-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="d996c-363">已啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="d996c-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="d996c-364">具有非媒體旁路系統的使用者</span><span class="sxs-lookup"><span data-stu-id="d996c-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="d996c-365">980</span><span class="sxs-lookup"><span data-stu-id="d996c-365">980</span></span> | <span data-ttu-id="d996c-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="d996c-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="d996c-367">真</span><span class="sxs-lookup"><span data-stu-id="d996c-367">true</span></span>
<span data-ttu-id="d996c-368">有媒體旁路的使用者</span><span class="sxs-lookup"><span data-stu-id="d996c-368">Users with media bypass trunk</span></span> | <span data-ttu-id="d996c-369">20</span><span class="sxs-lookup"><span data-stu-id="d996c-369">20</span></span> | <span data-ttu-id="d996c-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="d996c-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="d996c-371">假</span><span class="sxs-lookup"><span data-stu-id="d996c-371">false</span></span> | 

<span data-ttu-id="d996c-372">這兩個樹線可以指向擁有相同公用 IP 位址的同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="d996c-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="d996c-373">SBC 上的 TLS 訊號埠必須不同，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="d996c-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="d996c-374">請注意，您必須確定您的憑證支援兩個樹狀線。</span><span class="sxs-lookup"><span data-stu-id="d996c-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="d996c-375">在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 或萬用字元憑證。 </span><span class="sxs-lookup"><span data-stu-id="d996c-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d996c-376">![顯示兩個樹線可以指向具有相同公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="d996c-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="d996c-377">若要瞭解如何在同一個 SBC 上設定兩條樹線，請參閱 SBC 廠商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="d996c-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="d996c-378">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="d996c-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="d996c-379">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="d996c-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="d996c-380">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="d996c-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="d996c-381">TE-Systems (anynode) 部署檔</span><span class="sxs-lookup"><span data-stu-id="d996c-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="d996c-382">媒體旁路支援的用戶端端點</span><span class="sxs-lookup"><span data-stu-id="d996c-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="d996c-383">所有獨立的 Teams 桌面用戶端、Android 和 iOS 用戶端以及 Teams Phone 裝置都支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="d996c-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="d996c-384">對於不支援媒體旁路的所有其他端點，即使通話以旁路通話啟動，我們也會將呼叫轉換為非旁路。</span><span class="sxs-lookup"><span data-stu-id="d996c-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="d996c-385">這會自動發生，而且不需要系統管理員執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="d996c-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="d996c-386">這包括商務用 Skype 3PIP 電話，以及支援在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上直接路由通話 (WebRTC 用戶端的 Teams Web 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d996c-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="d996c-387">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d996c-387">See also</span></span>

[<span data-ttu-id="d996c-388">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="d996c-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


