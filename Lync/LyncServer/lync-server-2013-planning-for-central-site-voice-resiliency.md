---
title: Lync Server 2013：規劃中央網站語音回復性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="693b3-102">在 Lync Server 2013 中規劃中央網站語音回復性</span><span class="sxs-lookup"><span data-stu-id="693b3-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="693b3-103">_**主題上次修改日期：** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="693b3-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="693b3-104">企業越來越多地在全球各地分佈多個網站。</span><span class="sxs-lookup"><span data-stu-id="693b3-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="693b3-105">維護緊急服務、存取技術支援人員，以及在中央網站不在服務時執行重要業務工作的能力，對於任何企業語音復原方案而言都是必要的。</span><span class="sxs-lookup"><span data-stu-id="693b3-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="693b3-106">當中央網站變得無法使用時，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="693b3-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="693b3-107">必須提供語音容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="693b3-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="693b3-108">通常在中央網站上使用前端池登錄的使用者，必須能夠使用備用的 [前端] 池進行註冊。</span><span class="sxs-lookup"><span data-stu-id="693b3-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="693b3-109">這可以透過建立多個 DNS SRV 記錄來完成，每個記錄都可解析為每個中心網站中的控制器池或前端池。</span><span class="sxs-lookup"><span data-stu-id="693b3-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="693b3-110">您可以調整 SRV 記錄的優先順序和權重，讓該中央網站所提供的使用者取得對應的控制器，並將前端池排在其他 SRV 記錄中。</span><span class="sxs-lookup"><span data-stu-id="693b3-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="693b3-111">在其他網站的使用者撥打電話和寄件者必須重新路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="693b3-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="693b3-112">本主題將說明安全的中心網站語音復原建議的解決方案。</span><span class="sxs-lookup"><span data-stu-id="693b3-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="693b3-113">架構與拓撲</span><span class="sxs-lookup"><span data-stu-id="693b3-113">Architecture and Topology</span></span>

<span data-ttu-id="693b3-114">若要在中央網站規劃語音復原，必須先基本瞭解 Lync Server 2013 註冊機構在啟用語音容錯移轉時所扮演的中心角色。</span><span class="sxs-lookup"><span data-stu-id="693b3-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="693b3-115">Lync Server 註冊機構是一種伺服器角色，可啟用用戶端註冊和驗證並提供路由服務。</span><span class="sxs-lookup"><span data-stu-id="693b3-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="693b3-116">它與標準版伺服器、前端伺服器、控制器或 Survivable 分支裝置上的其他元件一起存放。</span><span class="sxs-lookup"><span data-stu-id="693b3-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="693b3-117">註冊機構池是由在前端池執行並位於相同網站的註冊機構服務所組成。</span><span class="sxs-lookup"><span data-stu-id="693b3-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="693b3-118">前端池必須是負載均衡的。</span><span class="sxs-lookup"><span data-stu-id="693b3-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="693b3-119">建議使用 DNS 負載平衡，但硬體負載平衡是可接受的。</span><span class="sxs-lookup"><span data-stu-id="693b3-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="693b3-120">Lync 用戶端透過下列探索機制來探索前端池：</span><span class="sxs-lookup"><span data-stu-id="693b3-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="693b3-121">DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="693b3-121">DNS SRV record</span></span>

2.  <span data-ttu-id="693b3-122">自動探索 Web 服務（Lync Server 2013 中的新功能）</span><span class="sxs-lookup"><span data-stu-id="693b3-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="693b3-123">DHCP 選項120</span><span class="sxs-lookup"><span data-stu-id="693b3-123">DHCP option 120</span></span>

