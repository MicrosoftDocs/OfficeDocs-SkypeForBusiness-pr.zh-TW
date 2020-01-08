---
title: Lync Server 2013：定義通話許可控制需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="60d4f-102">在 Lync Server 2013 中定義通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="60d4f-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60d4f-103">_**主題上次修改日期：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="60d4f-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="60d4f-104">規劃通話許可控制（CAC）需要有關商業網路拓朴的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="60d4f-104">Planning for call admission control (CAC) requires detailed information about your enterprise network topology.</span></span> <span data-ttu-id="60d4f-105">若要協助規劃您的通話許可控制原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="60d4f-105">To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="60d4f-106">在商業網路中找出中樞/backbones （稱為*網路區域*）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="60d4f-107">找出每個網路區域內的辦公室或位置（稱為「*網路」網站*）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="60d4f-108">判斷每一組網路區域之間的網路路線。</span><span class="sxs-lookup"><span data-stu-id="60d4f-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="60d4f-109">判斷每個 WAN 連結的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="60d4f-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="60d4f-110">頻寬限制是指 WAN 連結上的頻寬數已指派給企業語音及音訊/視頻流量。</span><span class="sxs-lookup"><span data-stu-id="60d4f-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="60d4f-111">當 WAN 連結被描述為「頻寬受限制」時，WAN 連結的頻寬限制低於連結的預期峰值流量。</span><span class="sxs-lookup"><span data-stu-id="60d4f-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="60d4f-112">找出指派給每個網路網站的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="60d4f-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="60d4f-113">為了說明這些概念，我們將使用下列圖中所示的範例網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="60d4f-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="60d4f-114">**通話許可控制的範例拓撲**</span><span class="sxs-lookup"><span data-stu-id="60d4f-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="60d4f-115">![Litware inc. 網路拓朴範例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.. 網路拓朴範例")</span><span class="sxs-lookup"><span data-stu-id="60d4f-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60d4f-116">所有網路網站都與一個網路區域相關聯。</span><span class="sxs-lookup"><span data-stu-id="60d4f-116">All network sites are associated with a network region.</span></span> <span data-ttu-id="60d4f-117">例如，[上海]、[Reno] 和 [Albuquerque] 都包含在北美洲的地區。</span><span class="sxs-lookup"><span data-stu-id="60d4f-117">For example, Portland, Reno, and Albuquerque are included in the North America region.</span></span> <span data-ttu-id="60d4f-118">在此圖中，只會顯示已套用 CAC 原則的 WAN 連結，且具有頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="60d4f-118">In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits.</span></span> <span data-ttu-id="60d4f-119">芝加哥、北京及底特律的網路網站會顯示在北美地區橢圓內，因為它們不會受到頻寬限制，因此不需要 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="60d4f-119">The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="60d4f-120">以下各節將說明這個範例的元件。</span><span class="sxs-lookup"><span data-stu-id="60d4f-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="60d4f-121">如需有關如何規劃此拓朴的詳細資料，包括頻寬限制，請參閱[範例：在 Lync Server 2013 中收集您的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="60d4f-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="60d4f-122">識別網路區域</span><span class="sxs-lookup"><span data-stu-id="60d4f-122">Identify Network Regions</span></span>

<span data-ttu-id="60d4f-123">網路區域代表網路骨幹或網路中樞。</span><span class="sxs-lookup"><span data-stu-id="60d4f-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="60d4f-124">網路骨幹或中樞是電腦網路基礎結構的一部分，可互連網路的不同部分，提供不同局域網或子網之間資訊交換的路徑。</span><span class="sxs-lookup"><span data-stu-id="60d4f-124">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="60d4f-125">中樞可將許多不同的網路從較小的位置連到廣域的地理區域。</span><span class="sxs-lookup"><span data-stu-id="60d4f-125">A backbone can tie together diverse networks from a small location to a wide geographic area.</span></span> <span data-ttu-id="60d4f-126">中樞的容量通常比連接至它的網路的容量還大。</span><span class="sxs-lookup"><span data-stu-id="60d4f-126">The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="60d4f-127">我們的範例拓朴有三個網路區域：北美、EMEA 及 APAC。</span><span class="sxs-lookup"><span data-stu-id="60d4f-127">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="60d4f-128">網路區域包含網路網站的集合（請參閱本主題稍後的網路網站定義）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-128">A network region contains a collection of network sites (see the definition of network sites later in this topic).</span></span> <span data-ttu-id="60d4f-129">與您的網路操作小組合作，找出您的網路區域。</span><span class="sxs-lookup"><span data-stu-id="60d4f-129">Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="60d4f-130">將中央網站與每個網路區域建立關聯</span><span class="sxs-lookup"><span data-stu-id="60d4f-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="60d4f-131">CAC 需要為每個網路區域定義 Lync Server 中心網站。</span><span class="sxs-lookup"><span data-stu-id="60d4f-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="60d4f-132">已選取中央網站，具有最佳的網路連線能力，以及該網路區域中所有其他網站的最高頻寬。</span><span class="sxs-lookup"><span data-stu-id="60d4f-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="60d4f-133">上述網路拓朴範例顯示三個網路區域，每個區域都有一個可管理 CAC 決策的中央網站。</span><span class="sxs-lookup"><span data-stu-id="60d4f-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="60d4f-134">在上述範例中，下表顯示適當的關聯。</span><span class="sxs-lookup"><span data-stu-id="60d4f-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60d4f-135">中央網站並不一定要與網路網站相對應。</span><span class="sxs-lookup"><span data-stu-id="60d4f-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="60d4f-136">在本檔的範例中，有些中央網站（芝加哥、倫敦及北京）與網路網站共用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="60d4f-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="60d4f-137">不過，即使中央網站和網路網站共用相同的名稱，中央網站還是 Lync Server 拓撲結構的元素，而網路網站是 Lync 伺服器拓撲結構所駐留之整個網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="60d4f-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="60d4f-138">網路區域、中央網站和網路網站</span><span class="sxs-lookup"><span data-stu-id="60d4f-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60d4f-139">網路區域</span><span class="sxs-lookup"><span data-stu-id="60d4f-139">Network Region</span></span></th>
<th><span data-ttu-id="60d4f-140">中央網站</span><span class="sxs-lookup"><span data-stu-id="60d4f-140">Central Site</span></span></th>
<th><span data-ttu-id="60d4f-141">網路網站</span><span class="sxs-lookup"><span data-stu-id="60d4f-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-142">北美洲</span><span class="sxs-lookup"><span data-stu-id="60d4f-142">North America</span></span></p></td>
<td><p><span data-ttu-id="60d4f-143">北京</span><span class="sxs-lookup"><span data-stu-id="60d4f-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="60d4f-144">北京</span><span class="sxs-lookup"><span data-stu-id="60d4f-144">Chicago</span></span></p>
<p><span data-ttu-id="60d4f-145">北京</span><span class="sxs-lookup"><span data-stu-id="60d4f-145">New York</span></span></p>
<p><span data-ttu-id="60d4f-146">底特律</span><span class="sxs-lookup"><span data-stu-id="60d4f-146">Detroit</span></span></p>
<p><span data-ttu-id="60d4f-147">至今波特蘭</span><span class="sxs-lookup"><span data-stu-id="60d4f-147">Portland</span></span></p>
<p><span data-ttu-id="60d4f-148">Reno</span><span class="sxs-lookup"><span data-stu-id="60d4f-148">Reno</span></span></p>
<p><span data-ttu-id="60d4f-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="60d4f-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-150">中東</span><span class="sxs-lookup"><span data-stu-id="60d4f-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="60d4f-151">位於</span><span class="sxs-lookup"><span data-stu-id="60d4f-151">London</span></span></p></td>
<td><p><span data-ttu-id="60d4f-152">位於</span><span class="sxs-lookup"><span data-stu-id="60d4f-152">London</span></span></p>
<p><span data-ttu-id="60d4f-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="60d4f-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-154">APAC</span><span class="sxs-lookup"><span data-stu-id="60d4f-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="60d4f-155">首都</span><span class="sxs-lookup"><span data-stu-id="60d4f-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="60d4f-156">首都</span><span class="sxs-lookup"><span data-stu-id="60d4f-156">Beijing</span></span></p>
<p><span data-ttu-id="60d4f-157">Manila</span><span class="sxs-lookup"><span data-stu-id="60d4f-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="60d4f-158">識別網路網站</span><span class="sxs-lookup"><span data-stu-id="60d4f-158">Identify Network Sites</span></span>

<span data-ttu-id="60d4f-159">網路網站代表貴組織有實體場所（例如，辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="60d4f-159">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus.</span></span> <span data-ttu-id="60d4f-160">有局域網的物理場所，且與其他網站有 WAN 連線，則被視為網路網站。</span><span class="sxs-lookup"><span data-stu-id="60d4f-160">A physical venue with a LAN and has WAN connectivity to other sites is considered a network site.</span></span> <span data-ttu-id="60d4f-161">首先，清點貴組織的所有辦事處。</span><span class="sxs-lookup"><span data-stu-id="60d4f-161">Start by inventorying all of your organization’s offices.</span></span> <span data-ttu-id="60d4f-162">在我們的範例拓撲中，北美網路區域由下列網路網站組成：紐約、芝加哥、底特律、上海、Reno 和 Albuquerque。</span><span class="sxs-lookup"><span data-stu-id="60d4f-162">In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="60d4f-163">您必須將每個網路網站與網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="60d4f-163">You must associate every network site with a network region.</span></span> <span data-ttu-id="60d4f-164">根據網路網站是否有受限制的 WAN 連結，頻寬原則會與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="60d4f-164">Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site.</span></span> <span data-ttu-id="60d4f-165">如需 CAC 原則的詳細資料，以及使用它們所指派的頻寬，請參閱本主題稍後的「定義頻寬原則」。</span><span class="sxs-lookup"><span data-stu-id="60d4f-165">For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic.</span></span> <span data-ttu-id="60d4f-166">若要設定 CAC，您可以將網路網站與網路區域建立關聯，然後建立頻寬分配原則，以套用到特定網站或區域之間的頻寬限制連接，以及網站與區域之間的 WAN 連線。</span><span class="sxs-lookup"><span data-stu-id="60d4f-166">To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="60d4f-167">識別網路連結</span><span class="sxs-lookup"><span data-stu-id="60d4f-167">Identify Network Links</span></span>

<span data-ttu-id="60d4f-168">網路連結代表連結不同地區和網站之物理 WAN 的連線。</span><span class="sxs-lookup"><span data-stu-id="60d4f-168">Network links represent connections to the physical WAN that links different regions and sites.</span></span> <span data-ttu-id="60d4f-169">在我們的範例拓撲中，有兩個地區網路連結、區域與網站之間有五個網路連結，以及兩個網站之間的一個網路連結。</span><span class="sxs-lookup"><span data-stu-id="60d4f-169">In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="60d4f-170">這兩個地區連結位於北美與 EMEA 之間，表示為 NA-EMEA-APAC 和 EMEA 之間，以 EMEA-APAC 連結表示。</span><span class="sxs-lookup"><span data-stu-id="60d4f-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="60d4f-171">網站連結是由將上海、Reno 和 Albuquerque 連接到北美地區、Manila 至 APAC 地區，以及 Cologne 到 EMEA 地區的線條所表示。</span><span class="sxs-lookup"><span data-stu-id="60d4f-171">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region.</span></span> <span data-ttu-id="60d4f-172">Reno 和 Albuquerque 之間的線條會顯示這兩個網站之間的 [直接網路] 連結。</span><span class="sxs-lookup"><span data-stu-id="60d4f-172">The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="60d4f-173">定義頻寬原則</span><span class="sxs-lookup"><span data-stu-id="60d4f-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="60d4f-174">與您的網路操作小組共同作業，判斷您組織中 WAN 連結的即時音訊與視頻流量有多少 WAN 頻寬可供使用。</span><span class="sxs-lookup"><span data-stu-id="60d4f-174">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization.</span></span> <span data-ttu-id="60d4f-175">如果頻寬使用量受到限制，則頻寬原則通常會套用至 WAN 連結;也就是說，如果預期的頻寬不超過可為音訊和影片形式指派的頻寬。</span><span class="sxs-lookup"><span data-stu-id="60d4f-175">Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="60d4f-176">CAC*頻寬原則*定義可為即時音訊與視頻形式保留的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="60d4f-176">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities.</span></span> <span data-ttu-id="60d4f-177">因為 CAC 不會限制其他流量的頻寬，所以無法從使用所有網路頻寬等其他資料流量（例如大型檔案傳輸、音樂資料流程）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-177">Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="60d4f-178">CAC 頻寬原則可定義下列任一或所有專案：</span><span class="sxs-lookup"><span data-stu-id="60d4f-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="60d4f-179">為音訊指派的總頻寬上限。</span><span class="sxs-lookup"><span data-stu-id="60d4f-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="60d4f-180">為影片指派的總頻寬上限。</span><span class="sxs-lookup"><span data-stu-id="60d4f-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="60d4f-181">針對單一音訊通話（會話）指派的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="60d4f-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="60d4f-182">針對單一視頻通話（會話）所指派的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="60d4f-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60d4f-183">所有的 CAC 頻寬值代表最大的<EM>單向</EM>頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="60d4f-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="60d4f-184">Lync Server 2013 語音原則功能可覆寫撥入來電給使用者的頻寬原則檢查，而不是使用者所發出的撥出電話。</span><span class="sxs-lookup"><span data-stu-id="60d4f-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="60d4f-185">會話建立之後，頻寬佔用將會精確反映。</span><span class="sxs-lookup"><span data-stu-id="60d4f-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="60d4f-186">此設定應該謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="60d4f-186">This setting should be used sparingly.</span></span> <span data-ttu-id="60d4f-187">如需詳細資訊，請參閱在<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013 中建立語音原則和設定 pstn 使用記錄</A>，或修改語音原則，並在 [部署] 檔的<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013 中設定 pstn 使用記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="60d4f-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="60d4f-188">若要針對每個會話優化頻寬利用率，請考慮將使用的音訊和視頻編解碼器類型。</span><span class="sxs-lookup"><span data-stu-id="60d4f-188">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used.</span></span> <span data-ttu-id="60d4f-189">特別是，請不要針對您想要經常使用的編解碼器，將頻寬不足的分配給它。</span><span class="sxs-lookup"><span data-stu-id="60d4f-189">In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently.</span></span> <span data-ttu-id="60d4f-190">相反地，如果您想要防止媒體使用需要更多頻寬的編解碼器，您應該將 [每個會話的最大頻寬] 設定為 [足夠不足] 來避免這種使用。</span><span class="sxs-lookup"><span data-stu-id="60d4f-190">Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use.</span></span> <span data-ttu-id="60d4f-191">對於音訊，並非每個案例都提供每個編解碼器。</span><span class="sxs-lookup"><span data-stu-id="60d4f-191">For audio, not every codec is available for every scenario.</span></span> <span data-ttu-id="60d4f-192">例如：</span><span class="sxs-lookup"><span data-stu-id="60d4f-192">For example:</span></span>

  - <span data-ttu-id="60d4f-193">在 Lync 端點之間進行對等音訊通話時，在您考慮使用 RTAudio （8kHz）或 RTAudio （16kHz）時，會在您考慮編解碼器的頻寬與優先順序。</span><span class="sxs-lookup"><span data-stu-id="60d4f-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="60d4f-194">Lync 端點與 A/V 會議服務之間的會議呼叫將使用722或 Siren。</span><span class="sxs-lookup"><span data-stu-id="60d4f-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="60d4f-195">呼叫或從 Lync 端點撥打電話網絡（PSTN）的呼叫將會使用711或 RTAudio （8kHz）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="60d4f-196">您可以使用下表來協助您優化每個會話的最大頻寬設定。</span><span class="sxs-lookup"><span data-stu-id="60d4f-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="60d4f-197">使用編解碼器的頻寬利用率</span><span class="sxs-lookup"><span data-stu-id="60d4f-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60d4f-198">編碼</span><span class="sxs-lookup"><span data-stu-id="60d4f-198">Codec</span></span></th>
<th><span data-ttu-id="60d4f-199">沒有轉寄錯誤修正的頻寬需求（FEC）</span><span class="sxs-lookup"><span data-stu-id="60d4f-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="60d4f-200">頻寬需求與轉寄錯誤修正（FEC）</span><span class="sxs-lookup"><span data-stu-id="60d4f-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="60d4f-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-202">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-203">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="60d4f-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-207">Siren</span><span class="sxs-lookup"><span data-stu-id="60d4f-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="60d4f-208">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-209">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-210">G. 711</span><span class="sxs-lookup"><span data-stu-id="60d4f-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="60d4f-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-213">G. 722</span><span class="sxs-lookup"><span data-stu-id="60d4f-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="60d4f-214">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-215">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-216">RTVideo （CIF 15 fps）</span><span class="sxs-lookup"><span data-stu-id="60d4f-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-218">不適用</span><span class="sxs-lookup"><span data-stu-id="60d4f-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-219">RTVideo （VGA 30 fps）</span><span class="sxs-lookup"><span data-stu-id="60d4f-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-221">不適用</span><span class="sxs-lookup"><span data-stu-id="60d4f-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="60d4f-222">頻寬需求會考慮下列各項的負荷：乙太網路 II、IP、使用者資料包協定（UDP）、RTP （即時傳輸通訊協定），以及 SRTP （安全的即時傳輸通訊協定）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-222">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol).</span></span> <span data-ttu-id="60d4f-223">它們也包括 10 kbps 的 RTCP 額外負荷。</span><span class="sxs-lookup"><span data-stu-id="60d4f-223">They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="60d4f-224">722.1 和 Siren 編解碼器類似，但它們提供不同的位元速率。</span><span class="sxs-lookup"><span data-stu-id="60d4f-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="60d4f-225">722（Lync Server 會議的預設編解碼器）與722.1 和 Siren 編解碼器完全不同。</span><span class="sxs-lookup"><span data-stu-id="60d4f-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="60d4f-226">在下列情況下，Lync Server 會使用 Siren 編解碼器：</span><span class="sxs-lookup"><span data-stu-id="60d4f-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="60d4f-227">如果頻寬原則設定的722太低，將無法使用。</span><span class="sxs-lookup"><span data-stu-id="60d4f-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="60d4f-228">如果通訊伺服器2007或通訊伺服器 2007 R2 用戶端連接至 Lync Server 會議服務（因為這些用戶端不支援722編解碼器）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="60d4f-229">依案例的頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="60d4f-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60d4f-230">例子</span><span class="sxs-lookup"><span data-stu-id="60d4f-230">Scenario</span></span></th>
<th><span data-ttu-id="60d4f-231">針對數量（kbps）優化的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="60d4f-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="60d4f-232">平衡模式的頻寬需求（kbps）</span><span class="sxs-lookup"><span data-stu-id="60d4f-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="60d4f-233">針對品質優化的頻寬需求（kbps）</span><span class="sxs-lookup"><span data-stu-id="60d4f-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-234">對等音訊通話</span><span class="sxs-lookup"><span data-stu-id="60d4f-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="60d4f-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-238">電話會議</span><span class="sxs-lookup"><span data-stu-id="60d4f-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="60d4f-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-242">PSTN 通話（在 Lync 2013 和 PSTN 閘道之間，有媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="60d4f-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-246">PSTN 通話（在 Lync 2013 和中繼伺服器之間，不使用媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="60d4f-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60d4f-250">PSTN 呼叫（在中繼伺服器與 PSTN 閘道之間，不使用媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="60d4f-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="60d4f-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60d4f-254">Lync-Polycom 通話</span><span class="sxs-lookup"><span data-stu-id="60d4f-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="60d4f-255">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="60d4f-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="60d4f-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="60d4f-258">識別 IP 子網</span><span class="sxs-lookup"><span data-stu-id="60d4f-258">Identify IP Subnets</span></span>

<span data-ttu-id="60d4f-259">針對每個網路網站，您必須與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="60d4f-259">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site.</span></span> <span data-ttu-id="60d4f-260">如果您的網路系統管理員已經將 IP 子網組織到網路區域和網路網站，您的工作會明顯簡化。</span><span class="sxs-lookup"><span data-stu-id="60d4f-260">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="60d4f-261">在我們的範例中，北北美地區的紐約網站會指派下列 IP 子網： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="60d4f-261">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="60d4f-262">假設 Bob 在底特律中的運作方式，是在紐約的辦公室進行訓練。</span><span class="sxs-lookup"><span data-stu-id="60d4f-262">Suppose Bob, who typically works in Detroit, travels to the New York office for training.</span></span> <span data-ttu-id="60d4f-263">當他開啟電腦並聯機到網路時，他的電腦會在為紐約保留的四個範圍其中之一取得 IP 位址，例如172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="60d4f-263">When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="60d4f-264">在伺服器的網路設定期間指定的 IP 子網必須符合用戶端電腦提供的格式，才能正確地用於媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="60d4f-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="60d4f-265">Lync 用戶端會採用其本機 IP 位址，並使用相關聯的子網路遮罩來遮罩 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="60d4f-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="60d4f-266">在判斷與每個用戶端相關的旁路識別碼時，註冊機構會將與各個網路網站相關聯的 IP 子網清單與用戶端提供的子網進行比較，以取得完全相符的專案。</span><span class="sxs-lookup"><span data-stu-id="60d4f-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="60d4f-267">基於這個原因，在伺服器的網路設定期間輸入的子網很重要，而不是虛擬子網。</span><span class="sxs-lookup"><span data-stu-id="60d4f-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="60d4f-268">（如果您部署 [呼叫許可控制]，但無法使用 [媒體旁路]，即使您設定虛擬子網，也能正常使用通話許可控制功能。）</span><span class="sxs-lookup"><span data-stu-id="60d4f-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="60d4f-269">例如，如果用戶端在 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，Lync 2013 會要求與子網172.29.81.0 相關聯的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="60d4f-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="60d4f-270">如果子網是定義為 172.29.0.0/16，雖然用戶端屬於虛擬子網，但註冊機構不會認為這個相符，因為註冊機構特別想要尋找子網172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="60d4f-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="60d4f-271">因此，系統管理員必須完全按照 Lync 用戶端所提供的方式輸入子網，這一點很重要（在靜態或由 DHCP 在網路設定期間由子網提供）。</span><span class="sxs-lookup"><span data-stu-id="60d4f-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

