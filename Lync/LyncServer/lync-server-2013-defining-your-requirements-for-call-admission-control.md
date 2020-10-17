---
title: Lync Server 2013：定義通話許可控制需求
description: Lync Server 2013：定義通話許可控制的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545419"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="9e7fc-103">在 Lync Server 2013 中定義通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="9e7fc-103">Defining your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e7fc-104">_**主題上次修改日期：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="9e7fc-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="9e7fc-p101">規劃通話許可控制 (CAC) 時，需要您的企業網路拓撲詳細資訊。為了協助規劃您的通話許可控制原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="9e7fc-107">識別企業網路內的集線器或骨幹 (稱為 *「網路地區」*)。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-107">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="9e7fc-108">識別每個網路地區內的辦公室或位置 (稱為 *「網站」*)。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-108">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="9e7fc-109">判斷每一組網路地區之間的網路路由。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-109">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="9e7fc-110">判斷每個 WAN 連結的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-110">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e7fc-111">頻寬限制是指 WAN 連結上的多少頻寬已分配給企業語音和音訊/視頻流量。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-111">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="9e7fc-112">因此，若有某個 WAN 連結有「頻寬限制」，代表該 WAN 連結的頻寬限制低於透過該連結傳送的預期尖峰流量。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-112">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="9e7fc-113">識別指派給每個網路網站的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-113">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="9e7fc-114">為方便各位了解這些概念，我們將以下圖中的網路拓撲為範例加以說明。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-114">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="9e7fc-115">**通話許可控制範例拓撲**</span><span class="sxs-lookup"><span data-stu-id="9e7fc-115">**Example topology for call admission control**</span></span>

