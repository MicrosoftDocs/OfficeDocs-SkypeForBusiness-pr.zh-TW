---
title: Lync Server 2013： 定義通話許可控制需求
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
ms.openlocfilehash: 6de02e10f884bf35c87ec8147c66bb720ad39c89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e52cc-102">定義 Lync Server 2013 中的 [通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="e52cc-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e52cc-103">_**上次修改主題：** 2013年-10-28_</span><span class="sxs-lookup"><span data-stu-id="e52cc-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="e52cc-p101">規劃通話許可控制 (CAC) 時，需要您的企業網路拓撲詳細資訊。為了協助規劃您的通話許可控制原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="e52cc-106">識別企業網路內的集線器或骨幹 (稱為 *「網路地區」*)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="e52cc-107">識別每個網路地區內的辦公室或位置 (稱為 *「網站」*)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="e52cc-108">判斷每一組網路地區之間的網路路由。</span><span class="sxs-lookup"><span data-stu-id="e52cc-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="e52cc-109">判斷每個 WAN 連結的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e52cc-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e52cc-110">頻寬限制，請參閱在 WAN 連結的頻寬中有多少配置給 Enterprise Voice 和音訊/視訊流量。</span><span class="sxs-lookup"><span data-stu-id="e52cc-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="e52cc-111">因此，若有某個 WAN 連結有「頻寬限制」，代表該 WAN 連結的頻寬限制低於透過該連結傳送的預期尖峰流量。</span><span class="sxs-lookup"><span data-stu-id="e52cc-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="e52cc-112">識別指派給每個網路網站的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="e52cc-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="e52cc-113">為方便各位了解這些概念，我們將以下圖中的網路拓撲為範例加以說明。</span><span class="sxs-lookup"><span data-stu-id="e52cc-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="e52cc-114">**通話許可控制範例拓撲**</span><span class="sxs-lookup"><span data-stu-id="e52cc-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="e52cc-115">![Litware Inc.網路拓撲範例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.網路拓撲範例")</span><span class="sxs-lookup"><span data-stu-id="e52cc-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e52cc-p103">所有網站都與網路地區有關聯。例如，波特蘭、雷諾與阿布奎基都包含在北美洲地區內。本圖只顯示已套用 CAC 原則且具有頻寬限制的 WAN 連結。包含芝加哥、紐約與底特律的網站會顯示在北美洲地區內，而且由於這幾個網站沒有頻寬限制，因此不需要 CAC 原則。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="e52cc-120">以下各節將說明此範例拓撲的各個元件。</span><span class="sxs-lookup"><span data-stu-id="e52cc-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="e52cc-121">如需如何這種拓撲已計劃中，包括頻寬限制的詳細資訊，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="e52cc-122">識別網路地區</span><span class="sxs-lookup"><span data-stu-id="e52cc-122">Identify Network Regions</span></span>

