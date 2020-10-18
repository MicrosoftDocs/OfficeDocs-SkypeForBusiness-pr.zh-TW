---
title: Lync Server 2013 中型組織的參考拓撲
description: 適用于中等規模組織的 Lync Server 2013 參考拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9e6ef467506865193dc26887e802198b16f42f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578609"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a><span data-ttu-id="6b7be-103">大中型組織中 Lync Server 2013 的參考拓撲</span><span class="sxs-lookup"><span data-stu-id="6b7be-103">Reference topology for Lync Server 2013 in medium-size organizations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b7be-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="6b7be-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="6b7be-105">具有高可用性和單一資料中心的參考拓撲是專為具有一個中央網站的中小型組織所設計。</span><span class="sxs-lookup"><span data-stu-id="6b7be-105">The reference topology with high availability and a single data center is designed for a small-to-medium size organization with one central site.</span></span> <span data-ttu-id="6b7be-106">下圖中的實際拓撲是針對20000使用者的組織。</span><span class="sxs-lookup"><span data-stu-id="6b7be-106">The exact topology in the following diagram is for an organization of 20,000 users.</span></span>

<span data-ttu-id="6b7be-107">**中型組織的參考拓撲**</span><span class="sxs-lookup"><span data-stu-id="6b7be-107">**Reference topology for medium organizations**</span></span>