<span data-ttu-id="693b3-124">在 Lync 用戶端連線到前端池之後，它會由負載平衡器導向至池中的一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="693b3-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="693b3-125">接著，該前端伺服器會將用戶端重定向到池中的首選註冊機構。</span><span class="sxs-lookup"><span data-stu-id="693b3-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="693b3-126">針對企業語音啟用的每個使用者都會指派給特定的註冊機構池，這會成為該使用者的主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="693b3-127">在特定的網站，幾百或上千個使用者通常會共用單一主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="693b3-128">若要考慮針對中央網站資源（無論是目前狀態、會議或容錯移轉的中心網站），由任何分支網站使用者使用的方式，建議您考慮每個分支網站使用者，就像使用者是使用中央網站註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="693b3-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="693b3-129">分支網站使用者的數目目前沒有限制，包括向 Survivable 分支裝置註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="693b3-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="693b3-130">若要在中央網站發生故障時保證語音復原能力，主要註冊機構池必須有一個指定的備份註冊機構池位於另一個網站。</span><span class="sxs-lookup"><span data-stu-id="693b3-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="693b3-131">您可以使用 [拓撲產生器復原設定] 來設定備份。</span><span class="sxs-lookup"><span data-stu-id="693b3-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="693b3-132">假設在兩個網站之間有彈性的 WAN 連結，主要註冊機構池已不再可用的使用者會自動導向到備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="693b3-133">下列步驟說明用戶端探索與註冊程式：</span><span class="sxs-lookup"><span data-stu-id="693b3-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="693b3-134">用戶端透過 DNS SRV 記錄來探索 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="693b3-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="693b3-135">在 Lync Server 2013 中，您可以設定 DNS SRV 記錄，將多個 FQDN 傳回給 DNS SRV 查詢。</span><span class="sxs-lookup"><span data-stu-id="693b3-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="693b3-136">例如，如果企業 Contoso 有三個中心網站（北美、歐洲和亞太地區），且每個中央網站都有一個控制器池，則 DNS SRV 記錄可以指向三個位置中的每一個控制器池 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="693b3-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="693b3-137">只要有其中一個位置的控制器池可供使用，用戶端就可以連線到第一個躍點 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="693b3-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="693b3-138">使用控制器池是選用的。</span><span class="sxs-lookup"><span data-stu-id="693b3-138">Using a Director pool is optional.</span></span> <span data-ttu-id="693b3-139">您可以改為使用前端池。</span><span class="sxs-lookup"><span data-stu-id="693b3-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="693b3-140">控制器池會通知 Lync 用戶端使用者的主要註冊機構池和備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="693b3-141">Lync 用戶端會先嘗試連線到使用者的主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="693b3-142">如果有可用的主要註冊機構池，註冊機構就會接受註冊。</span><span class="sxs-lookup"><span data-stu-id="693b3-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="693b3-143">如果主要註冊機構池無法使用，Lync 用戶端會嘗試連線到 [備份註冊機構] 池。</span><span class="sxs-lookup"><span data-stu-id="693b3-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="693b3-144">如果備份註冊機構池可用，且已確定使用者的主要註冊機構池無法使用（在特定的容錯移轉間隔內檢測到缺少心跳），備份註冊機構池就會接受使用者的註冊。</span><span class="sxs-lookup"><span data-stu-id="693b3-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="693b3-145">在備份註冊機構檢測到主要註冊機構再次提供後，備份註冊機構池會將容錯移轉 Lync 用戶端重新導向至其主要池。</span><span class="sxs-lookup"><span data-stu-id="693b3-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="693b3-146">下圖顯示可保證中心網站復原的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="693b3-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="693b3-147">這兩個網站是透過彈性 WAN 連結來連接。</span><span class="sxs-lookup"><span data-stu-id="693b3-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="693b3-148">如果中央網站變得無法使用，指派給該文件庫的使用者會被導向至備份網站進行註冊。</span><span class="sxs-lookup"><span data-stu-id="693b3-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="693b3-149">**中央網站語音復原的建議拓撲**</span><span class="sxs-lookup"><span data-stu-id="693b3-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="693b3-150">中央網站語音![resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "拓")朴的拓撲語音 resliency</span><span class="sxs-lookup"><span data-stu-id="693b3-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="693b3-151">需求與建議</span><span class="sxs-lookup"><span data-stu-id="693b3-151">Requirements and Recommendations</span></span>