<span data-ttu-id="e52cc-123">網路地區可代表網路骨幹或網路中樞。</span><span class="sxs-lookup"><span data-stu-id="e52cc-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="e52cc-p105">網路骨幹或集線器是電腦網路基礎結構的一環，可將不同的網路部分互相連結在一起，為不同的 LAN 或子網路提供資訊交換途徑。骨幹可以將小區域內的不同網路連結起來，成為範圍廣泛的區域。骨幹的傳輸能力通常比與其連結的所有網路還要大。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="e52cc-p106">此處的範例拓撲具有三個網路地區：北美地區、EMEA 與 APAC。網路地區包含許多網站 (請參閱本主題稍後有關網站的定義)。請與您的網路作業團隊合作，一同識別您的網路地區。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="e52cc-130">關聯中央網站與個別網路地區</span><span class="sxs-lookup"><span data-stu-id="e52cc-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="e52cc-131">CAC 要求每個網路地區定義 Lync Server 中央站台。</span><span class="sxs-lookup"><span data-stu-id="e52cc-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="e52cc-132">中央網站係以與該網路地區內所有其他網站相較之下，具有最佳網路連線和最高頻寬作為選擇依據。</span><span class="sxs-lookup"><span data-stu-id="e52cc-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="e52cc-133">先前的範例網路拓撲顯示三個網路地區，每一個都具備中央網站以負責管理 CAC 決策。</span><span class="sxs-lookup"><span data-stu-id="e52cc-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="e52cc-134">下表顯示先前範例中適當的關聯關係。</span><span class="sxs-lookup"><span data-stu-id="e52cc-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e52cc-135">中央網站不一定會對應至網站。</span><span class="sxs-lookup"><span data-stu-id="e52cc-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="e52cc-136">在此文件，某些中央網站中的範例 — 芝加哥、 倫敦和北京-共用的網路網站相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="e52cc-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="e52cc-137">不過，即使中央網站及網站共用相同的名稱，中央站台是元素的 Lync Server 拓撲，而網路站台是整體所在的網路時的 Lync Server 拓撲的一部分。</span><span class="sxs-lookup"><span data-stu-id="e52cc-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="e52cc-138">網路地區、中央網站與網路網站</span><span class="sxs-lookup"><span data-stu-id="e52cc-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e52cc-139">網路地區</span><span class="sxs-lookup"><span data-stu-id="e52cc-139">Network Region</span></span></th>
<th><span data-ttu-id="e52cc-140">中央網站</span><span class="sxs-lookup"><span data-stu-id="e52cc-140">Central Site</span></span></th>
<th><span data-ttu-id="e52cc-141">網路網站</span><span class="sxs-lookup"><span data-stu-id="e52cc-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-142">北美地區</span><span class="sxs-lookup"><span data-stu-id="e52cc-142">North America</span></span></p></td>
<td><p><span data-ttu-id="e52cc-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="e52cc-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="e52cc-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="e52cc-144">Chicago</span></span></p>
<p><span data-ttu-id="e52cc-145">紐約</span><span class="sxs-lookup"><span data-stu-id="e52cc-145">New York</span></span></p>
<p><span data-ttu-id="e52cc-146">底特律</span><span class="sxs-lookup"><span data-stu-id="e52cc-146">Detroit</span></span></p>
<p><span data-ttu-id="e52cc-147">波特蘭</span><span class="sxs-lookup"><span data-stu-id="e52cc-147">Portland</span></span></p>
<p><span data-ttu-id="e52cc-148">Reno</span><span class="sxs-lookup"><span data-stu-id="e52cc-148">Reno</span></span></p>
<p><span data-ttu-id="e52cc-149">阿布</span><span class="sxs-lookup"><span data-stu-id="e52cc-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="e52cc-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="e52cc-151">倫敦</span><span class="sxs-lookup"><span data-stu-id="e52cc-151">London</span></span></p></td>
<td><p><span data-ttu-id="e52cc-152">倫敦</span><span class="sxs-lookup"><span data-stu-id="e52cc-152">London</span></span></p>
<p><span data-ttu-id="e52cc-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="e52cc-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-154">亞太地區</span><span class="sxs-lookup"><span data-stu-id="e52cc-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="e52cc-155">北京</span><span class="sxs-lookup"><span data-stu-id="e52cc-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="e52cc-156">北京</span><span class="sxs-lookup"><span data-stu-id="e52cc-156">Beijing</span></span></p>
<p><span data-ttu-id="e52cc-157">Manila</span><span class="sxs-lookup"><span data-stu-id="e52cc-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="e52cc-158">識別網路網站</span><span class="sxs-lookup"><span data-stu-id="e52cc-158">Identify Network Sites</span></span>

<span data-ttu-id="e52cc-p109">網站代表您的組織在這個位置擁有實體場地 (例如辦公室、一群建築物或是一座校園)。具有 LAN 以及與其他網站有 WAN 連線的實體場地就視為網站。請先由清點組織內的所有辦公室開始。在我們的範例拓撲裡，北美洲網路地區包含下列網站：紐約、芝加哥、底特律、波特蘭、雷諾與阿布奎基。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="e52cc-p110">您必須建立每個網站與網路地區的關聯。頻寬原則與網站的關聯，取決於網站是否具備有限的 WAN 連結而定。如需有關 CAC 原則與使用這些原則來分配頻寬的詳細資訊，請參閱本主題稍後的＜定義頻寬原則＞。若要設定 CAC，首先請建立網站與網路地區的關聯，然後建立頻寬分配原則以套用至特定網站或地區之間受到頻寬限制的所有連線，以及網站與地區之間的所有 WAN 連線。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="e52cc-167">識別網路連結</span><span class="sxs-lookup"><span data-stu-id="e52cc-167">Identify Network Links</span></span>

