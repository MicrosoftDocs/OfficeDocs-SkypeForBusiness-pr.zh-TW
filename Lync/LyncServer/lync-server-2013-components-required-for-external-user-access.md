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
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="26bce-102">外部使用者在 Lync Server 2013 中存取時所需的元件</span><span class="sxs-lookup"><span data-stu-id="26bce-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26bce-103">_**主題上次修改日期：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="26bce-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="26bce-104">大部分的邊緣元件都是在周邊網路中部署。</span><span class="sxs-lookup"><span data-stu-id="26bce-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="26bce-105">下列元件構成周邊網路的邊緣拓撲。</span><span class="sxs-lookup"><span data-stu-id="26bce-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="26bce-106">除非另有說明，否則元件屬於[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，且位於周邊網路中。</span><span class="sxs-lookup"><span data-stu-id="26bce-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="26bce-107">Edge 元件包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="26bce-107">Edge components include the following:</span></span>

  - <span data-ttu-id="26bce-108">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="26bce-108">Edge Servers</span></span>

  - <span data-ttu-id="26bce-109">反向代理</span><span class="sxs-lookup"><span data-stu-id="26bce-109">Reverse proxies</span></span>

  - <span data-ttu-id="26bce-110">道</span><span class="sxs-lookup"><span data-stu-id="26bce-110">Firewalls</span></span>

  - <span data-ttu-id="26bce-111">控制器（可省略，且在內部網路上的邏輯位置）</span><span class="sxs-lookup"><span data-stu-id="26bce-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="26bce-112">針對調整後的邊緣拓撲（DNS 負載平衡或硬體負載平衡器）進行負載平衡</span><span class="sxs-lookup"><span data-stu-id="26bce-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="26bce-113">在一個介面上使用 DNS 負載平衡，而另一個介面上的硬體負載平衡則不受支援。</span><span class="sxs-lookup"><span data-stu-id="26bce-113">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="26bce-114">您必須針對兩種介面或 DNS 負載平衡使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="26bce-114">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="26bce-115">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="26bce-115">Edge Servers</span></span>

<span data-ttu-id="26bce-116">Edge 伺服器會傳送和接收外部使用者由內部部署所提供之服務的網路流量。</span><span class="sxs-lookup"><span data-stu-id="26bce-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="26bce-117">Edge 伺服器會執行下列服務：</span><span class="sxs-lookup"><span data-stu-id="26bce-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="26bce-118">**存取邊緣服務**   存取邊緣服務為輸出與輸入會話初始通訊協定（SIP）流量提供單一、受信任的連接點。</span><span class="sxs-lookup"><span data-stu-id="26bce-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="26bce-119">**網路會議 edge 服務**   ：網路會議 edge 服務可讓外部使用者加入託管在您內部 Lync Server 2013 部署上的會議。</span><span class="sxs-lookup"><span data-stu-id="26bce-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="26bce-120">**A/v 邊緣服務**   a/v 邊緣服務可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="26bce-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="26bce-121">您的使用者可以在包含外部參與者的會議中新增音訊和影片，而且他們可以使用音訊和/或影片，在點對點會話中直接使用外部使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="26bce-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="26bce-122">A/V 邊緣服務也提供對桌面共用和檔案傳輸的支援。</span><span class="sxs-lookup"><span data-stu-id="26bce-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="26bce-123">**XMPP proxy 服務**   XMPP Proxy 服務會從已設定的 XMPP 聯盟夥伴中接收並傳送可擴展的訊息和目前狀態通訊協定（XMPP）訊息。</span><span class="sxs-lookup"><span data-stu-id="26bce-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="26bce-124">已授權的外部使用者可以存取邊緣伺服器以連線到您的內部 Lync Server 2013 部署，但 Edge 伺服器不提供任何其他存取內部網路的方法。</span><span class="sxs-lookup"><span data-stu-id="26bce-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26bce-125">已部署邊緣伺服器來提供已啟用的 Lync 用戶端和其他 Microsoft Edge 伺服器（例如在同盟案例中）的連線。</span><span class="sxs-lookup"><span data-stu-id="26bce-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="26bce-126">它們不是用來允許來自其他端點用戶端或伺服器類型的連線。</span><span class="sxs-lookup"><span data-stu-id="26bce-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="26bce-127">XMPP 閘道伺服器可以部署，以允許與已設定 XMPP 夥伴的連線。</span><span class="sxs-lookup"><span data-stu-id="26bce-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="26bce-128">Edge 伺服器和 XMPP 閘道只能支援來自這些用戶端與同盟類型的端點連線。</span><span class="sxs-lookup"><span data-stu-id="26bce-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="26bce-129">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="26bce-129">Reverse Proxy</span></span>