<span data-ttu-id="9e7fc-116">![Litware Inc. 網路拓朴範例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 網路拓朴範例")</span><span class="sxs-lookup"><span data-stu-id="9e7fc-116">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7fc-p103">所有網站都與網路地區有關聯。例如，波特蘭、雷諾與阿布奎基都包含在北美洲地區內。本圖只顯示已套用 CAC 原則且具有頻寬限制的 WAN 連結。包含芝加哥、紐約與底特律的網站會顯示在北美洲地區內，而且由於這幾個網站沒有頻寬限制，因此不需要 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="9e7fc-121">以下各節將說明此範例拓撲的各個元件。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-121">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="9e7fc-122">如需有關如何規劃此拓撲的詳細資訊，包括頻寬限制，請參閱 [範例：在 Lync Server 2013 中收集通話許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-122">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="9e7fc-123">識別網路地區</span><span class="sxs-lookup"><span data-stu-id="9e7fc-123">Identify Network Regions</span></span>

<span data-ttu-id="9e7fc-124">網路地區可代表網路骨幹或網路中樞。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-124">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="9e7fc-p105">網路骨幹或集線器是電腦網路基礎結構的一環，可將不同的網路部分互相連結在一起，為不同的 LAN 或子網路提供資訊交換途徑。骨幹可以將小區域內的不同網路連結起來，成為範圍廣泛的區域。骨幹的傳輸能力通常比與其連結的所有網路還要大。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="9e7fc-p106">此處的範例拓撲具有三個網路地區：北美地區、EMEA 與 APAC。網路地區包含許多網站 (請參閱本主題稍後有關網站的定義)。請與您的網路作業團隊合作，一同識別您的網路地區。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="9e7fc-131">關聯中央網站與個別網路地區</span><span class="sxs-lookup"><span data-stu-id="9e7fc-131">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="9e7fc-132">CAC 需要為每個網路地區定義 Lync Server 中央網站。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-132">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="9e7fc-133">中央網站係以與該網路地區內所有其他網站相較之下，具有最佳網路連線和最高頻寬作為選擇依據。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-133">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="9e7fc-134">先前的範例網路拓撲顯示三個網路地區，每一個都具備中央網站以負責管理 CAC 決策。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-134">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="9e7fc-135">下表顯示先前範例中適當的關聯關係。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-135">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7fc-136">中央網站不一定會對應至網路網站。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-136">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="9e7fc-137">在本檔的範例中，有些中央網站（芝加哥、倫敦及北京）與網站共用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-137">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="9e7fc-138">不過，即使中央網站與網路網站共用相同名稱，中央網站還是 Lync Server 拓撲的元素，而網路網站是 Lync Server 拓撲所在整體網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-138">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="9e7fc-139">網路地區、中央網站與網路網站</span><span class="sxs-lookup"><span data-stu-id="9e7fc-139">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e7fc-140">網路地區</span><span class="sxs-lookup"><span data-stu-id="9e7fc-140">Network Region</span></span></th>
<th><span data-ttu-id="9e7fc-141">中央網站</span><span class="sxs-lookup"><span data-stu-id="9e7fc-141">Central Site</span></span></th>
<th><span data-ttu-id="9e7fc-142">網路網站</span><span class="sxs-lookup"><span data-stu-id="9e7fc-142">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-143">北美地區</span><span class="sxs-lookup"><span data-stu-id="9e7fc-143">North America</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="9e7fc-144">Chicago</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-145">Chicago</span><span class="sxs-lookup"><span data-stu-id="9e7fc-145">Chicago</span></span></p>
<p><span data-ttu-id="9e7fc-146">紐約</span><span class="sxs-lookup"><span data-stu-id="9e7fc-146">New York</span></span></p>
<p><span data-ttu-id="9e7fc-147">底特律</span><span class="sxs-lookup"><span data-stu-id="9e7fc-147">Detroit</span></span></p>
<p><span data-ttu-id="9e7fc-148">波特蘭</span><span class="sxs-lookup"><span data-stu-id="9e7fc-148">Portland</span></span></p>
<p><span data-ttu-id="9e7fc-149">雷諾</span><span class="sxs-lookup"><span data-stu-id="9e7fc-149">Reno</span></span></p>
<p><span data-ttu-id="9e7fc-150">阿爾伯克爾基</span><span class="sxs-lookup"><span data-stu-id="9e7fc-150">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-151">Emea</span><span class="sxs-lookup"><span data-stu-id="9e7fc-151">EMEA</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-152">倫敦</span><span class="sxs-lookup"><span data-stu-id="9e7fc-152">London</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-153">倫敦</span><span class="sxs-lookup"><span data-stu-id="9e7fc-153">London</span></span></p>
<p><span data-ttu-id="9e7fc-154">科隆</span><span class="sxs-lookup"><span data-stu-id="9e7fc-154">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-155">亞太</span><span class="sxs-lookup"><span data-stu-id="9e7fc-155">APAC</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-156">北京</span><span class="sxs-lookup"><span data-stu-id="9e7fc-156">Beijing</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-157">北京</span><span class="sxs-lookup"><span data-stu-id="9e7fc-157">Beijing</span></span></p>
<p><span data-ttu-id="9e7fc-158">馬尼拉</span><span class="sxs-lookup"><span data-stu-id="9e7fc-158">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="9e7fc-159">識別網路網站</span><span class="sxs-lookup"><span data-stu-id="9e7fc-159">Identify Network Sites</span></span>

<span data-ttu-id="9e7fc-p109">網站代表您的組織在這個位置擁有實體場地 (例如辦公室、一群建築物或是一座校園)。具有 LAN 以及與其他網站有 WAN 連線的實體場地就視為網站。請先由清點組織內的所有辦公室開始。在我們的範例拓撲裡，北美洲網路地區包含下列網站：紐約、芝加哥、底特律、波特蘭、雷諾與阿布奎基。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="9e7fc-p110">您必須建立每個網站與網路地區的關聯。頻寬原則與網站的關聯，取決於網站是否具備有限的 WAN 連結而定。如需有關 CAC 原則與使用這些原則來分配頻寬的詳細資訊，請參閱本主題稍後的＜定義頻寬原則＞。若要設定 CAC，首先請建立網站與網路地區的關聯，然後建立頻寬分配原則以套用至特定網站或地區之間受到頻寬限制的所有連線，以及網站與地區之間的所有 WAN 連線。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="9e7fc-168">識別網路連結</span><span class="sxs-lookup"><span data-stu-id="9e7fc-168">Identify Network Links</span></span>

<span data-ttu-id="9e7fc-p111">網路連結代表可連結不同地區與網站的實體 WAN 連線。在我們的範例拓撲中，共有兩個區域網路連結，各區域與網站之間有五個網路連結，而兩個網站之間又有一個網路連結。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="9e7fc-171">兩個區域連結分別位於北美洲與 EMEA 之間 (以 NA-EMEA-LINK 代表)，以及 APAC 與 EMEA 之間 (以 EMEA-APAC-LINK 代表)。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-171">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="9e7fc-p112">在波特蘭、雷諾與阿布奎基至北美洲地區之間，馬尼拉至 APAC 地域之間，以及科隆至 EMEA 地區之間，會用線條連結，代表網站連結。雷諾與阿布奎基之間的線條顯示這兩個網站之間有直接的網路連結。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="9e7fc-174">定義頻寬原則</span><span class="sxs-lookup"><span data-stu-id="9e7fc-174">Define Bandwidth Policies</span></span>

<span data-ttu-id="9e7fc-p113">請與您的網路作業團隊合作，決定組織內所有 WAN 連結之間的即時音訊與視訊流量可用的 WAN 頻寬大小。當頻寬使用量受到限制，亦即當預期頻寬使用量高出分配給音訊與視訊形式的頻寬大小時，通常會在 WAN 連結上套用頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="9e7fc-p114">CAC *「頻寬原則」* 定義可保留給即時音訊與視訊形式的最大頻寬。由於 CAC 未限制其他流量的頻寬，因此無法防止其他資料流量 (例如大型檔案傳輸、音樂串流等等) 用完所有的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="9e7fc-179">CAC 頻寬原則可定義下列任一或所有項目：</span><span class="sxs-lookup"><span data-stu-id="9e7fc-179">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="9e7fc-180">分配給音訊的最大總頻寬。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-180">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="9e7fc-181">分配給視訊的最大總頻寬。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-181">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="9e7fc-182">分配給單一音訊通話 (工作階段) 的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-182">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="9e7fc-183">分配給單一視訊通話 (工作階段) 的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-183">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7fc-184">所有的 CAC 頻寬值都代表最大的<EM>單向</EM>頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-184">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9e7fc-185">Lync Server 2013 語音原則功能可讓使用者在來電時，將來電的頻寬原則檢查功能覆寫至使用者 (，而不是用於使用者) 所撥打的撥出電話。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-185">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="9e7fc-186">工作階段建立完畢後，便可準確地計算頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-186">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="9e7fc-187">為順利做出適宜的通話許可控制決策，請勿頻繁使用此設定，能不用就不用。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-187">This setting should be used sparingly.</span></span> <span data-ttu-id="9e7fc-188">如需詳細資訊，請參閱部署檔中的在 lync server <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">2013 中建立語音原則和設定 pstn 使用方式記錄</A> 或 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">修改語音原則，以及在 lync server 2013 中設定 pstn 使用方式記錄</A> 。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-188">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="9e7fc-p116">若要最佳化個別工作階段的頻寬使用，請斟酌要使用的音訊與視訊轉碼器類型。具體地說，請避免分配過少的頻寬給預期將頻繁使用的轉碼器。相反地，如果您想要防止媒體使用會消耗大量頻寬的轉碼器，請儘可能將每個工作階段的最大頻寬設為最小值以抑制此類用途。對音訊而言，並非每一種情況都有可用的轉碼器。例如：</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="9e7fc-194">當您考慮編解碼器的頻寬和優先順序時，Lync 端點之間的對等音訊通話會使用 RTAudio (8kHz) 或 RTAudio (16kHz) 。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-194">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="9e7fc-195">Lync 端點和 A/V 會議服務之間的電話會議會使用 g.722 或 Siren。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-195">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="9e7fc-196">撥打給公用交換電話網路 (PSTN) 或從 Lync 端點撥打的電話，將會使用 g.711 或 RTAudio (8kHz) 。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-196">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="9e7fc-197">使用下表有助於最佳化每個工作階段的最大頻寬設定。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-197">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="9e7fc-198">依轉碼器的頻寬使用</span><span class="sxs-lookup"><span data-stu-id="9e7fc-198">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e7fc-199">轉碼器</span><span class="sxs-lookup"><span data-stu-id="9e7fc-199">Codec</span></span></th>
<th><span data-ttu-id="9e7fc-200">不含正向錯誤修正 (FEC) 功能的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="9e7fc-200">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="9e7fc-201">含正向錯誤修正 (FEC) 功能的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="9e7fc-201">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-202">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-202">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-203">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-203">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-204">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-204">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-205">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-205">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-206">67 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-206">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-207">96 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-207">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-208">警笛</span><span class="sxs-lookup"><span data-stu-id="9e7fc-208">Siren</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-209">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-209">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-210">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-210">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-211">G. g.711</span><span class="sxs-lookup"><span data-stu-id="9e7fc-211">G.711</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-212">102 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-212">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-213">166 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-213">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-214">G. g.722</span><span class="sxs-lookup"><span data-stu-id="9e7fc-214">G.722</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-215">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-215">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-216">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-216">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-217">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-217">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-218">260 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-218">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-219">不適用</span><span class="sxs-lookup"><span data-stu-id="9e7fc-219">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-220">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-220">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-221">610 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-221">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-222">不適用</span><span class="sxs-lookup"><span data-stu-id="9e7fc-222">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9e7fc-p117">頻寬需求需考量下列各項的負荷：Ethernet II、IP、使用者資料包通訊協定 (UDP)、RTP (即時傳輸通訊協定) 與 SRTP (安全即時傳輸通訊協定)。這些需求同時包含 10 kbps 的 RTCP 負荷。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="9e7fc-225">雖然 G.722.1 與 Siren 轉碼器很相近，但其位元速率卻不相同。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-225">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="9e7fc-226">G.722 （Lync Server 會議的預設編解碼器）與722.1 和 Siren 編解碼器完全不同。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-226">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="9e7fc-227">在下列情況下，Lync Server 會使用 Siren 編解碼器：</span><span class="sxs-lookup"><span data-stu-id="9e7fc-227">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="9e7fc-228">當頻寬原則設得太低，以致於無法使用 G.722 時。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-228">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="9e7fc-229">如果通訊伺服器2007或通訊伺服器 2007 R2 用戶端連接至 Lync Server 會議服務， (因為這些用戶端不支援 g.722 編解碼器) 。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-229">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="9e7fc-230">依案例的頻寬使用</span><span class="sxs-lookup"><span data-stu-id="9e7fc-230">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e7fc-231">案例</span><span class="sxs-lookup"><span data-stu-id="9e7fc-231">Scenario</span></span></th>
<th><span data-ttu-id="9e7fc-232">數量最佳化的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-232">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="9e7fc-233">平衡模式下的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-233">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="9e7fc-234">品質最佳化的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="9e7fc-234">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-235">對等音訊通話</span><span class="sxs-lookup"><span data-stu-id="9e7fc-235">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-236">45 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-236">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-237">62 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-237">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-238">91 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-238">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-239">電話會議</span><span class="sxs-lookup"><span data-stu-id="9e7fc-239">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-240">53 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-240">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-241">101 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-241">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-242">165 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-242">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-243">在 Lync 2013 與 PSTN 閘道之間的 PSTN 通話 (，具有媒體旁路) </span><span class="sxs-lookup"><span data-stu-id="9e7fc-243">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-245">97 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-245">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-246">161 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-246">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-247">在 Lync 2013 和轉送伺服器之間 (PSTN 通話，但沒有媒體旁路) </span><span class="sxs-lookup"><span data-stu-id="9e7fc-247">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-248">45 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-248">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-249">97 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-249">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-250">161 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-250">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e7fc-251">PSTN 通話 (轉送伺服器和 PSTN 閘道之間，未使用媒體旁路) </span><span class="sxs-lookup"><span data-stu-id="9e7fc-251">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-253">97 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-253">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-254">161 kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-254">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e7fc-255">Lync-Polycom 通話</span><span class="sxs-lookup"><span data-stu-id="9e7fc-255">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-257">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="9e7fc-258">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="9e7fc-258">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="9e7fc-259">識別 IP 子網路</span><span class="sxs-lookup"><span data-stu-id="9e7fc-259">Identify IP Subnets</span></span>

<span data-ttu-id="9e7fc-p118">對於每一個網路網站，您需要和網路管理員一同決定要指派給每一個網路網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網路網站的 IP 子網路，您的工作將會大幅簡化。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="9e7fc-p119">在我們的範例中，將指派以下 IP 子網路給北美洲地區內的紐約網站：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。假設原本在底特律上班的 Bob 必須出差到紐約辦公室接受訓練課程。當他開啟自己的電腦並連線至網路時，他的電腦會取得保留給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9e7fc-265">在伺服器上的網路設定期間指定的 IP 子網必須符合用戶端電腦提供的格式，才能正確用於媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-265">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="9e7fc-266">Lync 用戶端會採用其本機 IP 位址，並以關聯的子網路遮罩遮罩 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-266">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="9e7fc-267">決定與每個用戶端相關聯的旁路識別碼時，註冊機構會比較與用戶端所提供之子網相關聯的 IP 子網清單，以完全符合。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-267">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="9e7fc-268">因此，在伺服器上的網路設定期間輸入的子網，必須是實際的子網，而不是虛擬子網，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-268">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="9e7fc-269"> (如果您部署通話許可控制，但沒有媒體旁路，則即使您設定虛擬子網，通話許可控制也會正常運作。 ) </span><span class="sxs-lookup"><span data-stu-id="9e7fc-269">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="9e7fc-270">例如，如果用戶端登入的 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦，Lync 2013 會要求與子網172.29.81.0 相關聯的旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-270">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="9e7fc-271">如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="9e7fc-271">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="9e7fc-272">因此，管理員必須嚴格依照 Lync 用戶端所提供的方式輸入子網， (在設定網路設定（靜態或透過 DHCP）時，管理員必須輸入子網。 ) </span><span class="sxs-lookup"><span data-stu-id="9e7fc-272">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

