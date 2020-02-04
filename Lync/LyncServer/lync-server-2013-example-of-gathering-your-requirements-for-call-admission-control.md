---
title: 收集通話許可控制需求的範例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345f5d7e41dd9da3e6d68c59ce9656d3052c57b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="397aa-102">範例：在 Lync Server 2013 中收集您對通話許可控制的需求</span><span class="sxs-lookup"><span data-stu-id="397aa-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="397aa-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="397aa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="397aa-104">這個範例示範如何規劃及實現通話許可控制（CAC）。</span><span class="sxs-lookup"><span data-stu-id="397aa-104">This example shows you how to plan for and implement call admission control (CAC).</span></span> <span data-ttu-id="397aa-105">從較高層次來看，這包含下列活動：</span><span class="sxs-lookup"><span data-stu-id="397aa-105">At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="397aa-106">找出您所有的網路中心和 backbones （稱為「*網路區域*」）。</span><span class="sxs-lookup"><span data-stu-id="397aa-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="397aa-107">找出將管理每個網路區域 CAC 的 Lync Server 中心網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="397aa-108">找出並定義連接至每個網路區域的*網路網站*。</span><span class="sxs-lookup"><span data-stu-id="397aa-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="397aa-109">針對連接至 WAN 的每個網路網站，請描述 WAN 連線的頻寬容量，以及網路系統管理員針對 Lync Server 媒體流量所設定的頻寬限制（如果適用的話）。</span><span class="sxs-lookup"><span data-stu-id="397aa-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="397aa-110">您不需要包含連接至 WAN 的網站不受頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="397aa-111">將網路中的每個子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="397aa-112">對應網路區域之間的連結。</span><span class="sxs-lookup"><span data-stu-id="397aa-112">Map the links between the network regions.</span></span> <span data-ttu-id="397aa-113">針對每個連結，描述其頻寬容量，以及網路系統管理員在 Lync Server 媒體流量上所放的任何限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="397aa-114">在每一組網路區域之間定義路由。</span><span class="sxs-lookup"><span data-stu-id="397aa-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="397aa-115">收集所需的資訊</span><span class="sxs-lookup"><span data-stu-id="397aa-115">Gather the Required Information</span></span>