<span data-ttu-id="6b7be-108">![單一資料中心圖表的參考拓撲](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "單一資料中心圖表的參考拓撲")</span><span class="sxs-lookup"><span data-stu-id="6b7be-108">![Reference topology for single data center diagram](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Reference topology for single data center diagram")</span></span>

  - <span data-ttu-id="6b7be-109">**新增多部前端伺服器以容納更多使用者。**    此圖中的實際拓撲有三部前端伺服器，可為20000使用者提供支援。</span><span class="sxs-lookup"><span data-stu-id="6b7be-109">**Accommodate more users by adding more Front End Servers.**   The exact topology in this diagram has three Front End Servers to provide support for 20,000 users.</span></span> <span data-ttu-id="6b7be-110">如果您有單一的中央網站和更多使用者，您只需要將多部前端伺服器新增至集區即可。</span><span class="sxs-lookup"><span data-stu-id="6b7be-110">If you have a single central site and more users, you can simply add more Front End Servers to the pool.</span></span> <span data-ttu-id="6b7be-111">每個集區的使用者數目上限為80000，含十二部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-111">The maximum number of users per pool is 80,000, with twelve Front End Servers.</span></span>
    
    <span data-ttu-id="6b7be-112">不過，如果在網站再新增一個前端集區，則單一個網站拓撲可以支援更多使用者。</span><span class="sxs-lookup"><span data-stu-id="6b7be-112">However, the single site topology can support even more users by adding another Front End pool to the site.</span></span>

  - <span data-ttu-id="6b7be-113">可以**新增災難修復。**    針對此組織，其 Lync Server 服務的高可用性是必要的功能，但不會發生嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="6b7be-113">**Disaster Recovery could be added.**   For this organization, high availability for their Lync Server services is a necessary feature, but disaster recovery is not.</span></span> <span data-ttu-id="6b7be-114">其部署的前端伺服器集區提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="6b7be-114">The pool of Front End Servers they have deployed provides high availability.</span></span>
    
    <span data-ttu-id="6b7be-115">如果他們想要新增嚴重損壞復原能力，他們可能會考慮建立另一個資料中心，並在其中新增另一個前端集區，並將它與目前資料中心的前端集區配對。</span><span class="sxs-lookup"><span data-stu-id="6b7be-115">If they wanted to add disaster recovery ability, they could consider establishing another datacenter and adding another Front End pool there, and pairing it with the Front End pool in their current datacenter.</span></span> <span data-ttu-id="6b7be-116">然後，如果發生嚴重影響其主要集區的嚴重損壞，系統管理員可以將使用者容錯移轉至備份組區。</span><span class="sxs-lookup"><span data-stu-id="6b7be-116">Then, if there was a disaster affecting their primary pool, the administrators could fail over users to the backup pool.</span></span>

  - <span data-ttu-id="6b7be-117">**後端伺服器已鏡像**    若要提供更高的基本使用者功能可用性，該組織已為每一個前端集區部署一組鏡像的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-117">**Back End Servers are mirrored**   To provide more high availability for basic user features, the organization has deployed a mirrored pair of Back End Servers for each Front End pool.</span></span> <span data-ttu-id="6b7be-118">這是 Lync Server 2013 的新拓撲選項，且是選用的。</span><span class="sxs-lookup"><span data-stu-id="6b7be-118">This is a new topology option for Lync Server 2013, and is optional.</span></span> <span data-ttu-id="6b7be-119">您可以選擇改為部署單一後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-119">You could choose to deploy a single Back End Server instead.</span></span>

  - <span data-ttu-id="6b7be-120">**監控伺服器資料庫選項。**    此組織已部署監控，以確保 Enterprise Voice 通話的品質和 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="6b7be-120">**Monitoring Server database options.**   This organization has deployed Monitoring to ensure the quality of Enterprise Voice calls and A/V conferences.</span></span> <span data-ttu-id="6b7be-121">監控是部署于每一部前端伺服器上，而監視資料庫則是與後端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="6b7be-121">Monitoring is deployed on every Front End Server, and the Monitoring database is collocated with the Back End Servers.</span></span> <span data-ttu-id="6b7be-122">我們也支援監控資料庫位於不同伺服器上的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6b7be-122">We also support topologies in which the Monitoring database is located on a separate server.</span></span>

  - <span data-ttu-id="6b7be-123">**Edge Server 高可用性**    在此範例中，有20000位使用者的組織，只有一部 Edge Server 足以獲得效能。</span><span class="sxs-lookup"><span data-stu-id="6b7be-123">**Edge Server high availability**    In this example organization with 20,000 users, just one Edge Server would be sufficient for performance.</span></span> <span data-ttu-id="6b7be-124">不過，已部署兩部 Edge Server 的集區以提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="6b7be-124">However, there is a pool of two Edge Servers deployed to provide high availability.</span></span>

  - <span data-ttu-id="6b7be-125">**分支網站部署選項。**    此拓撲中的組織已部署企業語音，成為其語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="6b7be-125">**Branch site deployment options.**   The organization in this topology has Enterprise Voice deployed as their voice solution.</span></span> <span data-ttu-id="6b7be-126">分支網站1沒有 Survivable WAN) 連結到中央網站的彈性廣域 (網路，因此它已部署分支裝置，以維護許多 Lync Server 功能，以防中央網站的 WAN 連結停止運作。</span><span class="sxs-lookup"><span data-stu-id="6b7be-126">Branch Site 1 does not have a resilient wide area network (WAN) link to the central site, so it has a Survivable Branch Appliance deployed to maintain many Lync Server features in case the WAN link to the central site goes down.</span></span> <span data-ttu-id="6b7be-127">不過，分支網站 2 具有可恢復的 WAN 連結，因此只需要有公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="6b7be-127">Branch Site 2 however has a resilient WAN link, so only a public switched telephone network (PSTN) gateway is needed.</span></span> <span data-ttu-id="6b7be-128">此網站部署的 PSTN 閘道支援媒體旁路，所以分支網站 2 不需要有中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-128">The PSTN gateway deployed there supports media bypass, so no Mediation Server is needed at Branch Site 2.</span></span> <span data-ttu-id="6b7be-129">如需決定在分支網站上部署專案的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的 branch site voice 韌性](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。</span><span class="sxs-lookup"><span data-stu-id="6b7be-129">For details about deciding what to deploy at a branch site, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6b7be-130">**DNS 負載平衡。**    前端集區 andEdge 伺服器集區，具有部署 SIP 流量的 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="6b7be-130">**DNS load balancing.**   The Front End pool andEdge Server pool, have DNS load balancing for SIP traffic deployed.</span></span> <span data-ttu-id="6b7be-131">如此一來，Edge Server 就不需要硬體負載平衡器，這樣可大幅減少為其他集區安裝和維護硬體負載平衡器的工作，因為只有 HTTP 流量才需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-131">This eliminates the need for hardware load balancers for the Edge Servers, and significantly lessens the setup and maintenance of the hardware load balancers for the other pools, as the hardware load balancers are needed only for HTTP traffic.</span></span> <span data-ttu-id="6b7be-132">如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="6b7be-132">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6b7be-133">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="6b7be-133">**Exchange UM deployment.**</span></span> <span data-ttu-id="6b7be-134">此參考拓撲包含 Exchange 整合通訊 (UM) Server，它會執行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6b7be-134">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="6b7be-135">如需 Exchange UM 的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃 Exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [主控 Exchange 整合通訊2013整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。</span><span class="sxs-lookup"><span data-stu-id="6b7be-135">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6b7be-136">**Office Web Apps Server。**</span><span class="sxs-lookup"><span data-stu-id="6b7be-136">**Office Web Apps Server.**</span></span> <span data-ttu-id="6b7be-137">建議您在使用 Web 會議的每家組織中部署 Office Web Apps Server 或 Office Web Apps Server 伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="6b7be-137">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="6b7be-138">Office Web Apps Server 可以在 Web 會議中呈現 Powerpoint 投影片。</span><span class="sxs-lookup"><span data-stu-id="6b7be-138">Office Web Apps Server makes it possible for Powerpoint slides to be presented in web conferences.</span></span> <span data-ttu-id="6b7be-139">如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="6b7be-139">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="6b7be-140">**建議使用 Edge server。**    雖然不需要部署 Edge Server，但建議使用任何規模的部署。</span><span class="sxs-lookup"><span data-stu-id="6b7be-140">**Edge Servers are recommended.**   Although deploying an Edge Server is not required, we recommend it for any size of deployment.</span></span> <span data-ttu-id="6b7be-141">您可以部署 Edge Server，將服務提供給目前組織防火牆以外的使用者，以達到最大的 Lync 伺服器投資。</span><span class="sxs-lookup"><span data-stu-id="6b7be-141">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="6b7be-142">優點包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6b7be-142">The benefits include the following:</span></span>
    
      - <span data-ttu-id="6b7be-143">您組織的使用者可以使用 Lync Server 功能（如果他們在家中運作或是在旅途中外出）。</span><span class="sxs-lookup"><span data-stu-id="6b7be-143">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="6b7be-144">您的使用者可以邀請外部使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="6b7be-144">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="6b7be-145">如果您有也使用 Lync Server 的合作夥伴、廠商或客戶組織，您可以建立與該組織的同盟 *關聯* 。</span><span class="sxs-lookup"><span data-stu-id="6b7be-145">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="6b7be-146">然後，您的 Lync 伺服器部署會辨識來自該同盟組織的使用者，以改善合作。</span><span class="sxs-lookup"><span data-stu-id="6b7be-146">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="6b7be-147">您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任何或所有專案： Windows Live、AOL、Yahoo \! 和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="6b7be-147">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="6b7be-148">使用這些服務的公用 IM 連線可能需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="6b7be-148">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="6b7be-149">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="6b7be-149">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6b7be-150">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="6b7be-150">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6b7be-151">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="6b7be-151">Messenger until the service shut down date.</span></span> <span data-ttu-id="6b7be-152">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="6b7be-152">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6b7be-153">已宣告。</span><span class="sxs-lookup"><span data-stu-id="6b7be-153">has been announced.</span></span> <span data-ttu-id="6b7be-154">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="6b7be-154">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="6b7be-155">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="6b7be-155">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6b7be-156">信使。</span><span class="sxs-lookup"><span data-stu-id="6b7be-156">Messenger.</span></span> <span data-ttu-id="6b7be-157">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="6b7be-157">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="6b7be-158">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="6b7be-158">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6b7be-159">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="6b7be-159">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6b7be-160">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="6b7be-160">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="6b7be-161">**可以新增 director。**    如果此組織想要協助提高安全性以防範拒絕服務攻擊，也可以部署 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="6b7be-161">**Directors could be added.**   If this organization wanted to help to increase security against denial of service attacks, it could also deploy a pool of Directors.</span></span> <span data-ttu-id="6b7be-162">Director 是 Lync Server 中的個別非選用伺服器角色，不會家用使用者帳戶，也不會提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="6b7be-162">A Director is a separate, optional server role in Lync Server that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="6b7be-163">它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-163">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="6b7be-164">Director 對輸入要求進行預先驗證，並將它們重新導向至使用者的主集區或伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b7be-164">The Director pre-authenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="6b7be-165">Director 的預先驗證可讓您從部署中未知的使用者帳戶中丟棄要求。</span><span class="sxs-lookup"><span data-stu-id="6b7be-165">Pre-authentication at the Director allows for dropping of requests from user accounts unknown to the deployment.</span></span> <span data-ttu-id="6b7be-166">Director 可協助將前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="6b7be-166">A Director helps insulate Front End Servers from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="6b7be-167">如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。</span><span class="sxs-lookup"><span data-stu-id="6b7be-167">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span>

  - <span data-ttu-id="6b7be-168">**建議使用 System Center Operations Manager。**   建議您監視 Lync Server 部署的健康情況，以協助確保使用者的服務可用性。</span><span class="sxs-lookup"><span data-stu-id="6b7be-168">**System Center Operations Manager is recommended.**  We recommend that you monitor the health of your Lync Server deployment to help ensure service availability for end-users.</span></span> <span data-ttu-id="6b7be-169">您可以使用 Lync 的 System Center Operations Manager 管理元件（可免費從 Microsoft 下載）來監視 Lync。</span><span class="sxs-lookup"><span data-stu-id="6b7be-169">You can monitor Lync with the System Center Operations Manager Management Pack for Lync that is available as a free download from Microsoft.</span></span> <span data-ttu-id="6b7be-170">透過 Lync 管理元件，您可以在發生問題時主動取得即時警示、執行綜合交易，以測試端對端的 Lync 功能、取得服務可用性的報告等等。</span><span class="sxs-lookup"><span data-stu-id="6b7be-170">With the Lync Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Lync functionality, get reports for service availability, and so on.</span></span> <span data-ttu-id="6b7be-171">這可協助您在使用者體驗之前，主動回應部署的問題。</span><span class="sxs-lookup"><span data-stu-id="6b7be-171"> This helps you to proactively respond to issues with your deployment before end-users experience them.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