<span data-ttu-id="693b3-152">下列針對實施中心網站語音復原的需求和建議適用于大多陣列織：</span><span class="sxs-lookup"><span data-stu-id="693b3-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="693b3-153">主要和備份註冊器池所駐留的網站應該由彈性 WAN 連結來連接。</span><span class="sxs-lookup"><span data-stu-id="693b3-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="693b3-154">每個中央網站都必須包含由一或多位註冊機構組成的註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="693b3-155">每個註冊機構池都必須使用 DNS 負載平衡、硬體負載平衡或兩者同時進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="693b3-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="693b3-156">如需規劃負載平衡配置的詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="693b3-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="693b3-157">每個使用者都必須使用 Lync Server 管理命令介面**move-csuser** Cmdlet 或 lync server [控制台] 指派給主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="693b3-158">主要註冊機構池必須有一個位於不同中央網站的單一備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="693b3-159">主要註冊機構池必須設定為容錯移轉至備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="693b3-160">根據預設，主要註冊機構會設定為在300秒間隔後容錯移轉至備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="693b3-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="693b3-161">您可以使用 Lync Server 2013 拓撲產生器來變更此間隔。</span><span class="sxs-lookup"><span data-stu-id="693b3-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="693b3-162">如在規劃檔中的 [[在 Lync Server 2013 中設定容錯移轉路線](lync-server-2013-configuring-a-failover-route.md)] 主題中所述，設定容錯移轉路線。</span><span class="sxs-lookup"><span data-stu-id="693b3-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="693b3-163">設定路線時，請指定位於主要路由中指定之閘道以外的網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="693b3-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="693b3-164">如果中央網站包含您的主要管理伺服器，而且網站可能會在較長的期限內關閉，您必須在備份網站上重新安裝管理工具;否則，您將無法變更任何管理設定。</span><span class="sxs-lookup"><span data-stu-id="693b3-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="693b3-165">因素</span><span class="sxs-lookup"><span data-stu-id="693b3-165">Dependencies</span></span>

<span data-ttu-id="693b3-166">Lync Server 依賴下列基礎結構和軟體元件，以確保語音復原：</span><span class="sxs-lookup"><span data-stu-id="693b3-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="693b3-167"><strong>元件</strong></span><span class="sxs-lookup"><span data-stu-id="693b3-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="693b3-168"><strong>多功能</strong></span><span class="sxs-lookup"><span data-stu-id="693b3-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="693b3-169">DNS</span><span class="sxs-lookup"><span data-stu-id="693b3-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="693b3-170">解析伺服器伺服器與伺服器用戶端連線的 SRV 記錄及記錄</span><span class="sxs-lookup"><span data-stu-id="693b3-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="693b3-171">Exchange 與 Exchange Web 服務（EWS）</span><span class="sxs-lookup"><span data-stu-id="693b3-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="693b3-172">連絡人儲存空間;行事歷數據</span><span class="sxs-lookup"><span data-stu-id="693b3-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="693b3-173">Exchange 整合訊息與 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="693b3-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="693b3-174">通話記錄、語音信箱清單、語音信箱</span><span class="sxs-lookup"><span data-stu-id="693b3-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="693b3-175">DHCP 選項120</span><span class="sxs-lookup"><span data-stu-id="693b3-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="693b3-176">如果 DNS SRV 無法使用，用戶端會嘗試使用 DHCP 選項120來探索註冊機。</span><span class="sxs-lookup"><span data-stu-id="693b3-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="693b3-177">若要使用此功能，必須設定 DHCP 伺服器或啟用 Lync Server 2013 DHCP。</span><span class="sxs-lookup"><span data-stu-id="693b3-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="693b3-178">如需詳細資訊，請參閱<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013</a>區段的分支網站復原需求中的分支網站復原需求的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="693b3-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="693b3-179">Survivable 語音功能</span><span class="sxs-lookup"><span data-stu-id="693b3-179">Survivable Voice Features</span></span>