<span data-ttu-id="26bce-130">下列情況需要反向 proxy：</span><span class="sxs-lookup"><span data-stu-id="26bce-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="26bce-131">若要允許使用者使用簡單的 Url 連線至會議或電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="26bce-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="26bce-132">若要讓外部使用者下載會議內容</span><span class="sxs-lookup"><span data-stu-id="26bce-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="26bce-133">若要讓外部使用者展開通訊群組</span><span class="sxs-lookup"><span data-stu-id="26bce-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="26bce-134">允許使用者取得以用戶端憑證為基礎的驗證的使用者憑證</span><span class="sxs-lookup"><span data-stu-id="26bce-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="26bce-135">若要讓遠端使用者從通訊錄服務器下載檔案，或是將查詢提交至通訊錄網頁查詢服務</span><span class="sxs-lookup"><span data-stu-id="26bce-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="26bce-136">讓遠端使用者取得用戶端和裝置軟體的更新</span><span class="sxs-lookup"><span data-stu-id="26bce-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="26bce-137">讓行動裝置自動探索前端伺服器提供行動服務</span><span class="sxs-lookup"><span data-stu-id="26bce-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="26bce-138">從 Office 365 或 Apple 推播通知服務啟用 [推播通知] 至行動裝置</span><span class="sxs-lookup"><span data-stu-id="26bce-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="26bce-139">如需有關反向代理與反向代理伺服器必須符合的其他資訊，請參閱[Lync Server 2013 中的反向 proxy 設定需求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="26bce-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26bce-140">外部使用者不需要虛擬私人網路（VPN）連線至您的組織，就能使用 Lync Server 2013 參與通訊。</span><span class="sxs-lookup"><span data-stu-id="26bce-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="26bce-141">如果您已在組織中實現 VPN 技術，且您的使用者使用的是 Lync 的 VPN，媒體流量（例如視訊會議）可能會受到負面影響。</span><span class="sxs-lookup"><span data-stu-id="26bce-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="26bce-142">您應該考慮提供媒體流量以直接連線到 AV 邊緣服務的方式，並繞過 VPN。</span><span class="sxs-lookup"><span data-stu-id="26bce-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="26bce-143">如需詳細資訊，請參閱 NextHop 博客文章：「啟用 Lync 媒體旁路 VPN 隧道」 <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>。</span><span class="sxs-lookup"><span data-stu-id="26bce-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="26bce-144">防火牆</span><span class="sxs-lookup"><span data-stu-id="26bce-144">Firewall</span></span>

<span data-ttu-id="26bce-145">您可以只使用外部防火牆或外部與內部防火牆來部署 edge 拓撲。</span><span class="sxs-lookup"><span data-stu-id="26bce-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="26bce-146">案例架構包含兩個防火牆。</span><span class="sxs-lookup"><span data-stu-id="26bce-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="26bce-147">使用兩個防火牆是一種建議的方法，因為它可確保嚴格地從一個網路邊緣路由到另一個網路邊緣，而且它會保護您的內部部署是在兩個層次的防火牆後。</span><span class="sxs-lookup"><span data-stu-id="26bce-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="26bce-148">Director</span><span class="sxs-lookup"><span data-stu-id="26bce-148">Director</span></span>

<span data-ttu-id="26bce-149">Director 是 Lync Server 2013 中的個別、選擇性的伺服器角色，不會家用使用者帳戶，或提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="26bce-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="26bce-150">它是一種內部的下一個躍點伺服器，可讓邊緣伺服器路由發往內部伺服器的入站 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="26bce-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="26bce-151">Director preauthenticates 輸入要求，並將它們重新導向至使用者的主區或伺服器。</span><span class="sxs-lookup"><span data-stu-id="26bce-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="26bce-152">在導演 preauthenticating，您可以丟棄部署無法識別的使用者帳戶要求。</span><span class="sxs-lookup"><span data-stu-id="26bce-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="26bce-153">控制器可協助將企業版前端池中的標準版伺服器與前端伺服器與惡意流量（例如拒絕服務（DoS）攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="26bce-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="26bce-154">如果網路充斥在攻擊中的無效外部通信量，通信量就會結束在 Director 上。</span><span class="sxs-lookup"><span data-stu-id="26bce-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="26bce-155">如需有關使用控制器的詳細資料，請參閱[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="26bce-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26bce-156">請參閱</span><span class="sxs-lookup"><span data-stu-id="26bce-156">See Also</span></span>


[<span data-ttu-id="26bce-157">Lync Server 2013 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="26bce-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

