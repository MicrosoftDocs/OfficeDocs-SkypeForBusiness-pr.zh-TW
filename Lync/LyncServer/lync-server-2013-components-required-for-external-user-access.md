---
title: Lync Server 2013：外部使用者存取所需的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a97635c66d66703fc2e9879024004a95c2c09eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502450"
---
# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f4209-102">Lync Server 2013 中的外部使用者存取所需的元件</span><span class="sxs-lookup"><span data-stu-id="f4209-102">Components required for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4209-103">_**主題上次修改日期：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="f4209-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="f4209-104">大部分的 Edge 元件都是部署在周邊網路中。</span><span class="sxs-lookup"><span data-stu-id="f4209-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="f4209-105">周邊網路的 Edge 拓撲由下列元件組成。</span><span class="sxs-lookup"><span data-stu-id="f4209-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="f4209-106">除了另有說明之外，這些元件是 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md) 的一部分，且位於周邊網路中。</span><span class="sxs-lookup"><span data-stu-id="f4209-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="f4209-107">Edge 元件包括：</span><span class="sxs-lookup"><span data-stu-id="f4209-107">Edge components include the following:</span></span>

  - <span data-ttu-id="f4209-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="f4209-108">Edge Servers</span></span>

  - <span data-ttu-id="f4209-109">反向 proxy</span><span class="sxs-lookup"><span data-stu-id="f4209-109">Reverse proxies</span></span>

  - <span data-ttu-id="f4209-110">防火牆</span><span class="sxs-lookup"><span data-stu-id="f4209-110">Firewalls</span></span>

  - <span data-ttu-id="f4209-111">Director (選用，並在內部網路上以邏輯方式放置) </span><span class="sxs-lookup"><span data-stu-id="f4209-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="f4209-112">調整式 Edge 拓撲的負載平衡 (DNS 負載平衡或硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="f4209-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4209-p102">不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="f4209-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="f4209-115">Edge Server</span><span class="sxs-lookup"><span data-stu-id="f4209-115">Edge Servers</span></span>

<span data-ttu-id="f4209-116">Edge Server 會傳送和接收外部使用者內部部署所提供之服務的網路流量。</span><span class="sxs-lookup"><span data-stu-id="f4209-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="f4209-117">Edge Server 可執行下列服務：</span><span class="sxs-lookup"><span data-stu-id="f4209-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="f4209-118">**Access Edge service**    Access Edge service 會為輸出和輸入會話初始通訊協定 (SIP) 流量，提供單一、受信任的連接點。</span><span class="sxs-lookup"><span data-stu-id="f4209-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="f4209-119">**Web 會議 Edge service**    Web 會議 Edge service 可讓外部使用者加入內部 Lync Server 2013 部署中所主控的會議。</span><span class="sxs-lookup"><span data-stu-id="f4209-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="f4209-120">**A/V Edge service**    A/V Edge service 可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸功能。</span><span class="sxs-lookup"><span data-stu-id="f4209-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="f4209-121">您的使用者可以在包含外部參與者的會議中新增音訊和影片，也可以使用音訊和/或影片直接透過點對點會話中的外部使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f4209-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="f4209-122">A/V Edge Service 也可支援桌面共用與檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="f4209-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="f4209-123">**XMPP Proxy 服務**    XMPP Proxy 服務會接受及傳送可延伸的訊息和顯示狀態通訊協定 (XMPP) 郵件傳送至及從設定的 XMPP 同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="f4209-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="f4209-124">已授權的外部使用者可以存取 Edge Server，以連線至您的內部 Lync Server 2013 部署，但 Edge server 並未提供任何其他存取內部網路的方法。</span><span class="sxs-lookup"><span data-stu-id="f4209-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4209-125">Edge server 的部署是為了提供連線至已啟用的 Lync 用戶端和其他 Microsoft Edge server (如同在同盟案例中) 。</span><span class="sxs-lookup"><span data-stu-id="f4209-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="f4209-126">這些伺服器的設計，目的並非在於提供從其他端點用戶端或從其他伺服器類型進行連線的能力。</span><span class="sxs-lookup"><span data-stu-id="f4209-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="f4209-127">部署 XMPP 閘道伺服器可提供與設定的 XMPP 合作夥伴的進行連線的能力。</span><span class="sxs-lookup"><span data-stu-id="f4209-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="f4209-128">Edge Server 和 XMPP 閘道僅可支援從這些用戶端和同盟類型進行端點連線的能力。</span><span class="sxs-lookup"><span data-stu-id="f4209-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="f4209-129">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="f4209-129">Reverse Proxy</span></span>

