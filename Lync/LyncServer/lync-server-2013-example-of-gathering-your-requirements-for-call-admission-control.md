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
ms.openlocfilehash: 89983ae54e879bdb55691b33a0512a00e5883735
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528440"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="97fa8-102">範例：在 Lync Server 2013 中收集通話許可控制需求</span><span class="sxs-lookup"><span data-stu-id="97fa8-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97fa8-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="97fa8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="97fa8-p101">本範例顯示規劃及實作通話許可控制 (CAC) 的方式。概略而言，其中包含下列幾項活動：</span><span class="sxs-lookup"><span data-stu-id="97fa8-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="97fa8-106">識別您的所有網路中樞與骨幹 (又稱為*網路地區*)。</span><span class="sxs-lookup"><span data-stu-id="97fa8-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="97fa8-107">識別將為每個網路地區管理 CAC 的 Lync Server 中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="97fa8-108">識別及定義連線至每個網路地區的*網站*。</span><span class="sxs-lookup"><span data-stu-id="97fa8-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="97fa8-109">針對每個網路與 WAN 的連線受到頻寬限制的網站，請描述 WAN 連線的頻寬容量，以及網路系統管理員對 Lync Server 媒體流量所設定的頻寬限制（如果適用）。</span><span class="sxs-lookup"><span data-stu-id="97fa8-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="97fa8-110">WAN 連線的頻寬不受限制的網站無須納入。</span><span class="sxs-lookup"><span data-stu-id="97fa8-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="97fa8-111">建立網路中每個子網路與網站間的關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="97fa8-112">對應網路地區之間的連結。</span><span class="sxs-lookup"><span data-stu-id="97fa8-112">Map the links between the network regions.</span></span> <span data-ttu-id="97fa8-113">針對每個連結，描述其頻寬容量，以及網路系統管理員對 Lync Server 媒體流量所放置的任何限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="97fa8-114">定義每一組網路地區之間的路由。</span><span class="sxs-lookup"><span data-stu-id="97fa8-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="97fa8-115">收集必要資訊</span><span class="sxs-lookup"><span data-stu-id="97fa8-115">Gather the Required Information</span></span>

