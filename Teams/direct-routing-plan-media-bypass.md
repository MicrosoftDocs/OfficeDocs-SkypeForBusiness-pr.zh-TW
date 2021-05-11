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
description: 瞭解如何使用直接路由規劃媒體旁電話系統，這可讓您縮短媒體流量的路徑並改善績效。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b6624a81994c1d6797ed996fbcc233fe75f8907
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308352"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="dd6a1-103">媒體旁路搭配直接路由方案</span><span class="sxs-lookup"><span data-stu-id="dd6a1-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="dd6a1-104">關於使用直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="dd6a1-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="dd6a1-105">媒體旁路可讓您縮短媒體流量的路徑，並減少傳輸中的躍點數量，以提升績效。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="dd6a1-106">在媒體旁路時，媒體會保留在會話邊界控制器 (SBC) 與用戶端之間，而不是透過 Microsoft 電話 系統傳送。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="dd6a1-107">若要設定媒體旁路，SBC 和用戶端必須位於相同的位置或網路中。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="dd6a1-108">您可以使用 **Set-CSOnlinePSTNGateway** 命令，將 **-MediaBypass** 參數設為 True 或 false，控制每個 SBC 的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="dd6a1-109">如果您啟用媒體旁路，這不表示所有媒體流量都會維持在公司網路中。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="dd6a1-110">本文將說明不同情況下的通話流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="dd6a1-111">下圖說明通話流程與媒體旁路和無媒體旁路的差異。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="dd6a1-112">若沒有媒體旁路，當用戶端撥打或接收通話時，SBC、Microsoft 電話 System 和 Teams 用戶端之間的訊號和媒體流程，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-113">![顯示沒有媒體旁路的訊號和媒體流程](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="dd6a1-114">但假設使用者與 SBC 位於同一棟大樓或網路中。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="dd6a1-115">例如，假設位於位於德國慕尼克大樓的使用者撥打 PSTN 使用者電話：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="dd6a1-116">**若沒有媒體** 旁路，媒體會透過 (，將 Microsoft 資料中心部署至) ，並回到位於德國的 SBC。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="dd6a1-117">已選取歐洲資料中心，因為 SBC 位於歐洲，而 Microsoft 會使用最接近 SBC 的資料中心。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="dd6a1-118">雖然這個方法不會因為 Microsoft 網路內部流量優化而影響通話品質，但流量有不必要的迴圈。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="dd6a1-119">**在媒體旁** 路時，媒體會直接保留在Teams使用者與 SBC 之間，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="dd6a1-120">![使用媒體旁路顯示訊號和媒體流程](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="dd6a1-121">媒體旁路會利用稱為互動式 (建立) 的通訊協定Teams SBC 上的 ICE lite。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="dd6a1-122">這些通訊協定可讓直接路由使用最直接的媒體路徑，以獲得最佳品質。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="dd6a1-123">ICE 和 ICE Lite 是 WebRTC 標準。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="dd6a1-124">有關這些通訊協定的詳細資訊，請參閱 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="dd6a1-125">通話流程與防火牆規劃</span><span class="sxs-lookup"><span data-stu-id="dd6a1-125">Call flow and firewall planning</span></span>

<span data-ttu-id="dd6a1-126">通話流程與防火牆規劃取決於使用者是否可直接存取 SBC 的公用 IP 位址，以及使用者是否位於網路內外。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="dd6a1-127">如果使用者能直接存取 SBC 的公用 IP 位址，則通話流程</span><span class="sxs-lookup"><span data-stu-id="dd6a1-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="dd6a1-128">如果使用者可以直接存取 SBC 的公用 IP 位址，則通話流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="dd6a1-129">對於媒體旁Teams，用戶端必須能存取 SBC 的公用 IP 位址，即使從內部網路也一樣。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="dd6a1-130">如果不需要直接媒體，媒體可以透過傳輸轉場流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="dd6a1-131">當使用者與 SBC 位於同一棟大樓和/或網路中時，建議您使用這個解決方案：從媒體路徑移除 Microsoft Cloud 元件。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="dd6a1-132">訊號永遠會透過 Microsoft 雲端傳輸。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="dd6a1-133">下圖顯示啟用媒體旁路時通話流程、用戶端為內部，且用戶端可以到達 SBC (媒體的公用 IP 位址) ：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="dd6a1-134">路徑的箭號和數值與通話Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="dd6a1-135">SIP 訊號一直採用 4' 和 4' (視流量方向) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="dd6a1-136">媒體保持為本地，並採用路徑 5b。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-137">![顯示已啟用媒體旁路的通話流程，用戶端為內部](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="dd6a1-138">如果使用者無法存取 SBC 的公用 IP 位址，則通話流程</span><span class="sxs-lookup"><span data-stu-id="dd6a1-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="dd6a1-139">下列說明如果使用者無法存取 SBC 的公用 IP 位址，則通話流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="dd6a1-140">例如，假設使用者是外部使用者，而且租使用者系統管理員決定不將 SBC 的公用 IP 位址開放給網際網路中的每個人，而只會開啟到 Microsoft Cloud。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="dd6a1-141">流量的內部元件可以透過傳輸轉Teams流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="dd6a1-142">請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-142">Consider the following:</span></span>

- <span data-ttu-id="dd6a1-143">Teams使用傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="dd6a1-144">針對媒體旁路，Microsoft 會使用傳輸轉場版本，要求在 Teams 傳輸轉場和 SBC (之間開啟埠 50 000 到 59 999，我們計畫在未來移至需要 3478-3481 埠) 的版本。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="dd6a1-145">下圖顯示啟用媒體旁路、用戶端為外部，且用戶端無法到達會話框線控制器 (媒體的公用 IP 位址時，呼叫流程會由 Teams 傳輸轉) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="dd6a1-146">路徑的箭號和數值與通話Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="dd6a1-147">媒體會透過路徑 3、3'、4 和 4' 轉傳</span><span class="sxs-lookup"><span data-stu-id="dd6a1-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-148">![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="dd6a1-149">如果使用者位於網路外部，且可存取 SBC 的公用 IP，則通話流程</span><span class="sxs-lookup"><span data-stu-id="dd6a1-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="dd6a1-150">這不是建議的配置，因為它不會利用傳輸轉Teams的優點。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="dd6a1-151">相反地，您應該考慮使用者無法存取 SBC 公用 IP 位址的上一個案例。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="dd6a1-152">下圖顯示啟用媒體旁路時通話流程、用戶端為外部，且用戶端可以到達 SBC 的公用 IP 位址 (媒體) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="dd6a1-153">路徑的箭號和數值與通話流程Microsoft Teams[一樣](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="dd6a1-154">SIP 訊號一直採用路徑 3 和 3' (視流量方向) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="dd6a1-155">使用路徑 2 的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-156">![如果使用者無法存取 SBC 的公用 IP，則顯示通話流程](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="dd6a1-157">媒體處理器與傳輸轉場的使用</span><span class="sxs-lookup"><span data-stu-id="dd6a1-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="dd6a1-158">Microsoft Cloud 中的兩個元件可能位在媒體流量的路徑中：媒體處理器和傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="dd6a1-159">媒體處理器是一種公開元件，可處理非旁路情況下的媒體，並處理語音應用程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="dd6a1-160">媒體處理器一直位於使用者非旁路通話的路徑中，但絕不會在未接來電的路徑中。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="dd6a1-161">媒體處理器一直位於所有語音應用程式的路徑中，例如通話駐場、組織自動語音留言和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="dd6a1-162">傳輸轉送是用來連接到最近的傳輸服務，以傳送即時流量。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="dd6a1-163">傳輸轉訊可能位於未接來電的路徑中 ，這些通話可能來自或目的地給使用者，取決於使用者在哪裡，以及網路是如何配置的。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="dd6a1-164">下圖顯示兩個通話流程 ：一個已啟用媒體旁路，另一個已停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="dd6a1-165">圖表只會說明來自或目的地使用者的流量。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="dd6a1-166">媒體控制器是 Azure 中的微服務，可指派媒體處理器，並建立 SDP (會話) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="dd6a1-167">SIP Proxy 是一個元件，將用於 SIP 的 HTTP REST Teams轉換為 SIP。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-168">![顯示已啟用和停用媒體旁路的通話流程](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="dd6a1-169">下表摘要列出媒體處理器與傳輸轉場之間的差異。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="dd6a1-170">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="dd6a1-170">Media Processors</span></span> | <span data-ttu-id="dd6a1-171">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="dd6a1-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="dd6a1-172">針對使用者的非旁路通話的媒體路徑</span><span class="sxs-lookup"><span data-stu-id="dd6a1-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="dd6a1-173">總是</span><span class="sxs-lookup"><span data-stu-id="dd6a1-173">Always</span></span> | <span data-ttu-id="dd6a1-174">如果用戶端無法直接到達媒體處理器</span><span class="sxs-lookup"><span data-stu-id="dd6a1-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="dd6a1-175">在媒體路徑中為使用者進行旁路通話</span><span class="sxs-lookup"><span data-stu-id="dd6a1-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="dd6a1-176">從來 沒有</span><span class="sxs-lookup"><span data-stu-id="dd6a1-176">Never</span></span> | <span data-ttu-id="dd6a1-177">如果用戶端無法到達公用 IP 位址上的 SBC</span><span class="sxs-lookup"><span data-stu-id="dd6a1-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="dd6a1-178">在語音應用程式的媒體路徑中</span><span class="sxs-lookup"><span data-stu-id="dd6a1-178">In media path for voice applications</span></span> | <span data-ttu-id="dd6a1-179">總是</span><span class="sxs-lookup"><span data-stu-id="dd6a1-179">Always</span></span> | <span data-ttu-id="dd6a1-180">從來 沒有</span><span class="sxs-lookup"><span data-stu-id="dd6a1-180">Never</span></span> | 
<span data-ttu-id="dd6a1-181">可以轉譯 B2BUA (B2BUA) \*</span><span class="sxs-lookup"><span data-stu-id="dd6a1-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="dd6a1-182">是</span><span class="sxs-lookup"><span data-stu-id="dd6a1-182">Yes</span></span> | <span data-ttu-id="dd6a1-183">否，只會在端點之間轉傳音訊</span><span class="sxs-lookup"><span data-stu-id="dd6a1-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="dd6a1-184">全球實例數目和位置</span><span class="sxs-lookup"><span data-stu-id="dd6a1-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="dd6a1-185">總計 10 個：美國東部和西部 2 個;2 在荷蘭的阿姆斯特丹和伯林達;香港和新加坡有 2 個;日本為 2;澳洲東部和東南亞的 2 個</span><span class="sxs-lookup"><span data-stu-id="dd6a1-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="dd6a1-186">多個</span><span class="sxs-lookup"><span data-stu-id="dd6a1-186">Multiple</span></span>

<span data-ttu-id="dd6a1-187">IP 範圍為：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-187">The IP ranges are:</span></span>
- <span data-ttu-id="dd6a1-188">52.112.0.0/14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="dd6a1-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="dd6a1-189">52.120.0.0/14 (IP 位址從 52.120.0.1 到 52.123.255.254) </span><span class="sxs-lookup"><span data-stu-id="dd6a1-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="dd6a1-190">\* 轉碼說明：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="dd6a1-191">媒體處理器是 B2BUA，這表示它可以在 MP 和 S) BC (之間將編解碼器從 Teams 用戶端變更為 MP 和 G.711。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="dd6a1-192">傳輸轉場不是 B2BUA，這表示編解碼器永遠不會在用戶端與 SBC 之間變更，即使流量是透過轉場流程。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="dd6a1-193">如果主幹Teams媒體旁路，則使用媒體處理器</span><span class="sxs-lookup"><span data-stu-id="dd6a1-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="dd6a1-194">Teams媒體處理器一直在下列情況下插入媒體路徑中：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="dd6a1-195">通話從 1：1 升級為群組通話</span><span class="sxs-lookup"><span data-stu-id="dd6a1-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="dd6a1-196">通話會撥打至Teams使用者</span><span class="sxs-lookup"><span data-stu-id="dd6a1-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="dd6a1-197">呼叫已轉接或轉接至商務用 Skype使用者</span><span class="sxs-lookup"><span data-stu-id="dd6a1-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="dd6a1-198">請確定您的 SBC 能夠存取媒體處理器和傳輸轉場範圍，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="dd6a1-199">SIP 訊號：FQDNs</span><span class="sxs-lookup"><span data-stu-id="dd6a1-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="dd6a1-200">針對 SIP 訊號，FQDN 和防火牆需求與非旁路案例相同。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="dd6a1-201">直接路由提供于下列Microsoft 365或Office 365環境中：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="dd6a1-202">Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="dd6a1-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="dd6a1-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="dd6a1-203">Office 365 GCC</span></span>
- <span data-ttu-id="dd6a1-204">Office 365 GCC高</span><span class="sxs-lookup"><span data-stu-id="dd6a1-204">Office 365 GCC High</span></span>
- <span data-ttu-id="dd6a1-205">Office 365DoD 深入瞭解[Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)美國政府環境，例如 GCC、GCC高和 DoD。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="dd6a1-206">Microsoft 365、Office 365及Office 365 GCC環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="dd6a1-207">直接路由的連接點為下列三個 FQDNs：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="dd6a1-208">**sip.pstnhub.microsoft.com** 全域 FQDN - 必須先嘗試。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="dd6a1-209">當 SBC 傳送解決此名稱的要求時，Microsoft Azure DNS 伺服器會返回指向指派給 SBC 的主要 Azure 資料中心的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="dd6a1-210">此工作分派是根據資料中心的績效度量，以及 SBC 的地理位置鄰近度。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="dd6a1-211">所退回的 IP 位址會對應到主要 FQDN。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="dd6a1-212">**sip2.pstnhub.microsoft.com** - 次要 FQDN - 地理上會繪製至第二個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="dd6a1-213">**sip3.pstnhub.microsoft.com** - 三級 FQDN - 地理上可繪製至第三個優先順序區域。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="dd6a1-214">您必須放置這三個 FQDN，才能：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="dd6a1-215">查詢第一個 FQDN (，提供較不載入且最接近 SBC 資料中心的最佳) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="dd6a1-216">當從 SBC 建立到遇到暫時問題的資料中心的連接時，提供容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="dd6a1-217">詳細資訊，請參閱下方的容錯移轉機制。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="dd6a1-218">FQDNs **sip.pstnhub.microsoft.com** **、sip2.pstnhub.microsoft.com** 和 sip3.pstnhub.microsoft.com 會解析為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="dd6a1-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="dd6a1-219">52.114.148.0</span></span>
- <span data-ttu-id="dd6a1-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="dd6a1-220">52.114.132.46</span></span> 
- <span data-ttu-id="dd6a1-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="dd6a1-221">52.114.75.24</span></span> 
- <span data-ttu-id="dd6a1-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="dd6a1-222">52.114.76.76</span></span> 
- <span data-ttu-id="dd6a1-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="dd6a1-223">52.114.7.24</span></span> 
- <span data-ttu-id="dd6a1-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="dd6a1-224">52.114.14.70</span></span>
- <span data-ttu-id="dd6a1-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="dd6a1-225">52.114.16.74</span></span>
- <span data-ttu-id="dd6a1-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="dd6a1-226">52.114.20.29</span></span>
- <span data-ttu-id="dd6a1-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="dd6a1-227">52.114.36.156</span></span> 
- <span data-ttu-id="dd6a1-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="dd6a1-228">52.114.32.169</span></span>

<span data-ttu-id="dd6a1-229">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="dd6a1-230">如果您的防火牆支援 DNS 名稱，FQDN **sip-all.pstnhub.microsoft.com** 解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="dd6a1-231">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="dd6a1-232">直接路由的連接點為下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="dd6a1-233">**sip.pstnhub.dod.teams.microsoft.us** – 全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="dd6a1-234">由於 Office 365 DoD 環境僅存在於美國資料中心，因此沒有次要和三級 FQDNs。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="dd6a1-235">FQDNs – sip.pstnhub.dod.teams.microsoft.us 會解析為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="dd6a1-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="dd6a1-236">52.127.64.33</span></span>
- <span data-ttu-id="dd6a1-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="dd6a1-237">52.127.68.34</span></span>

<span data-ttu-id="dd6a1-238">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="dd6a1-239">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.dod.teams.microsoft.us 解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="dd6a1-240">Office 365 GCC高環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="dd6a1-241">直接路由的連接點為下列 FQDN：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="dd6a1-242">**sip.pstnhub.gov.teams.microsoft.us** – 全域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="dd6a1-243">由於 GCC高環境僅存在於美國資料中心，因此沒有次要和三級 FQDNs。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="dd6a1-244">FQDNs – sip.pstnhub.gov.teams.microsoft.us 會解析為下列其中一個 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="dd6a1-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="dd6a1-245">52.127.88.59</span></span>
- <span data-ttu-id="dd6a1-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="dd6a1-246">52.127.92.64</span></span>

<span data-ttu-id="dd6a1-247">您必須在防火牆中開啟所有這些 IP 位址的埠，以允許接收和傳出流量到與來自接收信令的位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="dd6a1-248">如果您的防火牆支援 DNS 名稱，FQDN sip.pstnhub.gov.teams.microsoft.us 解析為所有這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="dd6a1-249">SIP 訊號：埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="dd6a1-250">提供直接路由的所有Office 365埠需求相同：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="dd6a1-251">Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="dd6a1-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="dd6a1-252">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="dd6a1-252">Office 365 GCC</span></span>
- <span data-ttu-id="dd6a1-253">Office 365 GCC高</span><span class="sxs-lookup"><span data-stu-id="dd6a1-253">Office 365 GCC High</span></span>
- <span data-ttu-id="dd6a1-254">Office 365國防部</span><span class="sxs-lookup"><span data-stu-id="dd6a1-254">Office 365 DoD</span></span>

<span data-ttu-id="dd6a1-255">您必須使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-255">You must use the following ports:</span></span>

| <span data-ttu-id="dd6a1-256">交通</span><span class="sxs-lookup"><span data-stu-id="dd6a1-256">Traffic</span></span> | <span data-ttu-id="dd6a1-257">從</span><span class="sxs-lookup"><span data-stu-id="dd6a1-257">From</span></span> | <span data-ttu-id="dd6a1-258">自</span><span class="sxs-lookup"><span data-stu-id="dd6a1-258">To</span></span> | <span data-ttu-id="dd6a1-259">來源埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-259">Source port</span></span> | <span data-ttu-id="dd6a1-260">目的地埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="dd6a1-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="dd6a1-261">SIP/TLS</span></span>| <span data-ttu-id="dd6a1-262">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="dd6a1-262">SIP Proxy</span></span> | <span data-ttu-id="dd6a1-263">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-263">SBC</span></span> | <span data-ttu-id="dd6a1-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="dd6a1-264">1024 - 65535</span></span> | <span data-ttu-id="dd6a1-265">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-265">Defined on the SBC</span></span> |
| <span data-ttu-id="dd6a1-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="dd6a1-266">SIP/TLS</span></span> | <span data-ttu-id="dd6a1-267">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-267">SBC</span></span> | <span data-ttu-id="dd6a1-268">SIP Proxy</span><span class="sxs-lookup"><span data-stu-id="dd6a1-268">SIP Proxy</span></span> | <span data-ttu-id="dd6a1-269">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-269">Defined on the SBC</span></span> | <span data-ttu-id="dd6a1-270">5061</span><span class="sxs-lookup"><span data-stu-id="dd6a1-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="dd6a1-271">媒體流量：IP 和埠範圍</span><span class="sxs-lookup"><span data-stu-id="dd6a1-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="dd6a1-272">媒體流量在 SBC 和 Teams用戶端之間流動，如果用戶端無法使用公用 IP 位址Teams則透過 Teams 傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="dd6a1-273">在用戶端與 SBC (之間Teams媒體流量的需求) </span><span class="sxs-lookup"><span data-stu-id="dd6a1-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="dd6a1-274">用戶端必須能存取指定的埠 (請參閱) SBC 公用 IP 位址上的資料表。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="dd6a1-275">如果用戶端位於內部網路中，媒體會流向 SBC 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="dd6a1-276">您可以在 NAT 裝置上設定發釘，讓流量永遠不會離開商業網路設備。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="dd6a1-277">交通</span><span class="sxs-lookup"><span data-stu-id="dd6a1-277">Traffic</span></span> | <span data-ttu-id="dd6a1-278">從</span><span class="sxs-lookup"><span data-stu-id="dd6a1-278">From</span></span> | <span data-ttu-id="dd6a1-279">自</span><span class="sxs-lookup"><span data-stu-id="dd6a1-279">To</span></span> | <span data-ttu-id="dd6a1-280">來源埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-280">Source port</span></span> | <span data-ttu-id="dd6a1-281">目的地埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="dd6a1-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-282">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-283">用戶端</span><span class="sxs-lookup"><span data-stu-id="dd6a1-283">Client</span></span> | <span data-ttu-id="dd6a1-284">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-284">SBC</span></span> | <span data-ttu-id="dd6a1-285">3478-3481 和 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="dd6a1-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="dd6a1-286">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-286">Defined on the SBC</span></span> |
| <span data-ttu-id="dd6a1-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-287">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-288">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-288">SBC</span></span> | <span data-ttu-id="dd6a1-289">用戶端</span><span class="sxs-lookup"><span data-stu-id="dd6a1-289">Client</span></span> | <span data-ttu-id="dd6a1-290">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-290">Defined on the SBC</span></span> | <span data-ttu-id="dd6a1-291">3478-3481 和 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="dd6a1-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="dd6a1-292">如果您有可翻譯用戶端來源埠的網路設備，請確定已翻譯的埠在網路設備與 SBC 之間開啟。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="dd6a1-293">使用傳輸轉場的需求</span><span class="sxs-lookup"><span data-stu-id="dd6a1-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="dd6a1-294">傳輸轉場與媒體處理器的範圍相同， (非旁路情況下) ：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="dd6a1-295">Microsoft 365、Office 365及Office 365 GCC環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="dd6a1-296">52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="dd6a1-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="dd6a1-297">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="dd6a1-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="dd6a1-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="dd6a1-299">Office 365 GCC高環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="dd6a1-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="dd6a1-300">52.127.88.0/21</span></span>


<span data-ttu-id="dd6a1-301">適用于所有Teams傳輸轉 (的埠) 如下表所示：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="dd6a1-302">交通</span><span class="sxs-lookup"><span data-stu-id="dd6a1-302">Traffic</span></span> | <span data-ttu-id="dd6a1-303">從</span><span class="sxs-lookup"><span data-stu-id="dd6a1-303">From</span></span> | <span data-ttu-id="dd6a1-304">自</span><span class="sxs-lookup"><span data-stu-id="dd6a1-304">To</span></span> | <span data-ttu-id="dd6a1-305">來源埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-305">Source port</span></span> | <span data-ttu-id="dd6a1-306">目的地埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="dd6a1-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-307">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-308">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="dd6a1-308">Transport Relay</span></span> | <span data-ttu-id="dd6a1-309">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-309">SBC</span></span> | <span data-ttu-id="dd6a1-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="dd6a1-310">50 000 -59 999</span></span>    | <span data-ttu-id="dd6a1-311">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-311">Defined on the SBC</span></span> |
| <span data-ttu-id="dd6a1-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-312">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-313">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-313">SBC</span></span> | <span data-ttu-id="dd6a1-314">傳輸轉場</span><span class="sxs-lookup"><span data-stu-id="dd6a1-314">Transport Relay</span></span> | <span data-ttu-id="dd6a1-315">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-315">Defined on the SBC</span></span> | <span data-ttu-id="dd6a1-316">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="dd6a1-316">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="dd6a1-317">Microsoft 建議在 SBC 上，每個同時通話至少兩個埠。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="dd6a1-318">由於 Microsoft 有兩個版本的傳輸轉傳遞，因此必須執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="dd6a1-319">v4，只能使用埠範圍 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="dd6a1-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="dd6a1-320">v6，適用于埠 3478、3479</span><span class="sxs-lookup"><span data-stu-id="dd6a1-320">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="dd6a1-321">目前，媒體旁路僅支援 v4 版的傳輸轉場。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="dd6a1-322">我們會在未來推出 v6 的支援。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="dd6a1-323">您需要開啟埠 3478 和 3479 進行轉場。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-323">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="dd6a1-324">當 Microsoft 推出 V6 傳輸轉場與媒體旁路的支援時，您將不需要重新配置您的網路設備或 SBC。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="dd6a1-325">使用媒體處理器的需求</span><span class="sxs-lookup"><span data-stu-id="dd6a1-325">Requirements for using media processors</span></span>

<span data-ttu-id="dd6a1-326">媒體處理器一直位於語音應用程式和 Web 用戶端的媒體路徑 (例如 Edge 或 Google Chrome Teams用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="dd6a1-327">需求與非旁路組組相同。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="dd6a1-328">媒體流量的 IP 範圍為</span><span class="sxs-lookup"><span data-stu-id="dd6a1-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="dd6a1-329">Office 365和Office 365 GCC環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="dd6a1-330">52.112.0.0 /14 (IP 位址從 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="dd6a1-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="dd6a1-331">Office 365 GCC DoD 環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="dd6a1-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="dd6a1-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="dd6a1-333">Office 365 GCC高環境</span><span class="sxs-lookup"><span data-stu-id="dd6a1-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="dd6a1-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="dd6a1-334">52.127.88.0/21</span></span>

<span data-ttu-id="dd6a1-335">適用于所有環境 (的媒體處理器) 範圍如下表所示：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="dd6a1-336">交通</span><span class="sxs-lookup"><span data-stu-id="dd6a1-336">Traffic</span></span> | <span data-ttu-id="dd6a1-337">從</span><span class="sxs-lookup"><span data-stu-id="dd6a1-337">From</span></span> | <span data-ttu-id="dd6a1-338">自</span><span class="sxs-lookup"><span data-stu-id="dd6a1-338">To</span></span> | <span data-ttu-id="dd6a1-339">來源埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-339">Source port</span></span> | <span data-ttu-id="dd6a1-340">目的地埠</span><span class="sxs-lookup"><span data-stu-id="dd6a1-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="dd6a1-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-341">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-342">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="dd6a1-342">Media Processor</span></span> | <span data-ttu-id="dd6a1-343">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-343">SBC</span></span> | <span data-ttu-id="dd6a1-344">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="dd6a1-344">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="dd6a1-345">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-345">Defined on the SBC</span></span> |
| <span data-ttu-id="dd6a1-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="dd6a1-346">UDP/SRTP</span></span> | <span data-ttu-id="dd6a1-347">Sbc</span><span class="sxs-lookup"><span data-stu-id="dd6a1-347">SBC</span></span> | <span data-ttu-id="dd6a1-348">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="dd6a1-348">Media Processor</span></span> | <span data-ttu-id="dd6a1-349">在 SBC 上定義</span><span class="sxs-lookup"><span data-stu-id="dd6a1-349">Defined on the SBC</span></span> | <span data-ttu-id="dd6a1-350">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="dd6a1-350">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="dd6a1-351">設定媒體旁路和非媒體旁路的個別主幹</span><span class="sxs-lookup"><span data-stu-id="dd6a1-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="dd6a1-352">如果您要從非媒體旁路移至媒體旁路，並想要先確認功能，然後再將所有使用方式移遷移到媒體旁路，您可以建立個別的主幹和個別的線上語音路由策略，以路由至媒體旁路主幹並指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="dd6a1-353">高層次組組步驟：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-353">High-level configuration steps:</span></span>

- <span data-ttu-id="dd6a1-354">識別要測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="dd6a1-355">使用不同的 FQDNs 建立兩個不同的主幹：一個已啟用媒體旁路;另一個則啟用媒體旁路;另一個不會。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="dd6a1-356">這兩個主幹都指向相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="dd6a1-357">TLS SIP 訊號的埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="dd6a1-358">媒體埠必須相同。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="dd6a1-359">建立新的線上語音路由策略，並將媒體旁路主幹指派給與此政策 PSTN 使用量相關聯的對應路由。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="dd6a1-360">將新的線上語音路由策略指派給已識別以測試媒體旁路的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="dd6a1-361">下列範例說明此邏輯。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="dd6a1-362">一組使用者</span><span class="sxs-lookup"><span data-stu-id="dd6a1-362">Set of users</span></span> | <span data-ttu-id="dd6a1-363">使用者數目</span><span class="sxs-lookup"><span data-stu-id="dd6a1-363">Number of users</span></span> | <span data-ttu-id="dd6a1-364">在 OVRP 中指派的主幹 FQDN</span><span class="sxs-lookup"><span data-stu-id="dd6a1-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="dd6a1-365">已啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="dd6a1-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="dd6a1-366">具有非媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="dd6a1-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="dd6a1-367">980</span><span class="sxs-lookup"><span data-stu-id="dd6a1-367">980</span></span> | <span data-ttu-id="dd6a1-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="dd6a1-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="dd6a1-369">假</span><span class="sxs-lookup"><span data-stu-id="dd6a1-369">false</span></span> |
<span data-ttu-id="dd6a1-370">具有媒體旁路主幹的使用者</span><span class="sxs-lookup"><span data-stu-id="dd6a1-370">Users with media bypass trunk</span></span> | <span data-ttu-id="dd6a1-371">20</span><span class="sxs-lookup"><span data-stu-id="dd6a1-371">20</span></span> | <span data-ttu-id="dd6a1-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="dd6a1-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="dd6a1-373">真</span><span class="sxs-lookup"><span data-stu-id="dd6a1-373">true</span></span> | 

<span data-ttu-id="dd6a1-374">這兩個主幹可以指向具有相同公用 IP 位址的同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="dd6a1-375">SBC 上的 TLS 訊號埠必須不同，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="dd6a1-376">請注意，您必須確定憑證支援這兩個主幹。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="dd6a1-377">在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 萬用字元憑證。  </span><span class="sxs-lookup"><span data-stu-id="dd6a1-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6a1-378">![顯示兩個主幹可以指向相同公用 IP 的同一個 SBC](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="dd6a1-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="dd6a1-379">若要瞭解如何在同一個 SBC 上設定兩個主幹，請參閱 SBC 廠商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="dd6a1-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="dd6a1-380">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="dd6a1-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="dd6a1-381">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="dd6a1-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="dd6a1-382">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="dd6a1-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="dd6a1-383">TE-Systems (任何) 部署檔</span><span class="sxs-lookup"><span data-stu-id="dd6a1-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="dd6a1-384">媒體旁路支援的用戶端端點</span><span class="sxs-lookup"><span data-stu-id="dd6a1-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="dd6a1-385">所有獨立電腦用戶端、Android 和 iOS 用戶端Teams裝置都支援媒體Teams 電話旁路。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="dd6a1-386">對於不支援媒體旁路的所有其他端點，我們會將通話轉換為非旁路，即使它以旁路通話開始。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="dd6a1-387">這會自動發生，而且不需要系統管理員執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="dd6a1-388">這包括商務用 Skype 3PIP 電話和 Teams Web 用戶端，這些用戶端支援在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上直接路由通話 (WebRTC 用戶端。</span><span class="sxs-lookup"><span data-stu-id="dd6a1-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="dd6a1-389">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dd6a1-389">See also</span></span>

[<span data-ttu-id="dd6a1-390">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="dd6a1-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
