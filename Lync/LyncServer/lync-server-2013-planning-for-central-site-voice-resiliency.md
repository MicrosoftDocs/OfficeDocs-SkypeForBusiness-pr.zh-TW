---
title: Lync Server 2013：規劃中央網站語音恢復能力
description: Lync Server 2013：規劃中央網站語音恢復能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567379"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="821fc-103">在 Lync Server 2013 中規劃中央網站語音恢復能力</span><span class="sxs-lookup"><span data-stu-id="821fc-103">Planning for central site voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="821fc-104">_**主題上次修改日期：** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="821fc-104">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="821fc-105">越來越多的企業開始將網站散佈到全球各地。</span><span class="sxs-lookup"><span data-stu-id="821fc-105">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="821fc-106">維護緊急服務、存取服務台，以及在中央網站停止服務時執行重要商務工作的能力，對任何 Enterprise Voice 恢復解決方案都是必要的。</span><span class="sxs-lookup"><span data-stu-id="821fc-106">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="821fc-107">當中央網站無法使用時，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="821fc-107">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="821fc-108">必須提供語音容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="821fc-108">Voice failover must be provided.</span></span>

  - <span data-ttu-id="821fc-109">一般在中央網站上使用前端集區註冊的使用者，必須能夠使用替代的前端集區註冊。</span><span class="sxs-lookup"><span data-stu-id="821fc-109">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="821fc-110">若要執行此動作，可以建立多個 DNS SRV 記錄，每個記錄會解析為每一個中央網站的 Director 集區或前端集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-110">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="821fc-111">您可以調整 SRV 記錄的優先順序和權重，這樣該中央網站所提供的使用者就能在其他 SRV 記錄中取得對應的 Director 和前端集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-111">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="821fc-112">撥入其他網站或由其他網站撥出的使用者通話必須重新路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="821fc-112">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="821fc-113">本主題說明保障中央網站語音恢復能力的建議解決方案。</span><span class="sxs-lookup"><span data-stu-id="821fc-113">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="821fc-114">架構與拓撲</span><span class="sxs-lookup"><span data-stu-id="821fc-114">Architecture and Topology</span></span>

<span data-ttu-id="821fc-115">在中央網站規劃語音彈性功能時，需要有一個基本瞭解 Lync Server 2013 註冊機構在啟用語音容錯移轉時所扮演的中央角色。</span><span class="sxs-lookup"><span data-stu-id="821fc-115">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="821fc-116">Lync Server 註冊機構是一種伺服器角色，可讓用戶端註冊及驗證，並提供路由服務。</span><span class="sxs-lookup"><span data-stu-id="821fc-116">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="821fc-117">它與 Standard Edition server、前端伺服器、Director 或 Survivable 分支裝置上的其他元件一起存放。</span><span class="sxs-lookup"><span data-stu-id="821fc-117">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="821fc-118">註冊集區包含在前端集區上執行的註冊機構服務，且位於相同的網站。</span><span class="sxs-lookup"><span data-stu-id="821fc-118">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="821fc-119">前端集區必須進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="821fc-119">The Front End pool must be load balanced.</span></span> <span data-ttu-id="821fc-120">我們建議具備 DNS 平衡功能，不過如果只有硬體負載平衡也可接受。</span><span class="sxs-lookup"><span data-stu-id="821fc-120">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="821fc-121">Lync 用戶端會透過下列探索機制來探索前端集區：</span><span class="sxs-lookup"><span data-stu-id="821fc-121">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="821fc-122">DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="821fc-122">DNS SRV record</span></span>

2.  <span data-ttu-id="821fc-123">Lync Server 2013 中的自動探索 Web 服務 (新功能) </span><span class="sxs-lookup"><span data-stu-id="821fc-123">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="821fc-124">DHCP 選項 120</span><span class="sxs-lookup"><span data-stu-id="821fc-124">DHCP option 120</span></span>