<span data-ttu-id="e52cc-p111">網路連結代表可連結不同地區與網站的實體 WAN 連線。在我們的範例拓撲中，共有兩個區域網路連結，各區域與網站之間有五個網路連結，而兩個網站之間又有一個網路連結。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="e52cc-170">兩個區域連結分別位於北美洲與 EMEA 之間 (以 NA-EMEA-LINK 代表)，以及 APAC 與 EMEA 之間 (以 EMEA-APAC-LINK 代表)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="e52cc-p112">在波特蘭、雷諾與阿布奎基至北美洲地區之間，馬尼拉至 APAC 地域之間，以及科隆至 EMEA 地區之間，會用線條連結，代表網站連結。雷諾與阿布奎基之間的線條顯示這兩個網站之間有直接的網路連結。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="e52cc-173">定義頻寬原則</span><span class="sxs-lookup"><span data-stu-id="e52cc-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="e52cc-p113">請與您的網路作業團隊合作，決定組織內所有 WAN 連結之間的即時音訊與視訊流量可用的 WAN 頻寬大小。當頻寬使用量受到限制，亦即當預期頻寬使用量高出分配給音訊與視訊形式的頻寬大小時，通常會在 WAN 連結上套用頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="e52cc-p114">CAC *「頻寬原則」* 定義可保留給即時音訊與視訊形式的最大頻寬。由於 CAC 未限制其他流量的頻寬，因此無法防止其他資料流量 (例如大型檔案傳輸、音樂串流等等) 用完所有的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="e52cc-178">CAC 頻寬原則可定義下列任一或所有項目：</span><span class="sxs-lookup"><span data-stu-id="e52cc-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="e52cc-179">分配給音訊的最大總頻寬。</span><span class="sxs-lookup"><span data-stu-id="e52cc-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="e52cc-180">分配給視訊的最大總頻寬。</span><span class="sxs-lookup"><span data-stu-id="e52cc-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="e52cc-181">分配給單一音訊通話 (工作階段) 的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="e52cc-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="e52cc-182">分配給單一視訊通話 (工作階段) 的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="e52cc-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e52cc-183">所有的 CAC 頻寬值都代表最大的<EM>單向</EM>頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e52cc-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e52cc-184">Lync Server 2013 語音原則功能提供給使用者 （不會放置在使用者的撥出電話） 的傳入呼叫會檢查能夠覆寫頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="e52cc-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="e52cc-185">工作階段建立完畢後，便可準確地計算頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="e52cc-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="e52cc-186">為順利做出適宜的通話許可控制決策，請勿頻繁使用此設定，能不用就不用。</span><span class="sxs-lookup"><span data-stu-id="e52cc-186">This setting should be used sparingly.</span></span> <span data-ttu-id="e52cc-187">如需詳細資訊，請參閱部署文件中<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">建立的語音原則和設定 Lync Server 2013 中的 PSTN 使用方式記錄</A>，或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">修改語音原則和設定 Lync Server 2013 中的 PSTN 使用方式記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="e52cc-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e52cc-p116">若要最佳化個別工作階段的頻寬使用，請斟酌要使用的音訊與視訊轉碼器類型。具體地說，請避免分配過少的頻寬給預期將頻繁使用的轉碼器。相反地，如果您想要防止媒體使用會消耗大量頻寬的轉碼器，請儘可能將每個工作階段的最大頻寬設為最小值以抑制此類用途。對音訊而言，並非每一種情況都有可用的轉碼器。例如：</span><span class="sxs-lookup"><span data-stu-id="e52cc-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="e52cc-193">當您因素頻寬與優先轉碼器，Lync 端點之間的對等音訊通話會使用 RTAudio (8khz) 或 RTAudio (16khz)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="e52cc-194">電話會議之間 Lync 端點和 A / V 會議服務將使用 G.722 或 Siren。</span><span class="sxs-lookup"><span data-stu-id="e52cc-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="e52cc-195">呼叫公用交換的電話網路 (PSTN) 至或來自 Lync 端點將使用 G.711 或 RTAudio (8khz)。</span><span class="sxs-lookup"><span data-stu-id="e52cc-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="e52cc-196">使用下表有助於最佳化每個工作階段的最大頻寬設定。</span><span class="sxs-lookup"><span data-stu-id="e52cc-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="e52cc-197">依轉碼器的頻寬使用</span><span class="sxs-lookup"><span data-stu-id="e52cc-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e52cc-198">轉碼器</span><span class="sxs-lookup"><span data-stu-id="e52cc-198">Codec</span></span></th>
<th><span data-ttu-id="e52cc-199">不含正向錯誤修正 (FEC) 功能的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="e52cc-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="e52cc-200">含正向錯誤修正 (FEC) 功能的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="e52cc-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="e52cc-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-202">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-203">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="e52cc-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-207">Siren</span><span class="sxs-lookup"><span data-stu-id="e52cc-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="e52cc-208">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-209">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-210">G.711</span><span class="sxs-lookup"><span data-stu-id="e52cc-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="e52cc-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-213">G.722</span><span class="sxs-lookup"><span data-stu-id="e52cc-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="e52cc-214">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-215">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="e52cc-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-218">不適用</span><span class="sxs-lookup"><span data-stu-id="e52cc-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-219">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="e52cc-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-221">不適用</span><span class="sxs-lookup"><span data-stu-id="e52cc-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e52cc-p117">頻寬需求需考量下列各項的負荷：Ethernet II、IP、使用者資料包通訊協定 (UDP)、RTP (即時傳輸通訊協定) 與 SRTP (安全即時傳輸通訊協定)。這些需求同時包含 10 kbps 的 RTCP 負荷。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="e52cc-224">雖然 G.722.1 與 Siren 轉碼器很相近，但其位元速率卻不相同。</span><span class="sxs-lookup"><span data-stu-id="e52cc-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="e52cc-225">G.722，Lync Server 會議的預設轉碼器是截然不同 G.722.1 和 Siren 轉碼器。</span><span class="sxs-lookup"><span data-stu-id="e52cc-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="e52cc-226">Siren 轉碼器用於 Lync Server，在下列情況：</span><span class="sxs-lookup"><span data-stu-id="e52cc-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="e52cc-227">當頻寬原則設得太低，以致於無法使用 G.722 時。</span><span class="sxs-lookup"><span data-stu-id="e52cc-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="e52cc-228">如果 Communications Server 2007 或 Communications Server 2007 R2 的用戶端連線至 Lync Server 會議服務 （因為這些用戶端不支援 G.722 轉碼器）。</span><span class="sxs-lookup"><span data-stu-id="e52cc-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="e52cc-229">依案例的頻寬使用</span><span class="sxs-lookup"><span data-stu-id="e52cc-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e52cc-230">案例</span><span class="sxs-lookup"><span data-stu-id="e52cc-230">Scenario</span></span></th>
<th><span data-ttu-id="e52cc-231">數量最佳化的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="e52cc-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="e52cc-232">平衡模式下的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="e52cc-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="e52cc-233">品質最佳化的頻寬需求 (kbps)</span><span class="sxs-lookup"><span data-stu-id="e52cc-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-234">對等音訊通話</span><span class="sxs-lookup"><span data-stu-id="e52cc-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="e52cc-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-238">電話會議</span><span class="sxs-lookup"><span data-stu-id="e52cc-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="e52cc-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-242">PSTN 通話 （Lync 2013 與 PSTN 閘道之間透過媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="e52cc-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-246">PSTN 通話 （Lync 2013 和中繼伺服器之間，不透過媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="e52cc-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52cc-250">PSTN 通話 （中繼伺服器與 PSTN 閘道之間不透過媒體旁路）</span><span class="sxs-lookup"><span data-stu-id="e52cc-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="e52cc-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52cc-254">Lync-Polycom 電話</span><span class="sxs-lookup"><span data-stu-id="e52cc-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="e52cc-255">101 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="e52cc-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="e52cc-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="e52cc-258">識別 IP 子網路</span><span class="sxs-lookup"><span data-stu-id="e52cc-258">Identify IP Subnets</span></span>