<span data-ttu-id="693b3-180">如果已實現前面的需求和建議，則 [備份註冊機構] 池會提供下列語音功能：</span><span class="sxs-lookup"><span data-stu-id="693b3-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="693b3-181">呼出 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="693b3-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="693b3-182">當電話服務提供者支援容錯移轉至備份網站的功能時，輸入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="693b3-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="693b3-183">在相同網站和兩個不同網站之間的使用者之間的企業通話</span><span class="sxs-lookup"><span data-stu-id="693b3-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="693b3-184">基本呼叫處理，包括呼叫保留、檢索及轉移</span><span class="sxs-lookup"><span data-stu-id="693b3-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="693b3-185">兩方立即訊息，以及在相同網站的使用者之間共用音訊與影片</span><span class="sxs-lookup"><span data-stu-id="693b3-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="693b3-186">來電轉接、同時撥打端點、呼叫委派及小組通話服務，但僅限雙方都在相同的網站上設定呼叫委派或所有團隊成員的情況下。</span><span class="sxs-lookup"><span data-stu-id="693b3-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="693b3-187">現有的電話和用戶端仍能正常運作。</span><span class="sxs-lookup"><span data-stu-id="693b3-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="693b3-188">詳細通話記錄 (CDR)</span><span class="sxs-lookup"><span data-stu-id="693b3-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="693b3-189">驗證與授權</span><span class="sxs-lookup"><span data-stu-id="693b3-189">Authentication and authorization</span></span>

<span data-ttu-id="693b3-190">根據設定的方式，下列語音功能可能會在主要中心網站不在服務時運作：</span><span class="sxs-lookup"><span data-stu-id="693b3-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="693b3-191">語音信箱存放與檢索</span><span class="sxs-lookup"><span data-stu-id="693b3-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="693b3-192">如果您想要讓 Exchange UM 在主要中央網站不在服務時可用，您必須執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="693b3-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="693b3-193">變更 DNS SRV 記錄，讓中央網站上的 Exchange UM 伺服器指向其他網站上的 [備份 Exchange UM 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="693b3-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="693b3-194">設定每個使用者的 Exchange UM 撥號計畫，以將 Exchange UM 伺服器同時納入中心網站和備份網站，但將備份 Exchange UM 伺服器指定為已停用。</span><span class="sxs-lookup"><span data-stu-id="693b3-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="693b3-195">如果主要網站無法使用，Exchange 管理員必須在備份網站將 Exchange UM 伺服器標示為 [已啟用]。</span><span class="sxs-lookup"><span data-stu-id="693b3-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="693b3-196">如果上述方案都無法使用，則在中央網站無法使用的情況下，Exchange UM 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="693b3-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="693b3-197">所有類型的會議</span><span class="sxs-lookup"><span data-stu-id="693b3-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="693b3-198">已容錯移轉至備份網站的使用者可以加入由召集人所建立或託管的會議，但無法在自己的主要池上建立或託管會議，但已不再提供該會議。</span><span class="sxs-lookup"><span data-stu-id="693b3-198">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available.</span></span> <span data-ttu-id="693b3-199">同樣地，其他人不能加入託管在受影響使用者的主要池中的會議。</span><span class="sxs-lookup"><span data-stu-id="693b3-199">Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="693b3-200">當主要的中央網站不在服務時，下列語音功能無法運作：</span><span class="sxs-lookup"><span data-stu-id="693b3-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="693b3-201">會議自動助理</span><span class="sxs-lookup"><span data-stu-id="693b3-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="693b3-202">目前狀態與 DND 的路由</span><span class="sxs-lookup"><span data-stu-id="693b3-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="693b3-203">更新來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="693b3-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="693b3-204">回應群組服務和通話駐留</span><span class="sxs-lookup"><span data-stu-id="693b3-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="693b3-205">提供新的電話和用戶端</span><span class="sxs-lookup"><span data-stu-id="693b3-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="693b3-206">通訊錄網頁搜尋</span><span class="sxs-lookup"><span data-stu-id="693b3-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="693b3-207">請參閱</span><span class="sxs-lookup"><span data-stu-id="693b3-207">See Also</span></span>


[<span data-ttu-id="693b3-208">在 Lync Server 2013 中規劃分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="693b3-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

