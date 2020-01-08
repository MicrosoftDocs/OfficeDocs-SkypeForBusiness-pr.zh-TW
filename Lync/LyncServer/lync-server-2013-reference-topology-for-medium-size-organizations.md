---
title: Lync Server 2013 適用於中型組織的參考拓樸
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a><span data-ttu-id="67346-102">中型組織內 Lync Server 2013 的參考拓樸</span><span class="sxs-lookup"><span data-stu-id="67346-102">Reference topology for Lync Server 2013 in medium-size organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67346-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="67346-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="67346-104">具有高可用性與單一資料中心的參照拓撲是專為具有單一中心網站的中小型組織設計。</span><span class="sxs-lookup"><span data-stu-id="67346-104">The reference topology with high availability and a single data center is designed for a small-to-medium size organization with one central site.</span></span> <span data-ttu-id="67346-105">下圖中的確切拓撲是針對20000使用者的組織。</span><span class="sxs-lookup"><span data-stu-id="67346-105">The exact topology in the following diagram is for an organization of 20,000 users.</span></span>

<span data-ttu-id="67346-106">**中型組織的參考拓撲**</span><span class="sxs-lookup"><span data-stu-id="67346-106">**Reference topology for medium organizations**</span></span>

<span data-ttu-id="67346-107">單一資料![中心圖表的參照拓撲](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "單一資料中心圖表的參照拓撲")</span><span class="sxs-lookup"><span data-stu-id="67346-107">![Reference topology for single data center diagram](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Reference topology for single data center diagram")</span></span>

  - <span data-ttu-id="67346-108">**新增更多前端伺服器以容納更多使用者。**   此圖中的確切拓撲包含三個前端伺服器來提供20000使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="67346-108">**Accommodate more users by adding more Front End Servers.**   The exact topology in this diagram has three Front End Servers to provide support for 20,000 users.</span></span> <span data-ttu-id="67346-109">如果您有單一的中央網站及更多使用者，您可以直接在池中新增更多前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-109">If you have a single central site and more users, you can simply add more Front End Servers to the pool.</span></span> <span data-ttu-id="67346-110">每個池的使用者數目上限為80000，且有十二個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-110">The maximum number of users per pool is 80,000, with twelve Front End Servers.</span></span>
    
    <span data-ttu-id="67346-111">不過，單一網站拓朴可將另一個 [前端] 池新增至網站，以支援更多使用者。</span><span class="sxs-lookup"><span data-stu-id="67346-111">However, the single site topology can support even more users by adding another Front End pool to the site.</span></span>

  - <span data-ttu-id="67346-112">**您可以新增災害復原。**   針對此組織，其 Lync Server 服務的高可用性是必要的功能，但不需要災害復原。</span><span class="sxs-lookup"><span data-stu-id="67346-112">**Disaster Recovery could be added.**   For this organization, high availability for their Lync Server services is a necessary feature, but disaster recovery is not.</span></span> <span data-ttu-id="67346-113">其部署的前端伺服器池可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="67346-113">The pool of Front End Servers they have deployed provides high availability.</span></span>
    
    <span data-ttu-id="67346-114">如果他們想要新增災害復原能力，他們可以考慮建立另一個資料中心，並在其中新增另一個 [前端] 池，並將它與目前資料中心的前端池配對。</span><span class="sxs-lookup"><span data-stu-id="67346-114">If they wanted to add disaster recovery ability, they could consider establishing another datacenter and adding another Front End pool there, and pairing it with the Front End pool in their current datacenter.</span></span> <span data-ttu-id="67346-115">然後，如果發生影響其主要池的災難，系統管理員可能會將使用者容錯移轉至備份池。</span><span class="sxs-lookup"><span data-stu-id="67346-115">Then, if there was a disaster affecting their primary pool, the administrators could fail over users to the backup pool.</span></span>

  - <span data-ttu-id="67346-116">**後端伺服器會鏡像**   ，以提供更高的基本使用者功能可用性，組織已為每個前端池部署一個鏡像對後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-116">**Back End Servers are mirrored**   To provide more high availability for basic user features, the organization has deployed a mirrored pair of Back End Servers for each Front End pool.</span></span> <span data-ttu-id="67346-117">這是 Lync Server 2013 的新拓撲選項，且是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="67346-117">This is a new topology option for Lync Server 2013, and is optional.</span></span> <span data-ttu-id="67346-118">您可以改為選擇部署單一後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-118">You could choose to deploy a single Back End Server instead.</span></span>

  - <span data-ttu-id="67346-119">**監視伺服器資料庫選項。**   此組織已部署監控，以確保企業語音通話品質及 A/V 會議品質。</span><span class="sxs-lookup"><span data-stu-id="67346-119">**Monitoring Server database options.**   This organization has deployed Monitoring to ensure the quality of Enterprise Voice calls and A/V conferences.</span></span> <span data-ttu-id="67346-120">監視是在每個前端伺服器上部署，而監視資料庫則與後端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="67346-120">Monitoring is deployed on every Front End Server, and the Monitoring database is collocated with the Back End Servers.</span></span> <span data-ttu-id="67346-121">我們也支援監視資料庫位於個別伺服器上的拓撲。</span><span class="sxs-lookup"><span data-stu-id="67346-121">We also support topologies in which the Monitoring database is located on a separate server.</span></span>

  - <span data-ttu-id="67346-122">**Edge 伺服器高可用性**    在這個範例組織中，有20000個使用者，只要有一個 Edge 伺服器就足以達到效能。</span><span class="sxs-lookup"><span data-stu-id="67346-122">**Edge Server high availability**    In this example organization with 20,000 users, just one Edge Server would be sufficient for performance.</span></span> <span data-ttu-id="67346-123">不過，已部署兩個 Edge 伺服器的池中，以提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="67346-123">However, there is a pool of two Edge Servers deployed to provide high availability.</span></span>

  - <span data-ttu-id="67346-124">**分支網站部署選項。**   此拓撲中的組織已將企業語音部署為其語音方案。</span><span class="sxs-lookup"><span data-stu-id="67346-124">**Branch site deployment options.**   The organization in this topology has Enterprise Voice deployed as their voice solution.</span></span> <span data-ttu-id="67346-125">分支網站1沒有可復原的廣域網路（WAN）連結至中心網站，所以它擁有已部署來維護許多 Lync Server 功能的 Survivable 分支裝置，以便在指向中央網站的 WAN 連結關閉時使用。</span><span class="sxs-lookup"><span data-stu-id="67346-125">Branch Site 1 does not have a resilient wide area network (WAN) link to the central site, so it has a Survivable Branch Appliance deployed to maintain many Lync Server features in case the WAN link to the central site goes down.</span></span> <span data-ttu-id="67346-126">分支網站2不過有彈性 WAN 連結，所以只需要公開的交換式電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="67346-126">Branch Site 2 however has a resilient WAN link, so only a public switched telephone network (PSTN) gateway is needed.</span></span> <span data-ttu-id="67346-127">部署的 PSTN 閘道支援媒體旁路，因此分支網站2不需要任何轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-127">The PSTN gateway deployed there supports media bypass, so no Mediation Server is needed at Branch Site 2.</span></span> <span data-ttu-id="67346-128">如需決定要在分支網站上部署的內容的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="67346-128">For details about deciding what to deploy at a branch site, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="67346-129">**DNS 負載平衡。**   前端池 andEdge 伺服器池，具有部署 SIP 流量的 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="67346-129">**DNS load balancing.**   The Front End pool andEdge Server pool, have DNS load balancing for SIP traffic deployed.</span></span> <span data-ttu-id="67346-130">這消除了邊緣伺服器的硬體負載平衡器需求，並大大減少了其他池的硬體負載平衡器的設定和維護，因為只有 HTTP 流量需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="67346-130">This eliminates the need for hardware load balancers for the Edge Servers, and significantly lessens the setup and maintenance of the hardware load balancers for the other pools, as the hardware load balancers are needed only for HTTP traffic.</span></span> <span data-ttu-id="67346-131">如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="67346-131">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="67346-132">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="67346-132">**Exchange UM deployment.**</span></span> <span data-ttu-id="67346-133">這個參照拓撲包含 Exchange 整合通訊（UM）伺服器，該伺服器會執行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="67346-133">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="67346-134">如需有關 Exchange UM 的詳細資訊，請參閱規劃檔中的 lync server [2013 中的 Exchange 整合訊息整合規劃](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)（ [lync server 2013 中的託管 exchange](lync-server-2013-hosted-exchange-unified-messaging-integration.md)整合訊息整合）。</span><span class="sxs-lookup"><span data-stu-id="67346-134">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="67346-135">**Office Web Apps 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="67346-135">**Office Web Apps Server.**</span></span> <span data-ttu-id="67346-136">我們建議您在使用 Web 會議的每一個組織中部署 Office Web Apps Server 或 Office Web Apps 伺服器群。</span><span class="sxs-lookup"><span data-stu-id="67346-136">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="67346-137">Office Web Apps 伺服器可讓 Powerpoint 投影片呈現在網路會議中。</span><span class="sxs-lookup"><span data-stu-id="67346-137">Office Web Apps Server makes it possible for Powerpoint slides to be presented in web conferences.</span></span> <span data-ttu-id="67346-138">如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="67346-138">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="67346-139">**建議使用 Edge 伺服器。**   雖然不需要部署 Edge 伺服器，但我們建議將它用於任何部署大小。</span><span class="sxs-lookup"><span data-stu-id="67346-139">**Edge Servers are recommended.**   Although deploying an Edge Server is not required, we recommend it for any size of deployment.</span></span> <span data-ttu-id="67346-140">您可以部署 Edge 伺服器來將您的 Lync 伺服器投資最大化，為目前組織防火牆以外的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="67346-140">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="67346-141">其優點包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="67346-141">The benefits include the following:</span></span>
    
      - <span data-ttu-id="67346-142">貴組織的使用者可以使用 Lync Server 的功能（如果他們在家中或在路上）。</span><span class="sxs-lookup"><span data-stu-id="67346-142">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="67346-143">您的使用者可以邀請外部使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="67346-143">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="67346-144">如果您有合作夥伴、廠商或客戶組織，且使用 Lync Server，您可以建立與該組織的*聯盟關聯*。</span><span class="sxs-lookup"><span data-stu-id="67346-144">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="67346-145">接著，您的 Lync Server 部署會辨識來自該同盟組織的使用者，以更好的方式共同作業。</span><span class="sxs-lookup"><span data-stu-id="67346-145">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="67346-146">您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任一或所有專案： Windows Live、AOL、Yahoo\!和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="67346-146">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="67346-147">您可能需要使用這些服務的公用 IM 連線的個別授權。</span><span class="sxs-lookup"><span data-stu-id="67346-147">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="67346-148">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="67346-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="67346-149">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="67346-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="67346-150">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="67346-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="67346-151">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="67346-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="67346-152">已公佈。</span><span class="sxs-lookup"><span data-stu-id="67346-152">has been announced.</span></span> <span data-ttu-id="67346-153">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="67346-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="67346-154">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="67346-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="67346-155">名單.</span><span class="sxs-lookup"><span data-stu-id="67346-155">Messenger.</span></span> <span data-ttu-id="67346-156">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="67346-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="67346-157">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="67346-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="67346-158">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="67346-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="67346-159">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="67346-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="67346-160">**您可以新增控制器。**   如果此組織想要協助加強抵禦拒絕服務攻擊的安全性，也可以部署一個控制器池。</span><span class="sxs-lookup"><span data-stu-id="67346-160">**Directors could be added.**   If this organization wanted to help to increase security against denial of service attacks, it could also deploy a pool of Directors.</span></span> <span data-ttu-id="67346-161">Director 是 Lync Server 中不是家用使用者帳戶的個別、選擇性的伺服器角色，或提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="67346-161">A Director is a separate, optional server role in Lync Server that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="67346-162">它是一種內部的下一個躍點伺服器，可讓邊緣伺服器路由發往內部伺服器的入站 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="67346-162">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="67346-163">主管對輸入要求進行預驗證，並將它們重新導向至使用者的主區或伺服器。</span><span class="sxs-lookup"><span data-stu-id="67346-163">The Director pre-authenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="67346-164">在主管中進行預驗證，可在部署時丟棄使用者帳戶的要求。</span><span class="sxs-lookup"><span data-stu-id="67346-164">Pre-authentication at the Director allows for dropping of requests from user accounts unknown to the deployment.</span></span> <span data-ttu-id="67346-165">控制器可協助將前端伺服器與惡意流量（例如拒絕服務（DoS）攻擊）隔離。</span><span class="sxs-lookup"><span data-stu-id="67346-165">A Director helps insulate Front End Servers from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="67346-166">如果網路充斥在攻擊中的無效外部通信量，通信量就會結束在 Director 上。</span><span class="sxs-lookup"><span data-stu-id="67346-166">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span>

  - <span data-ttu-id="67346-167">**建議使用 System Center Operations Manager。**  我們建議您監視 Lync Server 部署的健康情況，以協助確保終端使用者的服務可用性。</span><span class="sxs-lookup"><span data-stu-id="67346-167">**System Center Operations Manager is recommended.**  We recommend that you monitor the health of your Lync Server deployment to help ensure service availability for end-users.</span></span> <span data-ttu-id="67346-168">您可以使用可從 Microsoft 免費下載的 Lync 系統中心作業管理員管理套件來監視 Lync。</span><span class="sxs-lookup"><span data-stu-id="67346-168">You can monitor Lync with the System Center Operations Manager Management Pack for Lync that is available as a free download from Microsoft.</span></span> <span data-ttu-id="67346-169">在 Lync 管理套件中，您可以在發生問題時，主動取得即時通知、執行綜合交易，以測試端對端 Lync 功能、取得服務可用性的報告等。</span><span class="sxs-lookup"><span data-stu-id="67346-169">With the Lync Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Lync functionality, get reports for service availability, and so on.</span></span> <span data-ttu-id="67346-170">這可協助您在最終使用者體驗到您的部署之前，提前回應您的部署問題。</span><span class="sxs-lookup"><span data-stu-id="67346-170"> This helps you to proactively respond to issues with your deployment before end-users experience them.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