<span data-ttu-id="821fc-125">在 Lync 用戶端連線至前端集區之後，它會被負載平衡器導向至集區中的前端伺服器之一。</span><span class="sxs-lookup"><span data-stu-id="821fc-125">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="821fc-126">然後，該前端伺服器又會將用戶端重新導向至集區中的首選註冊機構。</span><span class="sxs-lookup"><span data-stu-id="821fc-126">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="821fc-127">每個針對 Enterprise Voice 啟用的使用者會指派給特定的註冊機構集區，這會變成該使用者的主要註冊集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-127">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="821fc-128">在特定網站上，數百名或數千名使用者通常會共用單一主要登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-128">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="821fc-129">為了針對任何一個分支網站裡倚賴中央網站以獲得顯示狀態、會議或容錯移轉功能的使用者，記錄其對中央網站資源的使用情況，建議您將每位分支網站使用者視為向中央網站註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="821fc-129">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="821fc-130">分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="821fc-130">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="821fc-131">為了確保中央網站故障時的語音恢復能力，主要登錄器集區必須在另一個網站上設有一台指定的備份登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-131">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="821fc-132">您可以使用拓撲產生器恢復設定來設定備份。</span><span class="sxs-lookup"><span data-stu-id="821fc-132">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="821fc-133">假設兩個網站之間存在可恢復的 WAN 連結，則已無法再使用主要登錄器集區的使用者會自動導向至備用登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-133">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="821fc-134">下列步驟說明用戶端探索與註冊程序：</span><span class="sxs-lookup"><span data-stu-id="821fc-134">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="821fc-135">用戶端透過 DNS SRV 記錄來探索 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="821fc-135">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="821fc-136">在 Lync Server 2013 中，您可以設定 DNS SRV 記錄，以傳回 DNS SRV 查詢的一個以上 FQDN。</span><span class="sxs-lookup"><span data-stu-id="821fc-136">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="821fc-137">例如，如果 Contoso 企業擁有三個中央網站 (北美、歐洲與亞太地區) 並在每個中央網站擁有一個 Director 集區，DNS SRV 記錄可以分別指向這三個位置的個別 Director 集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="821fc-137">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="821fc-138">只要其中一個位置有 Director 集區可用，用戶端就可以連線至第一個躍點 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="821fc-138">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="821fc-139">使用 Director 集區是選用的。</span><span class="sxs-lookup"><span data-stu-id="821fc-139">Using a Director pool is optional.</span></span> <span data-ttu-id="821fc-140">可以改為使用前端集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-140">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="821fc-141">Director 集區會通知 Lync 用戶端使用者的主要註冊集區和備份報名者集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-141">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="821fc-142">Lync 用戶端會先嘗試連接至使用者的主要註冊集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-142">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="821fc-143">如果主要登錄器集區有回應，該登錄器就會接受註冊。</span><span class="sxs-lookup"><span data-stu-id="821fc-143">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="821fc-144">如果無法使用主要註冊集區，Lync 用戶端會嘗試連線至 [備份註冊機構] 集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-144">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="821fc-145">如果備份登錄器集區有回應且判斷使用者的主要登錄器集區沒有回應時 (藉由偵測特定容錯移轉間隔是否有活動訊號)，備份登錄器集區會接受使用者註冊。</span><span class="sxs-lookup"><span data-stu-id="821fc-145">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="821fc-146">在備份註冊機構偵測到主要報名者再次可用之後，[備份註冊機集區] 會將容錯移轉 Lync 用戶端重新導向至其主要集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-146">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="821fc-p110">下圖說明確保中央網站恢復能力的建議拓撲。這兩個網站由可恢復的 WAN 連結串連起來。當中央網站沒有回應時，指派至該集區的使用者就會被導向至備份網站進行註冊。</span><span class="sxs-lookup"><span data-stu-id="821fc-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="821fc-150">**中央網站語音恢復能力的建議拓撲**</span><span class="sxs-lookup"><span data-stu-id="821fc-150">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="821fc-151">![中央網站語音恢復能力的拓撲](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央網站語音恢復能力的拓撲")</span><span class="sxs-lookup"><span data-stu-id="821fc-151">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="821fc-152">需求和建議</span><span class="sxs-lookup"><span data-stu-id="821fc-152">Requirements and Recommendations</span></span>

<span data-ttu-id="821fc-153">以下為大多數組織在實作中央網站語音恢復能力時適用的需求與建議事項：</span><span class="sxs-lookup"><span data-stu-id="821fc-153">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="821fc-154">主要與備份登錄器集區所屬網站必須由可恢復的 WAN 連結來串連。</span><span class="sxs-lookup"><span data-stu-id="821fc-154">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="821fc-155">每個中央網站必須內含一個登錄器集區，且該集區必須包含一或多個登錄器。</span><span class="sxs-lookup"><span data-stu-id="821fc-155">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="821fc-156">每個註冊機構集區都必須使用 DNS 負載平衡、硬體負載平衡或兩者兩者進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="821fc-156">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="821fc-157">如需規劃負載平衡設定的詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="821fc-157">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="821fc-158">每個使用者都必須使用 Lync Server 管理命令介面 **get-csuser** Cmdlet 或 Lync server 控制台，指派給主要註冊集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-158">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="821fc-159">主要登錄器集區必須在其他中央網站設有一個備份登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-159">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="821fc-160">主要登錄器集區必須設為容錯移轉至備份登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-160">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="821fc-161">主要登錄器集區預設會在故障超過 300 秒之後容錯移轉至備份登錄器集區。</span><span class="sxs-lookup"><span data-stu-id="821fc-161">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="821fc-162">您可以使用 Lync Server 2013 拓撲產生器來變更此間隔。</span><span class="sxs-lookup"><span data-stu-id="821fc-162">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="821fc-163">如規劃檔中的「在[Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)」主題中所述，設定容錯移轉路由。</span><span class="sxs-lookup"><span data-stu-id="821fc-163">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="821fc-164">設定路由時，所指定的閘道必須與主要路由之指定閘道分屬不同網站。</span><span class="sxs-lookup"><span data-stu-id="821fc-164">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="821fc-165">如果中央網站內含主要管理伺服器，且該網站短期內可能無法恢復服務，則您需要在備份網站重新安裝管理工具，否則您將無法變更任何管理設定。</span><span class="sxs-lookup"><span data-stu-id="821fc-165">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="821fc-166">相依性</span><span class="sxs-lookup"><span data-stu-id="821fc-166">Dependencies</span></span>

<span data-ttu-id="821fc-167">Lync Server 取決於下列基礎結構和軟體元件，以確保語音復原能力：</span><span class="sxs-lookup"><span data-stu-id="821fc-167">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="821fc-168"><strong>元件</strong></span><span class="sxs-lookup"><span data-stu-id="821fc-168"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="821fc-169"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="821fc-169"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="821fc-170">DNS</span><span class="sxs-lookup"><span data-stu-id="821fc-170">DNS</span></span></p></td>
<td><p><span data-ttu-id="821fc-171">負責解析 SRV 記錄與 A 記錄以因應伺服器對伺服器，及伺服器對用戶端的連線需求</span><span class="sxs-lookup"><span data-stu-id="821fc-171">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="821fc-172">Exchange 與 Exchange Web 服務 (EWS)</span><span class="sxs-lookup"><span data-stu-id="821fc-172">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="821fc-173">連絡儲存裝置；行事曆資料</span><span class="sxs-lookup"><span data-stu-id="821fc-173">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="821fc-174">Exchange 整合通訊與 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="821fc-174">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="821fc-175">通話記錄、語音信箱清單、語音信箱</span><span class="sxs-lookup"><span data-stu-id="821fc-175">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="821fc-176">DHCP 選項 120</span><span class="sxs-lookup"><span data-stu-id="821fc-176">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="821fc-177">如果無可用的 DNS SRV，用戶端會嘗試使用 DHCP 選項 120 來探索登錄器。</span><span class="sxs-lookup"><span data-stu-id="821fc-177">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="821fc-178">若要執行此作業，您必須設定 DHCP 伺服器，或是必須啟用 Lync Server 2013 DHCP。</span><span class="sxs-lookup"><span data-stu-id="821fc-178">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="821fc-179">如需詳細資訊，請參閱 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 區段之分支網站恢復性需求</a> 中 Branch-Site 恢復的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="821fc-179">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="821fc-180">Survivable Voice 功能</span><span class="sxs-lookup"><span data-stu-id="821fc-180">Survivable Voice Features</span></span>

<span data-ttu-id="821fc-181">如果先前的需求與建議都實作完畢，則備份登錄器集區會提供下列語音功能：</span><span class="sxs-lookup"><span data-stu-id="821fc-181">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="821fc-182">撥出 PSTN 電話</span><span class="sxs-lookup"><span data-stu-id="821fc-182">Outbound PSTN calls</span></span>

  - <span data-ttu-id="821fc-183">撥入 PSTN 電話，前提是電話語音服務提供者支援容錯移轉至備份網站的功能</span><span class="sxs-lookup"><span data-stu-id="821fc-183">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="821fc-184">相同與不同的網站之間的使用者，皆可進行企業通話</span><span class="sxs-lookup"><span data-stu-id="821fc-184">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="821fc-185">基本通話處理，包括通話保留、取回和轉接</span><span class="sxs-lookup"><span data-stu-id="821fc-185">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="821fc-186">兩方立即訊息及相同網站的使用者之間共用音訊與視訊功能</span><span class="sxs-lookup"><span data-stu-id="821fc-186">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="821fc-187">來電轉接、端點同時響鈴、通話委派與小組通話服務，但前提是同一個網站裡通話委派的雙方或所有小組成員都有這些設定。</span><span class="sxs-lookup"><span data-stu-id="821fc-187">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="821fc-188">現有的電話與用戶端將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="821fc-188">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="821fc-189">詳細通話記錄 (CDR)</span><span class="sxs-lookup"><span data-stu-id="821fc-189">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="821fc-190">驗證與授權</span><span class="sxs-lookup"><span data-stu-id="821fc-190">Authentication and authorization</span></span>

<span data-ttu-id="821fc-191">依據這些功能的設定方式，當主要中央網站無法提供服務時，以下語音功能不一定能夠發揮功用：</span><span class="sxs-lookup"><span data-stu-id="821fc-191">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="821fc-192">語音信箱儲放與接聽</span><span class="sxs-lookup"><span data-stu-id="821fc-192">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="821fc-193">如果您想在主要中央網站中斷服務時提供 Exchange UM 服務的話，必須執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="821fc-193">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="821fc-194">變更 DNS SRV 記錄，以便中央網站的 Exchange UM 伺服器指向另一個網站的備份 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="821fc-194">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="821fc-195">將每一位使用者的 Exchange UM 撥號對應表設定為同時在中央網站和備份網站上包含 Exchange UM 伺服器，但將備份 Exchange UM 伺服器指定為停用。</span><span class="sxs-lookup"><span data-stu-id="821fc-195">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="821fc-196">若主網站無法使用，Exchange 系統管理員必須將備份網站上的 Exchange UM 伺服器標示為 [已啟用]。</span><span class="sxs-lookup"><span data-stu-id="821fc-196">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="821fc-197">如果上述兩種方案都不可行，則當中央網站無法使用時，便無法使用 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="821fc-197">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="821fc-198">所有會議類型</span><span class="sxs-lookup"><span data-stu-id="821fc-198">Conferencing of all types</span></span>
    
    <span data-ttu-id="821fc-p116">已經容錯移轉至備份網站的使用者，可以加入由開放使用集區的召集人所建立或主控的會議，但是由於該使用者所屬的主要集區已經不再提供服務，因此無法自行建立或主控會議。同理，其他使用者無法加入由受影響使用者之主要集區所主控的會議。</span><span class="sxs-lookup"><span data-stu-id="821fc-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="821fc-201">下列語音功能在主要中央網站中斷服務時將無法運作：</span><span class="sxs-lookup"><span data-stu-id="821fc-201">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="821fc-202">會議自動語音應答</span><span class="sxs-lookup"><span data-stu-id="821fc-202">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="821fc-203">顯示狀態與 DND 基礎路由</span><span class="sxs-lookup"><span data-stu-id="821fc-203">Presence and DND-based routing</span></span>

  - <span data-ttu-id="821fc-204">更新來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="821fc-204">Updating call forwarding settings</span></span>

  - <span data-ttu-id="821fc-205">回應群組服務和通話駐留</span><span class="sxs-lookup"><span data-stu-id="821fc-205">Response Group service and Call Park</span></span>

  - <span data-ttu-id="821fc-206">佈建新電話與用戶端</span><span class="sxs-lookup"><span data-stu-id="821fc-206">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="821fc-207">通訊錄 Web 搜尋</span><span class="sxs-lookup"><span data-stu-id="821fc-207">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="821fc-208">另請參閱</span><span class="sxs-lookup"><span data-stu-id="821fc-208">See Also</span></span>


[<span data-ttu-id="821fc-209">在 Lync Server 2013 中規劃分支網站語音彈性</span><span class="sxs-lookup"><span data-stu-id="821fc-209">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