<span data-ttu-id="e52cc-p118">對於每一個網路網站，您需要和網路管理員一同決定要指派給每一個網路網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網路網站的 IP 子網路，您的工作將會大幅簡化。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="e52cc-p119">在我們的範例中，將指派以下 IP 子網路給北美洲地區內的紐約網站：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。假設原本在底特律上班的 Bob 必須出差到紐約辦公室接受訓練課程。當他開啟自己的電腦並連線至網路時，他的電腦會取得保留給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="e52cc-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e52cc-264">在伺服器上的網路組態期間指定的 IP 子網路必須相符才能正確地使用媒體旁路的用戶端電腦所提供的格式。</span><span class="sxs-lookup"><span data-stu-id="e52cc-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="e52cc-265">Lync 用戶端會採用其本機 IP 位址，並與相關聯的子網路遮罩遮罩的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e52cc-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="e52cc-266">當決定旁路 ID 與每個用戶端相關聯時，登錄器會比較用戶端提供完全符合的子網路對每個網路網站相關聯的 IP 子網路的清單。</span><span class="sxs-lookup"><span data-stu-id="e52cc-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="e52cc-267">基於這個理由，請務必在伺服器上的網路設定期間輸入的子網路會實際的子網路，而不是虛擬的子網路。</span><span class="sxs-lookup"><span data-stu-id="e52cc-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="e52cc-268">（如果您部署通話許可控制，但不是媒體旁路，通話許可控制會正常運作，即使您設定虛擬子網路）。</span><span class="sxs-lookup"><span data-stu-id="e52cc-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="e52cc-269">例如，如果用戶端登入與 IP 子網路遮罩 255.255.255.0 172.29.81.57 IP 位址的電腦上，Lync 2013 會要求 172.29.81.0 的子網路相關聯的旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="e52cc-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="e52cc-270">如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="e52cc-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="e52cc-271">因此，是很重要系統管理員輸入完全 Lync 用戶端 （這佈建的子網路與網路組態期間靜態或 DHCP。） 所提供的子網路</span><span class="sxs-lookup"><span data-stu-id="e52cc-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