<span data-ttu-id="f4209-130">下列作業需要反向 Proxy：</span><span class="sxs-lookup"><span data-stu-id="f4209-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="f4209-131">讓使用者透過簡單 URL 連線至會議或電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="f4209-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="f4209-132">讓外部使用者下載會議內容</span><span class="sxs-lookup"><span data-stu-id="f4209-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="f4209-133">讓外部使用者能夠擴充通訊群組</span><span class="sxs-lookup"><span data-stu-id="f4209-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="f4209-134">讓使用者取得可用於用戶端憑證式驗證的使用者式憑證</span><span class="sxs-lookup"><span data-stu-id="f4209-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="f4209-135">讓遠端使用者從 Address Book Server 下載檔案，或送出查詢至通訊錄 Web 查詢服務</span><span class="sxs-lookup"><span data-stu-id="f4209-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="f4209-136">讓遠端使用者取得用戶端與裝置軟體的更新</span><span class="sxs-lookup"><span data-stu-id="f4209-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="f4209-137">讓行動裝置能夠自動探索前端伺服器提供行動服務</span><span class="sxs-lookup"><span data-stu-id="f4209-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="f4209-138">從 Microsoft 365、Office 365 或 Apple push notification 服務，啟用行動裝置的推播通知</span><span class="sxs-lookup"><span data-stu-id="f4209-138">To enable push notifications to mobile devices from the Microsoft 365, Office 365, or Apple push notification services</span></span>

<span data-ttu-id="f4209-139">如需與反向 proxy 相關的其他資訊，以及反向 proxy 必須符合的需求，請參閱 [Lync Server 2013 中的反向 proxy 設定需求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f4209-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4209-140">外部使用者不需要使用虛擬私人網路 (VPN) 連接至您的組織，即可參與使用 Lync Server 2013 的通訊。</span><span class="sxs-lookup"><span data-stu-id="f4209-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="f4209-141">如果您已在組織中實施 VPN 技術，且使用者使用的是 Lync 的 VPN，則媒體流量 (例如影片會議) 會受到不良影響。</span><span class="sxs-lookup"><span data-stu-id="f4209-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="f4209-142">您應考慮提供一種方法，讓媒體流量直接連線至 AV Edge service，並略過 VPN。</span><span class="sxs-lookup"><span data-stu-id="f4209-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="f4209-143">如需詳細資訊，請參閱 NextHop 的博客文章：「啟用 Lync Media 旁路 VPN 隧道」 <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> 。</span><span class="sxs-lookup"><span data-stu-id="f4209-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="f4209-144">防火牆</span><span class="sxs-lookup"><span data-stu-id="f4209-144">Firewall</span></span>

<span data-ttu-id="f4209-145">部署您的 Edge 拓撲時，您可以僅使用外部防火牆，也可以同時使用外部與內部防火牆。</span><span class="sxs-lookup"><span data-stu-id="f4209-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="f4209-146">案例架構包含兩個防火牆。</span><span class="sxs-lookup"><span data-stu-id="f4209-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="f4209-147">建議您使用兩個防火牆，因為這樣可確保從某個網路邊緣傳入另一個網路邊緣的流量嚴格遵守路由規則，且內部部署可受到兩層防火牆保護。</span><span class="sxs-lookup"><span data-stu-id="f4209-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="f4209-148">Director</span><span class="sxs-lookup"><span data-stu-id="f4209-148">Director</span></span>

<span data-ttu-id="f4209-149">Director 是 Lync Server 2013 中的個別非選用伺服器角色，不會家用使用者帳戶，也不會提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="f4209-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="f4209-150">它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4209-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="f4209-151">Director preauthenticates 輸入要求並將其重新導向至使用者的主集區或伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4209-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="f4209-152">透過 preauthenticating 在 Director 上，您可以丟棄部署無法識別之使用者帳戶的要求。</span><span class="sxs-lookup"><span data-stu-id="f4209-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="f4209-153">Director 可協助將 Enterprise Edition 前端集區中的 Standard Edition 伺服器和前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="f4209-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="f4209-154">如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="f4209-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="f4209-155">如需使用 Director 的詳細資訊，請參閱 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="f4209-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4209-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4209-156">See Also</span></span>


[<span data-ttu-id="f4209-157">Lync Server 2013 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="f4209-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