<span data-ttu-id="397aa-116">若要準備通話許可控制，請收集下列步驟所述的資訊：</span><span class="sxs-lookup"><span data-stu-id="397aa-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="397aa-117">識別您的網路區域。</span><span class="sxs-lookup"><span data-stu-id="397aa-117">Identify your network regions.</span></span> <span data-ttu-id="397aa-118">網路區域代表網路骨幹或網路中樞。</span><span class="sxs-lookup"><span data-stu-id="397aa-118">A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="397aa-119">網路骨幹或網路中樞是電腦網路基礎結構的一部分，可互連各個網路元件，提供不同局域網或子網之間資訊交換的路徑。</span><span class="sxs-lookup"><span data-stu-id="397aa-119">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="397aa-120">中樞可將許多不同的網路（從較小的位置到廣域地理區域）相互結合。</span><span class="sxs-lookup"><span data-stu-id="397aa-120">A backbone can tie together diverse networks, from a small location to a wide geographic area.</span></span> <span data-ttu-id="397aa-121">中樞的容量通常大於與其連接的網路的容量。</span><span class="sxs-lookup"><span data-stu-id="397aa-121">The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="397aa-122">我們的範例拓朴有三個網路區域：北美、EMEA 及 APAC。</span><span class="sxs-lookup"><span data-stu-id="397aa-122">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="397aa-123">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="397aa-123">A network region contains a collection of network sites.</span></span> <span data-ttu-id="397aa-124">與您的網路系統管理員合作，為您的企業定義網路區域。</span><span class="sxs-lookup"><span data-stu-id="397aa-124">Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="397aa-125">找出每個網路區域的關聯中心網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="397aa-126">中央網站包含至少一個前端伺服器，也是 Lync Server 部署，它會針對透過網路區域的 WAN 連線而傳送的所有媒體流量管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="397aa-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="397aa-127">**將商業網路分成三個網路區域的範例**</span><span class="sxs-lookup"><span data-stu-id="397aa-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="397aa-128">![三個網路地區的網路拓撲範例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "三個網路地區的網路拓撲範例")</span><span class="sxs-lookup"><span data-stu-id="397aa-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="397aa-129">多協定標籤切換（MPLS）網路應該表示為網路區域，每個地理位置都有對應的網路網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="397aa-130">如需詳細資訊，請參閱規劃檔中的「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">使用 Lync Server 2013 的 MPLS 網路上的通話許可控制</A>」主題。</span><span class="sxs-lookup"><span data-stu-id="397aa-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="397aa-131">在上述的網路拓朴範例中，有三個網路區域，每個都有管理 CAC 的 Lync Server 中央網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="397aa-132">地理區域附近會選取適當的網路區域中心網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="397aa-133">因為媒體流量會在網路區域內最不等，所以由地理位置附近擁有者會將它設為自包含，即使其他中央網站都無法使用也會繼續運作。</span><span class="sxs-lookup"><span data-stu-id="397aa-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="397aa-134">在這個範例中，名為芝加哥的 Lync Server 部署是北美地區的中心網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="397aa-135">北美洲中的所有 Lync 使用者都是駐留在芝加哥部署的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="397aa-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="397aa-136">下表顯示所有三個網路區域的中心網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="397aa-137">網路區域及其關聯的中央網站</span><span class="sxs-lookup"><span data-stu-id="397aa-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-138">網路區域</span><span class="sxs-lookup"><span data-stu-id="397aa-138">Network Region</span></span></th>
    <th><span data-ttu-id="397aa-139">中央網站</span><span class="sxs-lookup"><span data-stu-id="397aa-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-140">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-141">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-142">中東</span><span class="sxs-lookup"><span data-stu-id="397aa-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="397aa-143">位於</span><span class="sxs-lookup"><span data-stu-id="397aa-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-144">APAC</span><span class="sxs-lookup"><span data-stu-id="397aa-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="397aa-145">首都</span><span class="sxs-lookup"><span data-stu-id="397aa-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="397aa-146">根據您的 Lync 伺服器拓撲，相同的中央網站可以指派給多個網路區域。</span><span class="sxs-lookup"><span data-stu-id="397aa-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="397aa-147">針對每個網路區域，找出 WAN 連線不受頻寬限制的所有網路網站（辦公室或位置）。</span><span class="sxs-lookup"><span data-stu-id="397aa-147">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained.</span></span> <span data-ttu-id="397aa-148">因為這些網站的頻寬不受限制，所以您不需要將 CAC 頻寬原則套用到它們。</span><span class="sxs-lookup"><span data-stu-id="397aa-148">Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="397aa-149">在下表所示的範例中，三個網路網站沒有頻寬限制的 WAN 連結：北京、芝加哥及底特律。</span><span class="sxs-lookup"><span data-stu-id="397aa-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="397aa-150">網路網站未受 WAN 頻寬的限制</span><span class="sxs-lookup"><span data-stu-id="397aa-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-151">網路網站</span><span class="sxs-lookup"><span data-stu-id="397aa-151">Network Site</span></span></th>
    <th><span data-ttu-id="397aa-152">網路區域</span><span class="sxs-lookup"><span data-stu-id="397aa-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-153">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="397aa-154">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-155">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="397aa-156">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-157">底特律</span><span class="sxs-lookup"><span data-stu-id="397aa-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="397aa-158">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="397aa-159">針對每個網路區域，找出透過頻寬限制 WAN 連結連接到網路區域的所有網路網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="397aa-160">為了協助確保音訊與視頻品質，我們建議這些頻寬限制的網路網站擁有 Wan 監控和 CAC 頻寬原則，這些原則會限制媒體（語音或視頻）流量流入或從網路區域。</span><span class="sxs-lookup"><span data-stu-id="397aa-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="397aa-161">在下表所示的範例中，有三個由 WAN 頻寬所限制的網路網站： [Reno] 和 [Albuquerque]。</span><span class="sxs-lookup"><span data-stu-id="397aa-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="397aa-162">受 WAN 頻寬限制的網路網站</span><span class="sxs-lookup"><span data-stu-id="397aa-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-163">網路網站</span><span class="sxs-lookup"><span data-stu-id="397aa-163">Network Site</span></span></th>
    <th><span data-ttu-id="397aa-164">網路區域</span><span class="sxs-lookup"><span data-stu-id="397aa-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="397aa-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="397aa-166">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-167">Reno</span><span class="sxs-lookup"><span data-stu-id="397aa-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="397aa-168">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-169">至今波特蘭</span><span class="sxs-lookup"><span data-stu-id="397aa-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="397aa-170">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="397aa-171">**由 WAN 頻寬（底特律、Reno 和 Albuquerque 所限制的三個網路網站，即北美擁有3個不受頻寬限制的網路區域（芝加哥、紐約和）和三個網路網站**</span><span class="sxs-lookup"><span data-stu-id="397aa-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="397aa-172">![受 WAN 頻寬限制的網路站台範例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "受 WAN 頻寬限制的網路站台範例")</span><span class="sxs-lookup"><span data-stu-id="397aa-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="397aa-173">針對每個頻寬受限制的 WAN 連結，請判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="397aa-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="397aa-174">您想要針對所有併發音訊會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="397aa-175">如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-176">您想要為每個個別音訊會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-176">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="397aa-177">預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-177">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="397aa-178">您想要針對所有併發影片會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="397aa-179">如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-180">您想要為每個個別的影片會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-180">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="397aa-181">預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-181">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="397aa-182">含 WAN 頻寬限制資訊的網路網站（頻寬以 kbps 為單位）</span><span class="sxs-lookup"><span data-stu-id="397aa-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-183">網路網站</span><span class="sxs-lookup"><span data-stu-id="397aa-183">Network Site</span></span></th>
    <th><span data-ttu-id="397aa-184">網路區域</span><span class="sxs-lookup"><span data-stu-id="397aa-184">Network Region</span></span></th>
    <th><span data-ttu-id="397aa-185">BW 限制</span><span class="sxs-lookup"><span data-stu-id="397aa-185">BW Limit</span></span></th>
    <th><span data-ttu-id="397aa-186">音訊限制</span><span class="sxs-lookup"><span data-stu-id="397aa-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="397aa-187">音訊會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="397aa-188">影片限制</span><span class="sxs-lookup"><span data-stu-id="397aa-188">Video Limit</span></span></th>
    <th><span data-ttu-id="397aa-189">影片會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="397aa-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="397aa-191">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-192">5,000</span><span class="sxs-lookup"><span data-stu-id="397aa-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-193">2000</span><span class="sxs-lookup"><span data-stu-id="397aa-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-194">175</span><span class="sxs-lookup"><span data-stu-id="397aa-194">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-195">1400</span><span class="sxs-lookup"><span data-stu-id="397aa-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="397aa-196">700</span><span class="sxs-lookup"><span data-stu-id="397aa-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-197">Reno</span><span class="sxs-lookup"><span data-stu-id="397aa-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="397aa-198">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-199">10000</span><span class="sxs-lookup"><span data-stu-id="397aa-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-200">4000</span><span class="sxs-lookup"><span data-stu-id="397aa-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-201">175</span><span class="sxs-lookup"><span data-stu-id="397aa-201">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-202">2800</span><span class="sxs-lookup"><span data-stu-id="397aa-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="397aa-203">700</span><span class="sxs-lookup"><span data-stu-id="397aa-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-204">至今波特蘭</span><span class="sxs-lookup"><span data-stu-id="397aa-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="397aa-205">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-206">5,000</span><span class="sxs-lookup"><span data-stu-id="397aa-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-207">4000</span><span class="sxs-lookup"><span data-stu-id="397aa-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-208">175</span><span class="sxs-lookup"><span data-stu-id="397aa-208">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-209">2800</span><span class="sxs-lookup"><span data-stu-id="397aa-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="397aa-210">700</span><span class="sxs-lookup"><span data-stu-id="397aa-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-211">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="397aa-212">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-213">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-214">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-215">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-216">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-217">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-218">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="397aa-219">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-220">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-221">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-222">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-223">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-224">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-225">底特律</span><span class="sxs-lookup"><span data-stu-id="397aa-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="397aa-226">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-227">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-228">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-229">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-230">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-231">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="397aa-232">針對您網路中的每個子網，指定其相關的網路網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="397aa-233">您網路中的每個子網都必須與網路網站相關聯，即使網路網站未受頻寬限制也一樣。</span><span class="sxs-lookup"><span data-stu-id="397aa-233">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained.</span></span> <span data-ttu-id="397aa-234">這是因為呼叫許可控制會使用子網資訊來判斷端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-234">This is because call admission control uses subnet information to determine at which network site an endpoint is located.</span></span> <span data-ttu-id="397aa-235">當會話中雙方雙方的位置都已決定時，通話許可控制可以判斷是否有足夠的頻寬來建立通話。</span><span class="sxs-lookup"><span data-stu-id="397aa-235">When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call.</span></span> <span data-ttu-id="397aa-236">當透過沒有頻寬限制的連結建立會話時，會產生警示。</span><span class="sxs-lookup"><span data-stu-id="397aa-236">When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="397aa-237">如果您部署音訊/視頻邊緣伺服器，則每個 Edge 伺服器的公用 IP 位址都必須與部署邊緣伺服器的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="397aa-238">A/V 邊緣伺服器的每個公用 IP 位址，都必須以子網路遮罩為32的子網新增至您的網路設定設定。</span><span class="sxs-lookup"><span data-stu-id="397aa-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="397aa-239">例如，如果您在芝加哥部署 A/V 邊緣伺服器，那麼針對這些伺服器的每個外部 IP 位址，都會建立一個子網路遮罩為32的子網，並將網路 site 芝加哥與這些子網建立關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="397aa-240">如需有關公用 IP 位址的詳細資料，請參閱在規劃檔中，針對<A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 判斷外部 A/V 防火牆和埠需求</A>。</span><span class="sxs-lookup"><span data-stu-id="397aa-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="397aa-241">會產生一個金鑰健康情況指標（KHI）警示，指定您網路中存在的 IP 位址清單，但不與子網建立關聯，或者包含 IP 位址的子網不與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-241">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="397aa-242">在8小時內，不會多次引發此通知。</span><span class="sxs-lookup"><span data-stu-id="397aa-242">This alert will not be raised more than once within an 8 hour period.</span></span> <span data-ttu-id="397aa-243">相關的警示資訊和範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="397aa-243">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="397aa-244"><STRONG>來源：</STRONG>CS 頻寬原則服務（核心）</span><span class="sxs-lookup"><span data-stu-id="397aa-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="397aa-245"><STRONG>事件號碼：</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="397aa-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="397aa-246"><STRONG>層級：</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="397aa-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="397aa-247"><STRONG>描述：</STRONG>下列 IP 位址的子網： &lt;ip 位址&gt;清單未設定，或子網不與網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="397aa-248"><STRONG>原因：</STRONG>[網路設定] 中缺少對應 IP 位址的子網，或子網不會與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="397aa-249"><STRONG>解決方式：</STRONG>將與先前的 IP 位址清單相對應的子網新增至 [網路設定]，並將每個子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="397aa-250">例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其關聯的子網不屬於網路網站。</span><span class="sxs-lookup"><span data-stu-id="397aa-250">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site.</span></span> <span data-ttu-id="397aa-251">如果 10.121.248.0/24 和 10.121.249.0/24 是這些位址對應的子網，您可以解決此問題，如下所示：</span><span class="sxs-lookup"><span data-stu-id="397aa-251">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="397aa-252">請確定 IP 位址10.121.248.226 已與 10.121.249.0/24 子網相關聯的 10.121.248.0/24 子網和 IP 位址10.121.249.20 相關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="397aa-253">請確定 10.121.248.0/24 和 10.121.249.0/24 子網分別與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="397aa-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="397aa-254">網路網站與相關子網（kbps 的頻寬）</span><span class="sxs-lookup"><span data-stu-id="397aa-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-255">網路網站</span><span class="sxs-lookup"><span data-stu-id="397aa-255">Network Site</span></span></th>
    <th><span data-ttu-id="397aa-256">網路區域</span><span class="sxs-lookup"><span data-stu-id="397aa-256">Network Region</span></span></th>
    <th><span data-ttu-id="397aa-257">BW 限制</span><span class="sxs-lookup"><span data-stu-id="397aa-257">BW Limit</span></span></th>
    <th><span data-ttu-id="397aa-258">音訊限制</span><span class="sxs-lookup"><span data-stu-id="397aa-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="397aa-259">音訊會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="397aa-260">影片限制</span><span class="sxs-lookup"><span data-stu-id="397aa-260">Video Limit</span></span></th>
    <th><span data-ttu-id="397aa-261">影片會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="397aa-262">網</span><span class="sxs-lookup"><span data-stu-id="397aa-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="397aa-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="397aa-264">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-265">5,000</span><span class="sxs-lookup"><span data-stu-id="397aa-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-266">2000</span><span class="sxs-lookup"><span data-stu-id="397aa-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-267">175</span><span class="sxs-lookup"><span data-stu-id="397aa-267">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-268">1400</span><span class="sxs-lookup"><span data-stu-id="397aa-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="397aa-269">700</span><span class="sxs-lookup"><span data-stu-id="397aa-269">700</span></span></p></td>
    <td><p><span data-ttu-id="397aa-270">172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="397aa-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-271">Reno</span><span class="sxs-lookup"><span data-stu-id="397aa-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="397aa-272">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-273">10000</span><span class="sxs-lookup"><span data-stu-id="397aa-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-274">4000</span><span class="sxs-lookup"><span data-stu-id="397aa-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-275">175</span><span class="sxs-lookup"><span data-stu-id="397aa-275">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-276">2800</span><span class="sxs-lookup"><span data-stu-id="397aa-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="397aa-277">700</span><span class="sxs-lookup"><span data-stu-id="397aa-277">700</span></span></p></td>
    <td><p><span data-ttu-id="397aa-278">157.57.210.0/23，172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="397aa-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-279">至今波特蘭</span><span class="sxs-lookup"><span data-stu-id="397aa-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="397aa-280">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-281">5,000</span><span class="sxs-lookup"><span data-stu-id="397aa-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-282">4000</span><span class="sxs-lookup"><span data-stu-id="397aa-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-283">175</span><span class="sxs-lookup"><span data-stu-id="397aa-283">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-284">2800</span><span class="sxs-lookup"><span data-stu-id="397aa-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="397aa-285">700</span><span class="sxs-lookup"><span data-stu-id="397aa-285">700</span></span></p></td>
    <td><p><span data-ttu-id="397aa-286">172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="397aa-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-287">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="397aa-288">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-289">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-290">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-291">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-292">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-293">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-294">172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="397aa-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-295">北京</span><span class="sxs-lookup"><span data-stu-id="397aa-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="397aa-296">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-297">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-298">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-299">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-300">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-301">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-302">157.57.211.0/23，172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="397aa-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-303">底特律</span><span class="sxs-lookup"><span data-stu-id="397aa-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="397aa-304">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-305">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-306">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-307">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-308">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-309">（無限制）</span><span class="sxs-lookup"><span data-stu-id="397aa-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="397aa-310">172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="397aa-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="397aa-311">在 Lync Server 通話許可控制中，網路區域之間的連線稱為*區域連結*。</span><span class="sxs-lookup"><span data-stu-id="397aa-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="397aa-312">針對每個區域連結，請決定下列專案，就像您針對網路網站所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="397aa-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="397aa-313">您想要針對所有併發音訊會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="397aa-314">如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-315">您想要為每個個別音訊會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-315">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="397aa-316">預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-316">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="397aa-317">您想要針對所有併發影片會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="397aa-318">如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-319">您想要為每個個別的影片會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-319">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="397aa-320">預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-320">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="397aa-321">**具有相關頻寬限制的網路區域連結**</span><span class="sxs-lookup"><span data-stu-id="397aa-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="397aa-322">![三個地區之間的限制範例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "三個地區之間的限制範例")</span><span class="sxs-lookup"><span data-stu-id="397aa-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="397aa-323">地區連結頻寬資訊（頻寬以 kbps 為單位）</span><span class="sxs-lookup"><span data-stu-id="397aa-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-324">地區連結名稱</span><span class="sxs-lookup"><span data-stu-id="397aa-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="397aa-325">第一個區域</span><span class="sxs-lookup"><span data-stu-id="397aa-325">First Region</span></span></th>
    <th><span data-ttu-id="397aa-326">第二個區域</span><span class="sxs-lookup"><span data-stu-id="397aa-326">Second Region</span></span></th>
    <th><span data-ttu-id="397aa-327">BW 限制</span><span class="sxs-lookup"><span data-stu-id="397aa-327">BW Limit</span></span></th>
    <th><span data-ttu-id="397aa-328">音訊限制</span><span class="sxs-lookup"><span data-stu-id="397aa-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="397aa-329">音訊會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="397aa-330">影片限制</span><span class="sxs-lookup"><span data-stu-id="397aa-330">Video Limit</span></span></th>
    <th><span data-ttu-id="397aa-331">影片會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-332">NA-EMEA-連結</span><span class="sxs-lookup"><span data-stu-id="397aa-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="397aa-333">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-334">中東</span><span class="sxs-lookup"><span data-stu-id="397aa-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="397aa-335">50000</span><span class="sxs-lookup"><span data-stu-id="397aa-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-336">20000</span><span class="sxs-lookup"><span data-stu-id="397aa-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-337">175</span><span class="sxs-lookup"><span data-stu-id="397aa-337">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-338">14000</span><span class="sxs-lookup"><span data-stu-id="397aa-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-339">700</span><span class="sxs-lookup"><span data-stu-id="397aa-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-340">EMEA-APAC-連結</span><span class="sxs-lookup"><span data-stu-id="397aa-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="397aa-341">中東</span><span class="sxs-lookup"><span data-stu-id="397aa-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="397aa-342">APAC</span><span class="sxs-lookup"><span data-stu-id="397aa-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="397aa-343">25000</span><span class="sxs-lookup"><span data-stu-id="397aa-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-344">10000</span><span class="sxs-lookup"><span data-stu-id="397aa-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-345">175</span><span class="sxs-lookup"><span data-stu-id="397aa-345">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-346">7000</span><span class="sxs-lookup"><span data-stu-id="397aa-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-347">700</span><span class="sxs-lookup"><span data-stu-id="397aa-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="397aa-348">在每一組網路區域之間定義路由。</span><span class="sxs-lookup"><span data-stu-id="397aa-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="397aa-349">北美與 APAC 區域之間的路線需要兩個連結，因為沒有直接連接它們的區域連結。</span><span class="sxs-lookup"><span data-stu-id="397aa-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="397aa-350">地區路線</span><span class="sxs-lookup"><span data-stu-id="397aa-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-351">地區路線名稱</span><span class="sxs-lookup"><span data-stu-id="397aa-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="397aa-352">第一個區域</span><span class="sxs-lookup"><span data-stu-id="397aa-352">First Region</span></span></th>
    <th><span data-ttu-id="397aa-353">第二個區域</span><span class="sxs-lookup"><span data-stu-id="397aa-353">Second Region</span></span></th>
    <th><span data-ttu-id="397aa-354">區域連結</span><span class="sxs-lookup"><span data-stu-id="397aa-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-355">NA-EMEA-路線</span><span class="sxs-lookup"><span data-stu-id="397aa-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="397aa-356">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-357">中東</span><span class="sxs-lookup"><span data-stu-id="397aa-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="397aa-358">NA-EMEA-連結</span><span class="sxs-lookup"><span data-stu-id="397aa-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="397aa-359">EMEA-APAC-路線</span><span class="sxs-lookup"><span data-stu-id="397aa-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="397aa-360">中東</span><span class="sxs-lookup"><span data-stu-id="397aa-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="397aa-361">APAC</span><span class="sxs-lookup"><span data-stu-id="397aa-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="397aa-362">EMEA-APAC-連結</span><span class="sxs-lookup"><span data-stu-id="397aa-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-363">NA-APAC-路由</span><span class="sxs-lookup"><span data-stu-id="397aa-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="397aa-364">北美洲</span><span class="sxs-lookup"><span data-stu-id="397aa-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="397aa-365">APAC</span><span class="sxs-lookup"><span data-stu-id="397aa-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="397aa-366">NA-EMEA-連結，EMEA-APAC-連結</span><span class="sxs-lookup"><span data-stu-id="397aa-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="397aa-367">針對直接透過單一連結（稱為「*站間*連結」）連線的每一組網路網站，決定下列事項：</span><span class="sxs-lookup"><span data-stu-id="397aa-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="397aa-368">您想要針對所有併發音訊會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="397aa-369">如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-370">您想要為每個個別音訊會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-370">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="397aa-371">預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-371">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="397aa-372">您想要針對所有併發影片會話設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="397aa-373">如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。</span><span class="sxs-lookup"><span data-stu-id="397aa-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="397aa-374">您想要為每個個別的影片會話設定的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="397aa-374">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="397aa-375">預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。</span><span class="sxs-lookup"><span data-stu-id="397aa-375">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="397aa-376">**[CAC 網路區域北美] 顯示在 Reno 和 Albuquerque 之間的網站間連結的頻寬容量和頻寬限制**</span><span class="sxs-lookup"><span data-stu-id="397aa-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="397aa-377">![受 WAN 頻寬限制的網路站台範例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "受 WAN 頻寬限制的網路站台範例")</span><span class="sxs-lookup"><span data-stu-id="397aa-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="397aa-378">兩個網路網站之間的站間連結頻寬資訊（頻寬以 kbps 為單位）</span><span class="sxs-lookup"><span data-stu-id="397aa-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="397aa-379">網站間連結名稱</span><span class="sxs-lookup"><span data-stu-id="397aa-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="397aa-380">第一個網站</span><span class="sxs-lookup"><span data-stu-id="397aa-380">First Site</span></span></th>
    <th><span data-ttu-id="397aa-381">第二個網站</span><span class="sxs-lookup"><span data-stu-id="397aa-381">Second Site</span></span></th>
    <th><span data-ttu-id="397aa-382">BW 限制</span><span class="sxs-lookup"><span data-stu-id="397aa-382">BW Limit</span></span></th>
    <th><span data-ttu-id="397aa-383">音訊限制</span><span class="sxs-lookup"><span data-stu-id="397aa-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="397aa-384">音訊會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="397aa-385">影片限制</span><span class="sxs-lookup"><span data-stu-id="397aa-385">Video Limit</span></span></th>
    <th><span data-ttu-id="397aa-386">影片會話限制</span><span class="sxs-lookup"><span data-stu-id="397aa-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="397aa-387">Reno-Albu-站間連結</span><span class="sxs-lookup"><span data-stu-id="397aa-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="397aa-388">Reno</span><span class="sxs-lookup"><span data-stu-id="397aa-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="397aa-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="397aa-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="397aa-390">20000</span><span class="sxs-lookup"><span data-stu-id="397aa-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-391">12000</span><span class="sxs-lookup"><span data-stu-id="397aa-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-392">175</span><span class="sxs-lookup"><span data-stu-id="397aa-392">175</span></span></p></td>
    <td><p><span data-ttu-id="397aa-393">5,000</span><span class="sxs-lookup"><span data-stu-id="397aa-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="397aa-394">700</span><span class="sxs-lookup"><span data-stu-id="397aa-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="397aa-395">後續步驟</span><span class="sxs-lookup"><span data-stu-id="397aa-395">Next Steps</span></span>

<span data-ttu-id="397aa-396">收集必要資訊之後，您可以使用 Lync Server 管理命令介面或 Lync Server 控制台來執行 CAC 部署。</span><span class="sxs-lookup"><span data-stu-id="397aa-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="397aa-397">雖然您可以使用 Lync Server [控制台] 執行大部分網路設定工作，但若要建立子網和網站間連結，您必須使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="397aa-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="397aa-398">如需詳細資訊，請參閱適用于<STRONG>CsNetworkSubnet</STRONG> Cmdlet 和<STRONG>CsNetworkIntersitePolicy</STRONG> Cmdlet 的 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="397aa-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