<span data-ttu-id="97fa8-116">若要進行通話許可控制的準備工作，請收集下列步驟中所說明的資訊：</span><span class="sxs-lookup"><span data-stu-id="97fa8-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="97fa8-p104">識別您的網路地區。網路地區可代表網路骨幹或網路中樞。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="97fa8-p105">網路骨幹或網路中樞是電腦網路基礎結構之中可讓不同網路組件交互連線的部分，可提供路徑讓不同的 LAN 或子網路之間進行資訊交換。骨幹可連繫不同形式的網路，從小地方乃至於廣大的地理區域皆可。骨幹通常會比與之連接的網路有更大的容量。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="97fa8-p106">此處的範例拓撲具有三個網路地區：北美地區、EMEA 與 APAC。網路地區包含一個網站集合。請與您的網路系統管理員共同定義企業的網路地區。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="97fa8-125">識別每個網路地區所關聯的中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="97fa8-126">中央網站包含至少一部前端伺服器，也是 Lync Server 部署，可管理透過網路地區之 WAN 連線的所有媒體流量的 CAC。</span><span class="sxs-lookup"><span data-stu-id="97fa8-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="97fa8-127">**範例企業網路分成三個網路地區**</span><span class="sxs-lookup"><span data-stu-id="97fa8-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="97fa8-128">![具有3個網路地區的網路拓撲範例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "具有3個網路地區的網路拓撲範例")</span><span class="sxs-lookup"><span data-stu-id="97fa8-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="97fa8-129">Multiprotocol Label Switching (MPLS) 網路應呈現為每個地理位置皆有其對應網站的網路地區。</span><span class="sxs-lookup"><span data-stu-id="97fa8-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="97fa8-130">如需詳細資訊，請參閱規劃檔中的「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">使用 Lync Server 2013 的 MPLS 網路上的通話許可控制</A>」主題。</span><span class="sxs-lookup"><span data-stu-id="97fa8-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="97fa8-131">在上述的網路拓撲範例中，有三個網路區域，每個地區都有一個管理 CAC 的 Lync Server 中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="97fa8-132">網路地區會依據地理位置鄰近性選出適當的中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="97fa8-133">由於媒體流量最大之處是在網路地區內，因此若能位於鄰近之處，此中央網站將保有獨立運作性，且在其他中央網站無法使用時仍能持續運作。</span><span class="sxs-lookup"><span data-stu-id="97fa8-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="97fa8-134">在此範例中，名為芝加哥的 Lync Server 部署為北美地區的中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="97fa8-135">北美所有的 Lync 使用者皆位於芝加哥部署中的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="97fa8-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="97fa8-136">下表顯示三個網路地區的中央網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="97fa8-137">網路地區及其關聯的中央網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="97fa8-138">網路地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-138">Network Region</span></span></th>
    <th><span data-ttu-id="97fa8-139">中央網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-140">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-141">Chicago</span><span class="sxs-lookup"><span data-stu-id="97fa8-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-142">Emea</span><span class="sxs-lookup"><span data-stu-id="97fa8-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-143">倫敦</span><span class="sxs-lookup"><span data-stu-id="97fa8-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-144">亞太</span><span class="sxs-lookup"><span data-stu-id="97fa8-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-145">北京</span><span class="sxs-lookup"><span data-stu-id="97fa8-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="97fa8-146">根據您的 Lync Server 拓撲，相同的中央網站可以指派給多個網路地區。</span><span class="sxs-lookup"><span data-stu-id="97fa8-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="97fa8-p111">對於各個網路地區，識別 WAN 連線的頻寬不受限制的所有網站 (辦公室或地點)。由於這些網站的頻寬不受限制，因此您無須對其套用 CAC 頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="97fa8-149">在下表顯示的範例中，有三個網站不含頻寬受到限制的 WAN 連結：紐約、芝加哥與底特律。</span><span class="sxs-lookup"><span data-stu-id="97fa8-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="97fa8-150">不受 WAN 頻寬限制的網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="97fa8-151">網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-151">Network Site</span></span></th>
    <th><span data-ttu-id="97fa8-152">網路地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-153">紐約</span><span class="sxs-lookup"><span data-stu-id="97fa8-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-154">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-155">Chicago</span><span class="sxs-lookup"><span data-stu-id="97fa8-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-156">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-157">底特律</span><span class="sxs-lookup"><span data-stu-id="97fa8-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-158">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="97fa8-159">對於各個網路地區，識別透過頻寬受到限制的 WAN 連結連線至網路地區的所有網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="97fa8-160">為了協助確保音訊與視訊品質，建議您讓這些頻寬受限的網站監控其 WAN，並使用會對網路地區的進出媒體流量 (聲音或視訊) 施加限制的 CAC 頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="97fa8-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="97fa8-161">在下表顯示的範例中，有三個網站受到 WAN 頻寬的限制：波特蘭、雷諾與阿布奎基。</span><span class="sxs-lookup"><span data-stu-id="97fa8-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="97fa8-162">受 WAN 頻寬限制的網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="97fa8-163">網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-163">Network Site</span></span></th>
    <th><span data-ttu-id="97fa8-164">網路地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-165">阿爾伯克爾基</span><span class="sxs-lookup"><span data-stu-id="97fa8-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-166">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-167">雷諾</span><span class="sxs-lookup"><span data-stu-id="97fa8-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-168">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-169">波特蘭</span><span class="sxs-lookup"><span data-stu-id="97fa8-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-170">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="97fa8-171">**CAC 網路地區「北美地區」，其中有三個網站不受頻寬限制 (芝加哥、紐約與底特律)，三個網站受 WAN 頻寬限制 (波特蘭、雷諾與阿布奎基)**</span><span class="sxs-lookup"><span data-stu-id="97fa8-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="97fa8-172">![受 WAN 頻寬限制的網路網站範例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "受 WAN 頻寬限制的網路網站範例")</span><span class="sxs-lookup"><span data-stu-id="97fa8-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="97fa8-173">為每個頻寬受限的 WAN 連結決定下列項目：</span><span class="sxs-lookup"><span data-stu-id="97fa8-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="97fa8-174">您要為所有的並行音訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="97fa8-175">如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p113">您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="97fa8-178">您要為所有並行視訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="97fa8-179">如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p115">您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="97fa8-182">網站與 WAN 頻寬限制資訊 (頻寬以 kbps 為單位)</span><span class="sxs-lookup"><span data-stu-id="97fa8-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="97fa8-183">網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-183">Network Site</span></span></th>
    <th><span data-ttu-id="97fa8-184">網路地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-184">Network Region</span></span></th>
    <th><span data-ttu-id="97fa8-185">BW 限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-185">BW Limit</span></span></th>
    <th><span data-ttu-id="97fa8-186">音訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="97fa8-187">音訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="97fa8-188">視訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-188">Video Limit</span></span></th>
    <th><span data-ttu-id="97fa8-189">視訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-190">阿爾伯克爾基</span><span class="sxs-lookup"><span data-stu-id="97fa8-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-191">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-192">5,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-193">2,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-194">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-194">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-195">1400</span><span class="sxs-lookup"><span data-stu-id="97fa8-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-196">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-197">雷諾</span><span class="sxs-lookup"><span data-stu-id="97fa8-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-198">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-199">10,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-200">4000</span><span class="sxs-lookup"><span data-stu-id="97fa8-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-201">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-201">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-202">2800</span><span class="sxs-lookup"><span data-stu-id="97fa8-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-203">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-204">波特蘭</span><span class="sxs-lookup"><span data-stu-id="97fa8-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-205">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-206">5,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-207">4000</span><span class="sxs-lookup"><span data-stu-id="97fa8-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-208">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-208">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-209">2800</span><span class="sxs-lookup"><span data-stu-id="97fa8-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-210">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-211">紐約</span><span class="sxs-lookup"><span data-stu-id="97fa8-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-212">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-213">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-214">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-215">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-216">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-217">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-218">Chicago</span><span class="sxs-lookup"><span data-stu-id="97fa8-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-219">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-220">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-221">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-222">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-223">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-224">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-225">底特律</span><span class="sxs-lookup"><span data-stu-id="97fa8-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-226">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-227">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-228">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-229">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-230">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-231">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="97fa8-232">為您網路中的每個子網路指定其關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="97fa8-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="97fa8-p116">網路中的每個子網路都必須與一個網站相關聯，即使該網站的頻寬不受限亦然。這是因為「通話許可控制」會使用子網路資訊來判斷端點所在的網站。確認工作階段中雙方的所在位置後，「通話許可控制」即可判斷是否有足夠的頻寬可建立通話。在透過沒有頻寬限制的連結建立工作階段時，將會產生通知。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="97fa8-237">如果您部署了 Audio/Video Edge Server，則每個 Edge Server 的公用 IP 位址都必須與 Edge Server 部署所在的網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="97fa8-238">A/V Edge Server 的每個公用 IP 位址，都必須在您的網路組態設定中新增為具有子網路遮罩 32 的子網路。</span><span class="sxs-lookup"><span data-stu-id="97fa8-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="97fa8-239">例如，若您在「芝加哥」中部署了 A/V Edge Server，則應為這些伺服器的每個外部 IP 位址建立具有子網路遮罩 32 的子網路，並建立網站「芝加哥」與這些子網路的關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="97fa8-240">如需公用 IP 位址的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="97fa8-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="97fa8-p118">會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。此通知在 8 小時內不會多次引發。以下是相關的通知資訊與範例：</span><span class="sxs-lookup"><span data-stu-id="97fa8-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="97fa8-244"><STRONG>來源：</STRONG> CS 頻寬原則服務 (核心) </span><span class="sxs-lookup"><span data-stu-id="97fa8-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="97fa8-245"><STRONG>事件編號：</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="97fa8-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="97fa8-246"><STRONG>層級：</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="97fa8-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="97fa8-247"><STRONG>描述：</STRONG> 下列 IP 位址的子網： &lt; 未設定 Ip 位址的清單 &gt; ，或未將子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="97fa8-248"><STRONG>原因：</STRONG> 網路設定中遺失對應之 IP 位址的子網，也不會將子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="97fa8-249"><STRONG>解決方法：</STRONG> 將對應至先前的 IP 位址清單的子網新增至網路設定設定，並將每個子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="97fa8-p119">例如，如果通知中的 IP 位址清單指定了 10.121.248.226 與 10.121.249.20，表示這些 IP 位址未與子網路相關聯，或是與這些位址相關聯的子網路不屬於任何網站。如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題：</span><span class="sxs-lookup"><span data-stu-id="97fa8-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="97fa8-252">確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="97fa8-253">確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="97fa8-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="97fa8-254">網站與相關聯的子網路 (頻寬以 kbps 為單位)</span><span class="sxs-lookup"><span data-stu-id="97fa8-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="97fa8-255">網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-255">Network Site</span></span></th>
    <th><span data-ttu-id="97fa8-256">網路地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-256">Network Region</span></span></th>
    <th><span data-ttu-id="97fa8-257">BW 限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-257">BW Limit</span></span></th>
    <th><span data-ttu-id="97fa8-258">音訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="97fa8-259">音訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="97fa8-260">視訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-260">Video Limit</span></span></th>
    <th><span data-ttu-id="97fa8-261">視訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="97fa8-262">子網路</span><span class="sxs-lookup"><span data-stu-id="97fa8-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-263">阿爾伯克爾基</span><span class="sxs-lookup"><span data-stu-id="97fa8-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-264">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-265">5,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-266">2,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-267">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-267">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-268">1400</span><span class="sxs-lookup"><span data-stu-id="97fa8-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-269">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-269">700</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-270">172.29.79.0/23，157.57.215.0/25，172.29.90.0/23，172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="97fa8-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-271">雷諾</span><span class="sxs-lookup"><span data-stu-id="97fa8-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-272">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-273">10,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-274">4000</span><span class="sxs-lookup"><span data-stu-id="97fa8-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-275">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-275">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-276">2800</span><span class="sxs-lookup"><span data-stu-id="97fa8-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-277">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-277">700</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-278">157.57.210.0/23，172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="97fa8-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-279">波特蘭</span><span class="sxs-lookup"><span data-stu-id="97fa8-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-280">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-281">5,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-282">4000</span><span class="sxs-lookup"><span data-stu-id="97fa8-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-283">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-283">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-284">2800</span><span class="sxs-lookup"><span data-stu-id="97fa8-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-285">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-285">700</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-286">172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="97fa8-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-287">紐約</span><span class="sxs-lookup"><span data-stu-id="97fa8-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-288">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-289">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-290">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-291">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-292">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-293">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-294">172.29.80.0/23，157.57.216.0/25，172.29.91.0/23，172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="97fa8-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-295">Chicago</span><span class="sxs-lookup"><span data-stu-id="97fa8-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-296">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-297">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-298">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-299">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-300">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-301">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-302">157.57.211.0/23，172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="97fa8-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-303">底特律</span><span class="sxs-lookup"><span data-stu-id="97fa8-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-304">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-305">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-306">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-307">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-308">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-309">(無限制)</span><span class="sxs-lookup"><span data-stu-id="97fa8-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-310">172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="97fa8-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="97fa8-311">在 [Lync Server 通話許可控制] 中，網路地區之間的連線稱為 *地區連結*。</span><span class="sxs-lookup"><span data-stu-id="97fa8-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="97fa8-312">請比照網站的處理方式，為每個地區連結指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="97fa8-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="97fa8-313">您要為所有的並行音訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="97fa8-314">如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p122">您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="97fa8-317">您要為所有並行視訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="97fa8-318">如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p124">您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="97fa8-321">**網路地區連結與相關聯的頻寬限制**</span><span class="sxs-lookup"><span data-stu-id="97fa8-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="97fa8-322">![3個地區之間的限制範例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3個地區之間的限制範例")</span><span class="sxs-lookup"><span data-stu-id="97fa8-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="97fa8-323">地區連結頻寬資訊 (頻寬以 kbps 為單位)</span><span class="sxs-lookup"><span data-stu-id="97fa8-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="97fa8-324">地區連結名稱</span><span class="sxs-lookup"><span data-stu-id="97fa8-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="97fa8-325">第一個地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-325">First Region</span></span></th>
    <th><span data-ttu-id="97fa8-326">第二個地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-326">Second Region</span></span></th>
    <th><span data-ttu-id="97fa8-327">BW 限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-327">BW Limit</span></span></th>
    <th><span data-ttu-id="97fa8-328">音訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="97fa8-329">音訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="97fa8-330">視訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-330">Video Limit</span></span></th>
    <th><span data-ttu-id="97fa8-331">視訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-332">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="97fa8-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-333">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-334">Emea</span><span class="sxs-lookup"><span data-stu-id="97fa8-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-335">50,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-336">20,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-337">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-337">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-338">14000</span><span class="sxs-lookup"><span data-stu-id="97fa8-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-339">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-340">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="97fa8-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-341">Emea</span><span class="sxs-lookup"><span data-stu-id="97fa8-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-342">亞太</span><span class="sxs-lookup"><span data-stu-id="97fa8-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-343">25,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-344">10,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-345">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-345">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-346">7000</span><span class="sxs-lookup"><span data-stu-id="97fa8-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-347">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="97fa8-348">定義每一組網路地區之間的路由。</span><span class="sxs-lookup"><span data-stu-id="97fa8-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="97fa8-349">「北美地區」與 APAC 兩個地區間的路由需要兩個連結，因為並沒有直接連接這兩者的地區連結。</span><span class="sxs-lookup"><span data-stu-id="97fa8-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="97fa8-350">地區路由</span><span class="sxs-lookup"><span data-stu-id="97fa8-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="97fa8-351">地區路由名稱</span><span class="sxs-lookup"><span data-stu-id="97fa8-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="97fa8-352">第一個地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-352">First Region</span></span></th>
    <th><span data-ttu-id="97fa8-353">第二個地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-353">Second Region</span></span></th>
    <th><span data-ttu-id="97fa8-354">地區連結</span><span class="sxs-lookup"><span data-stu-id="97fa8-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-355">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="97fa8-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-356">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-357">Emea</span><span class="sxs-lookup"><span data-stu-id="97fa8-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-358">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="97fa8-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="97fa8-359">EMEA-APAC-路由傳送</span><span class="sxs-lookup"><span data-stu-id="97fa8-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-360">Emea</span><span class="sxs-lookup"><span data-stu-id="97fa8-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-361">亞太</span><span class="sxs-lookup"><span data-stu-id="97fa8-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-362">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="97fa8-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-363">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="97fa8-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-364">北美地區</span><span class="sxs-lookup"><span data-stu-id="97fa8-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-365">亞太</span><span class="sxs-lookup"><span data-stu-id="97fa8-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-366">NA-EMEA-LINK、EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="97fa8-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="97fa8-367">為每一組由單一連結 (稱為「網站間」\*\* 連結) 直接連接的網站，指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="97fa8-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="97fa8-368">您要為所有的並行音訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="97fa8-369">如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p126">您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="97fa8-372">您要為所有並行視訊工作階段設定的整體頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="97fa8-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="97fa8-373">如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。</span><span class="sxs-lookup"><span data-stu-id="97fa8-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="97fa8-p128">您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。</span><span class="sxs-lookup"><span data-stu-id="97fa8-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="97fa8-376">**CAC 網路地區「北美地區」，顯示雷諾與阿布奎基兩者間之網站間連結的頻寬容量與頻寬限制**</span><span class="sxs-lookup"><span data-stu-id="97fa8-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="97fa8-377">![受 WAN 頻寬限制的網路網站範例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "受 WAN 頻寬限制的網路網站範例")</span><span class="sxs-lookup"><span data-stu-id="97fa8-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="97fa8-378">兩個網站間之網站間連結的頻寬資訊 (頻寬以 kbps 為單位)</span><span class="sxs-lookup"><span data-stu-id="97fa8-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="97fa8-379">網站間連結名稱</span><span class="sxs-lookup"><span data-stu-id="97fa8-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="97fa8-380">第一個網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-380">First Site</span></span></th>
    <th><span data-ttu-id="97fa8-381">第二個網站</span><span class="sxs-lookup"><span data-stu-id="97fa8-381">Second Site</span></span></th>
    <th><span data-ttu-id="97fa8-382">BW 限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-382">BW Limit</span></span></th>
    <th><span data-ttu-id="97fa8-383">音訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="97fa8-384">音訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="97fa8-385">視訊限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-385">Video Limit</span></span></th>
    <th><span data-ttu-id="97fa8-386">視訊工作階段限制</span><span class="sxs-lookup"><span data-stu-id="97fa8-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="97fa8-387">雷諾-Albu-連結間連結</span><span class="sxs-lookup"><span data-stu-id="97fa8-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-388">雷諾</span><span class="sxs-lookup"><span data-stu-id="97fa8-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-389">阿爾伯克爾基</span><span class="sxs-lookup"><span data-stu-id="97fa8-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-390">20,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-391">12000</span><span class="sxs-lookup"><span data-stu-id="97fa8-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-392">175</span><span class="sxs-lookup"><span data-stu-id="97fa8-392">175</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-393">5,000</span><span class="sxs-lookup"><span data-stu-id="97fa8-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="97fa8-394">700</span><span class="sxs-lookup"><span data-stu-id="97fa8-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="97fa8-395">後續步驟</span><span class="sxs-lookup"><span data-stu-id="97fa8-395">Next Steps</span></span>

<span data-ttu-id="97fa8-396">收集必要資訊之後，您可以使用 Lync Server 管理命令介面或 Lync Server 控制台執行 CAC 部署。</span><span class="sxs-lookup"><span data-stu-id="97fa8-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="97fa8-397">雖然您可以使用 Lync Server 控制台執行大部分的網路設定工作，若要建立子網和網站間連結，您必須使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="97fa8-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="97fa8-398">如需詳細資訊，請參閱 Lync Server 管理命令介面檔，以取得 <STRONG>New-CsNetworkSubnet</STRONG> Cmdlet 及 <STRONG>CsNetworkIntersitePolicy</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="97fa8-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

