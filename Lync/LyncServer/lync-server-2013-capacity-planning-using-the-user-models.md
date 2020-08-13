---
title: 使用使用者模型規劃的 Lync Server 2013 容量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7665a8edb5e77514633de5e66a063ab509fdd821
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="292aa-102">使用使用者模型進行 Lync Server 2013 的容量規劃</span><span class="sxs-lookup"><span data-stu-id="292aa-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="292aa-103">_**主題上次修改日期：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="292aa-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="292aa-104">本節依據 [Lync Server 2013 中使用者模型](lync-server-2013-user-models.md)所述的使用方式，針對網站上的使用者人數，提供您在網站上的多少伺服器所需的指導方針。</span><span class="sxs-lookup"><span data-stu-id="292aa-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="292aa-105">測試的硬體平臺</span><span class="sxs-lookup"><span data-stu-id="292aa-105">Tested Hardware Platform</span></span>

<span data-ttu-id="292aa-106">本節中的所有效能結果和部署建議，都是以執行下表所述硬體的伺服器上的效能測試為基礎。</span><span class="sxs-lookup"><span data-stu-id="292aa-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="292aa-107">建議您使用類似的硬體。</span><span class="sxs-lookup"><span data-stu-id="292aa-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="292aa-108">如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能不良。</span><span class="sxs-lookup"><span data-stu-id="292aa-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="292aa-109">請注意，這些硬體建議高於舊版 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="292aa-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="292aa-110">效能測試中所使用的硬體</span><span class="sxs-lookup"><span data-stu-id="292aa-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-111">硬體元件</span><span class="sxs-lookup"><span data-stu-id="292aa-111">Hardware component</span></span></th>
<th><span data-ttu-id="292aa-112">建議</span><span class="sxs-lookup"><span data-stu-id="292aa-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-113">CPU</span><span class="sxs-lookup"><span data-stu-id="292aa-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="292aa-114">64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="292aa-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="292aa-115">Lync Server server role 不支援 Intel Itanium 處理器。</span><span class="sxs-lookup"><span data-stu-id="292aa-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-116">記憶體</span><span class="sxs-lookup"><span data-stu-id="292aa-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="292aa-117">32 gb (GB) </span><span class="sxs-lookup"><span data-stu-id="292aa-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-118">磁片</span><span class="sxs-lookup"><span data-stu-id="292aa-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="292aa-119">8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="292aa-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="292aa-120">磁片的兩個應該使用 RAID 1，而六個應該使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="292aa-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="292aa-121">- 或</span><span class="sxs-lookup"><span data-stu-id="292aa-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="292aa-122">固態硬碟 (Ssd) ，可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="292aa-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-123">網路</span><span class="sxs-lookup"><span data-stu-id="292aa-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="292aa-124">1個雙埠網路介面卡，建議使用 1 Gbps 以上的 (2，需要搭配單一 MAC 位址和單一 IP 位址進行搭配) </span><span class="sxs-lookup"><span data-stu-id="292aa-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="292aa-125">結果摘要</span><span class="sxs-lookup"><span data-stu-id="292aa-125">Summary of Results</span></span>

<span data-ttu-id="292aa-126">下表摘要說明這些建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-127">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="292aa-127">Server role</span></span></th>
<th><span data-ttu-id="292aa-128">支援的使用者人數上限</span><span class="sxs-lookup"><span data-stu-id="292aa-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-129">前端集區，具有十二部前端伺服器和一部後端伺服器，或一對後端伺服器的鏡像對。</span><span class="sxs-lookup"><span data-stu-id="292aa-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="292aa-130">80000同時登入的個別使用者，加上50% 的多點狀態 (MPOP) 代表非行動實例，加上40% 的使用者，以行動為總數，總使用152000端點。</span><span class="sxs-lookup"><span data-stu-id="292aa-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-131">會議 A/V</span><span class="sxs-lookup"><span data-stu-id="292aa-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="292aa-132">前端集區所提供的 A/V 會議服務，可支援集區的會議，其為最大的會議大小為250的使用者，且一次只執行一個這類大型會議。</span><span class="sxs-lookup"><span data-stu-id="292aa-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="292aa-133">此外，您可以將個別的前端集區與兩部前端伺服器搭配使用，以主控大型會議，以支援250和1000使用者之間的大型會議。</span><span class="sxs-lookup"><span data-stu-id="292aa-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="292aa-134">如需詳細資訊，請參閱 <A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支援大型會議</A>。</span><span class="sxs-lookup"><span data-stu-id="292aa-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-135">一部 Edge Server</span><span class="sxs-lookup"><span data-stu-id="292aa-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="292aa-136">12000並行遠端使用者</span><span class="sxs-lookup"><span data-stu-id="292aa-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-137">一個 Director</span><span class="sxs-lookup"><span data-stu-id="292aa-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="292aa-138">12000並行遠端使用者</span><span class="sxs-lookup"><span data-stu-id="292aa-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-139">監控和封存</span><span class="sxs-lookup"><span data-stu-id="292aa-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="292aa-140">在 Lync Server 2013 中，監控和封存前端服務現在會在每一部前端伺服器上執行，而不是在不同的伺服器角色上執行。</span><span class="sxs-lookup"><span data-stu-id="292aa-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="292aa-141">監視和封存每個仍然需要自己的資料庫存放區。</span><span class="sxs-lookup"><span data-stu-id="292aa-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="292aa-142">如果您也執行 Exchange 2013，您可以將封存資料保存在 Exchange 中，而不是放在專用的 SQL 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="292aa-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-143">一個轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="292aa-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="292aa-144">組合與前端伺服器的轉送伺服器，可在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。</span><span class="sxs-lookup"><span data-stu-id="292aa-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="292aa-145">若為獨立轉送伺服器，請參閱本主題稍後的「轉送伺服器」一節。</span><span class="sxs-lookup"><span data-stu-id="292aa-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-146">一個 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="292aa-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="292aa-147">強烈建議您在使用 Standard Edition server 主控使用者時，永遠使用兩部伺服器搭配使用，以在 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中規劃高可用性和嚴重損壞修復</a>的建議搭配使用。</span><span class="sxs-lookup"><span data-stu-id="292aa-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="292aa-148">配對中的每一部伺服器都可以主控最多2500個使用者，如果一部伺服器失敗，則剩餘的伺服器可支援容錯移轉案例中的5000使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="292aa-149">如果您的部署包含大量的音訊或影片流量，則伺服器效能可能會受到每一部伺服器的2500多個使用者的影響。</span><span class="sxs-lookup"><span data-stu-id="292aa-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="292aa-150">在此情況下，您應該考慮新增更多 Standard Edition 伺服器或移至 Lync Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="292aa-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="292aa-151">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="292aa-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-152">此伺服器角色不支援延伸集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="292aa-153">在前端集區中，每個位於集區中的6660使用者都應該有一個前端伺服器，假設集區中的所有伺服器都已啟用超執行緒，而且伺服器硬體符合 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)中的建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="292aa-154">一個前端集區中的使用者數目上限為80000，假設已在集區中的所有伺服器上啟用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="292aa-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="292aa-155">如果網站上的使用者超過80000，您可以部署一個以上的前端集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="292aa-156">當您考慮前端集區中的使用者人數時，請在與此前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable Branch 伺服器的使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="292aa-157">當作用中的伺服器無法使用時，其連線會自動轉接至集區中的其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="292aa-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="292aa-158">例如，如果您有30000使用者和五部前端伺服器，當一部伺服器無法使用時，必須將6000使用者的連線轉移至其他四部伺服器。</span><span class="sxs-lookup"><span data-stu-id="292aa-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="292aa-159">其餘四部伺服器會有7500位使用者，而不是建議的數目。</span><span class="sxs-lookup"><span data-stu-id="292aa-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="292aa-160">如果您已開始使用六部前端伺服器做為30000的使用者，後來一個伺服器無法使用，則總計5000的使用者將會移至其餘的五台伺服器。</span><span class="sxs-lookup"><span data-stu-id="292aa-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="292aa-161">這五部伺服器將每個主機6000使用者，這是建議的範圍。</span><span class="sxs-lookup"><span data-stu-id="292aa-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="292aa-162">前端集區中的使用者數目上限為80000。</span><span class="sxs-lookup"><span data-stu-id="292aa-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="292aa-163">集區中的前端伺服器數目上限為12。</span><span class="sxs-lookup"><span data-stu-id="292aa-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="292aa-164">若是具有80000使用者的前端集區，則在採用 [Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)的一般部署中，十二部前端伺服器對於效能來說已足夠。</span><span class="sxs-lookup"><span data-stu-id="292aa-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="292aa-165">設計用來支援嚴重損壞修復容錯移轉的部署假設每兩個成對的前端集區中，每個集區都有足夠40000的前端伺服器以容納兩個集區中的使用者，則必須有一個集區可以容錯移轉至另一個集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="292aa-166">根據特定前端集區，具有良好效能的支援使用者數目，可能與這些數目不同，原因如下：</span><span class="sxs-lookup"><span data-stu-id="292aa-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="292aa-167">前端伺服器的硬體不符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="292aa-168">您的組織的使用量與使用者模型有極大的差異，例如大量的會議流量。</span><span class="sxs-lookup"><span data-stu-id="292aa-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="292aa-169">在 [Lync Server 2013] 中，目前的目前狀態資料庫是在前端伺服器上裝載，其所在的 Lync Server 2010 與後端伺服器上的主機上的位置不同。</span><span class="sxs-lookup"><span data-stu-id="292aa-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="292aa-170">這表示，不論前端伺服器所主控的使用者數目為何，前端伺服器前面所列的建議和 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>，都不會損害前端伺服器的磁片效能與容量。</span><span class="sxs-lookup"><span data-stu-id="292aa-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="292aa-171">下表顯示 IM 和目前狀態的平均頻寬（如使用者模型 [在 Lync Server 2013 中](lync-server-2013-user-models.md)所定義）。</span><span class="sxs-lookup"><span data-stu-id="292aa-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-172">每位使用者的平均頻寬</span><span class="sxs-lookup"><span data-stu-id="292aa-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="292aa-173">每個前端伺服器與6660使用者的頻寬需求</span><span class="sxs-lookup"><span data-stu-id="292aa-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="292aa-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="292aa-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="292aa-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="292aa-176">若要改善前端伺服器上歸置 A/V 會議和轉送伺服器功能的媒體效能，您應該在前端伺服器上的網路介面卡上啟用接收端伸縮 (RSS) 。</span><span class="sxs-lookup"><span data-stu-id="292aa-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="292aa-177">RSS 可讓伺服器上的多個處理器同時處理內送的封包。</span><span class="sxs-lookup"><span data-stu-id="292aa-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="292aa-178">如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="292aa-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="292aa-179">如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="292aa-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="292aa-180">會議最大</span><span class="sxs-lookup"><span data-stu-id="292aa-180">Conferencing Maximums</span></span>

<span data-ttu-id="292aa-181">給定使用者模型：集區中有5% 的使用者可能在會議中80000，一次只能有5% 的使用者在會議中，一次只能有一次在會議中使用4000使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="292aa-182">這些會議應該是混合媒體 (某些只供 IM 使用的 IM、某些音訊/影片，例如) 和參與者人數。</span><span class="sxs-lookup"><span data-stu-id="292aa-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="292aa-183">實際允許的會議數目沒有硬性限制，而且實際使用方式會決定實際的效能。</span><span class="sxs-lookup"><span data-stu-id="292aa-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="292aa-184">例如，如果您的組織有許多混合模式會議，而超過使用者模型中的假設，您可能需要部署多部前端伺服器或 A/V 的會議服務器，而不是本檔中的建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="292aa-185">如需使用者模型中假設的詳細資訊，請參閱 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="292aa-186">一般 Lync Server 2013 前端集區所主控的支援會議大小上限，也是由250參與者所裝載。</span><span class="sxs-lookup"><span data-stu-id="292aa-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="292aa-187">當發生 250-使用者會議時，集區仍會同時支援其他會議，例如，總的集區使用者人數為同時召開會議的5%。</span><span class="sxs-lookup"><span data-stu-id="292aa-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="292aa-188">例如，在十二部前端伺服器和80000使用者的集區中，當250使用者的會議發生時，Lync Server 會支援3750其他參與小型會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="292aa-189">不論位於前端集區或 Standard Edition server 上的使用者數目為何，Lync Server 至少會支援125在主控250使用者會議的相同集區或伺服器上參與小型會議的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="292aa-190">若要啟用介於250和1000使用者之間的會議，您可以設定個別的前端集區，僅供主控這些會議。</span><span class="sxs-lookup"><span data-stu-id="292aa-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="292aa-191">此前端集區不會主控任何使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="292aa-192">如需詳細資訊，請參閱 [使用 Lync Server 2013 支援大型會議](lync-server-2013-supporting-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="292aa-193">如果您的組織有許多混合模式會議，超過使用者模型中的假設，您可能需要部署的前端伺服器數目超過此檔中的建議 (，最多可包含12個 FEs) 的限制。</span><span class="sxs-lookup"><span data-stu-id="292aa-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="292aa-194">如需使用者模型中假設的詳細資訊，請參閱 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="292aa-195">Edge Server</span><span class="sxs-lookup"><span data-stu-id="292aa-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-196">此伺服器角色不支援延伸集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="292aa-197">您應該針對同時存取網站的每個12000遠端使用者部署一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="292aa-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="292aa-198">至少我們建議使用兩部 Edge 伺服器以取得高可用性。</span><span class="sxs-lookup"><span data-stu-id="292aa-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="292aa-199">這些建議假設 Edge Server 的硬體符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="292aa-200">當您考慮 Edge Server 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室上，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-201">若要提高 Edge Server 上 A/V 會議 Edge service 的效能，您應該在 Edge Server 上的網路介面卡上啟用接收端伸縮 (RSS) 。</span><span class="sxs-lookup"><span data-stu-id="292aa-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="292aa-202">RSS 可讓伺服器上的多個處理器同時處理內送的封包。</span><span class="sxs-lookup"><span data-stu-id="292aa-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="292aa-203">如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="292aa-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="292aa-204">如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="292aa-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="292aa-205">Director</span><span class="sxs-lookup"><span data-stu-id="292aa-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-206">此伺服器角色不支援延伸集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="292aa-207">如果您部署 Director 伺服器角色，建議您針對同時存取網站的每個12000遠端使用者部署一個 Director。</span><span class="sxs-lookup"><span data-stu-id="292aa-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="292aa-208">至少我們建議使用兩個 Director 以取得高可用性。</span><span class="sxs-lookup"><span data-stu-id="292aa-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="292aa-209">這些建議假設 Edge Server 的硬體符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。</span><span class="sxs-lookup"><span data-stu-id="292aa-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="292aa-210">當您考慮 Director 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="292aa-211">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="292aa-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-212">此伺服器角色不支援延伸集區。</span><span class="sxs-lookup"><span data-stu-id="292aa-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="292aa-213">如果您組合轉送伺服器與前端伺服器，則轉送伺服器會在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。</span><span class="sxs-lookup"><span data-stu-id="292aa-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="292aa-214">如果您部署獨立的轉送伺服器集區，則要部署的轉送伺服器數目取決於許多因素，包括用於轉送伺服器的硬體、您擁有的 VoIP 使用者數目、每個轉送伺服器集區所控制的閘道對等數目、透過這些閘道的繁忙小時流量，以及繞過轉送伺服器之媒體的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="292aa-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="292aa-215">下表提供一項指導方針，讓轉送伺服器可以處理多少並行通話，並假設轉送伺服器的硬體符合 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 需求，且已啟用超執行緒功能。</span><span class="sxs-lookup"><span data-stu-id="292aa-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="292aa-216">如需轉送伺服器擴充性的詳細資訊，請參閱在 Lync server 2013 中 [評估 Lync server 2013 的語音使用方式和流量](lync-server-2013-estimating-voice-usage-and-traffic.md) 和中繼 [伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="292aa-217">下表假設 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)所摘要的使用方式。</span><span class="sxs-lookup"><span data-stu-id="292aa-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="292aa-218">獨立轉送伺服器容量：70% 內部使用者，30% 具有非旁路通話容量的外部使用者 (轉送伺服器所執行的媒體轉碼) </span><span class="sxs-lookup"><span data-stu-id="292aa-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-219">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="292aa-219">Server hardware</span></span></th>
<th><span data-ttu-id="292aa-220">呼叫數目上限</span><span class="sxs-lookup"><span data-stu-id="292aa-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="292aa-221">T1 線路數目上限</span><span class="sxs-lookup"><span data-stu-id="292aa-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="292aa-222">E1 線數目上限</span><span class="sxs-lookup"><span data-stu-id="292aa-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-223">雙處理器，hex core，2.26 GHz 超 <strong>執行緒</strong>處理的超執行緒 CPU，含 32 GB 記憶體和一個雙埠網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="292aa-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="292aa-224">1100</span><span class="sxs-lookup"><span data-stu-id="292aa-224">1100</span></span></p></td>
<td><p><span data-ttu-id="292aa-225">46</span><span class="sxs-lookup"><span data-stu-id="292aa-225">46</span></span></p></td>
<td><p><span data-ttu-id="292aa-226">35</span><span class="sxs-lookup"><span data-stu-id="292aa-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-227">雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 記憶體和一個雙埠網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="292aa-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="292aa-228">1500</span><span class="sxs-lookup"><span data-stu-id="292aa-228">1500</span></span></p></td>
<td><p><span data-ttu-id="292aa-229">63</span><span class="sxs-lookup"><span data-stu-id="292aa-229">63</span></span></p></td>
<td><p><span data-ttu-id="292aa-230">47</span><span class="sxs-lookup"><span data-stu-id="292aa-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="292aa-231">雖然具有 32 GB 記憶體的伺服器用於效能測試，但獨立的轉送伺服器支援具有 16 GB 記憶體的伺服器，且足以提供此表格中所示的效能。</span><span class="sxs-lookup"><span data-stu-id="292aa-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="292aa-232">轉送伺服器容量 (與前端伺服器的轉送伺服器組合) 70% 內部使用者、30% 外部使用者、Non-Bypass 通話容量 (轉送伺服器所執行的媒體處理) </span><span class="sxs-lookup"><span data-stu-id="292aa-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-233">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="292aa-233">Server hardware</span></span></th>
<th><span data-ttu-id="292aa-234">呼叫數目上限</span><span class="sxs-lookup"><span data-stu-id="292aa-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-235">雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 記憶體和 2 1GB 網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="292aa-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="292aa-236">150</span><span class="sxs-lookup"><span data-stu-id="292aa-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="292aa-237">此數位比獨立轉送伺服器的號碼小許多，因為前端伺服器除了語音通話所需的轉碼之外，還必須處理其所在之6600使用者的其他功能和功能。</span><span class="sxs-lookup"><span data-stu-id="292aa-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="292aa-238">若要改善轉送伺服器的效能，您應該啟用轉送伺服器上網路介面卡上的接收端擴充 (RSS) 。</span><span class="sxs-lookup"><span data-stu-id="292aa-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="292aa-239">RSS 可讓伺服器上的多個處理器同時處理內送的封包。</span><span class="sxs-lookup"><span data-stu-id="292aa-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="292aa-240">如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="292aa-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="292aa-241">如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="292aa-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="292aa-242">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="292aa-242">Back End Server</span></span>

<span data-ttu-id="292aa-243">在 Lync Server 2013 中，目前狀態資料庫位於前端伺服器上，而不是在後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="292aa-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="292aa-244">這已導致 Lync Server 2013 中的每一部後端伺服器的需求變得更簡單，相當於前端伺服器的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="292aa-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="292aa-245">請將這種方式與 Lync Server 2010 的對比，即要求後端伺服器必須是高達25個磁片的高伺服器等級伺服器。</span><span class="sxs-lookup"><span data-stu-id="292aa-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="292aa-246">不過，後端伺服器的工作負載仍然如此，您應該不會滿足本節前面所列的硬體建議和 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="292aa-247">為了提供高可用性的後端伺服器，我們建議您部署伺服器鏡像。</span><span class="sxs-lookup"><span data-stu-id="292aa-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="292aa-248">如需詳細資訊，請參閱 [Lync server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="292aa-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="292aa-249">監控和封存</span><span class="sxs-lookup"><span data-stu-id="292aa-249">Monitoring and Archiving</span></span>

<span data-ttu-id="292aa-250">在 Lync Server 2013 中，如果您部署監控或封存，這些服務的前端功能會在前端伺服器上執行，而不是在不同的伺服器角色上執行。</span><span class="sxs-lookup"><span data-stu-id="292aa-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="292aa-251">監視和封存每個仍然使用自己的資料庫存放區，與後端存放區分開。</span><span class="sxs-lookup"><span data-stu-id="292aa-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="292aa-252">或者，如果您已部署 Exchange 2013，您可以將立即訊息封存資料儲存在 Exchange 中，而不是儲存在專用的 SQL 存放區中。</span><span class="sxs-lookup"><span data-stu-id="292aa-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="292aa-253">下表指出每位使用者每天需要多少資料庫儲存空間，以監控和封存資料。</span><span class="sxs-lookup"><span data-stu-id="292aa-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="292aa-254"><strong>CDR (監控) </strong></span><span class="sxs-lookup"><span data-stu-id="292aa-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="292aa-255"><strong>QoE (監控) </strong></span><span class="sxs-lookup"><span data-stu-id="292aa-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="292aa-256"><strong>封存</strong></span><span class="sxs-lookup"><span data-stu-id="292aa-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-257">每位使用者每天所需的磁碟空間</span><span class="sxs-lookup"><span data-stu-id="292aa-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="292aa-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="292aa-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="292aa-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="292aa-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="292aa-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="292aa-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="292aa-261">Microsoft 使用下表中的硬體，以在其效能測試期間監控和封存資料庫伺服器。</span><span class="sxs-lookup"><span data-stu-id="292aa-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="292aa-262">測試會收集兩個前端集區的資料，每個集區都包含80000個使用者。</span><span class="sxs-lookup"><span data-stu-id="292aa-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="292aa-263">監視與封存效能測試中所使用的硬體</span><span class="sxs-lookup"><span data-stu-id="292aa-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292aa-264">硬體元件</span><span class="sxs-lookup"><span data-stu-id="292aa-264">Hardware component</span></span></th>
<th><span data-ttu-id="292aa-265">建議</span><span class="sxs-lookup"><span data-stu-id="292aa-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-266">CPU</span><span class="sxs-lookup"><span data-stu-id="292aa-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="292aa-267">64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="292aa-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-268">記憶體</span><span class="sxs-lookup"><span data-stu-id="292aa-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="292aa-269">48 gb (GB) </span><span class="sxs-lookup"><span data-stu-id="292aa-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-270">磁片</span><span class="sxs-lookup"><span data-stu-id="292aa-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="292aa-271">每個磁片上有 300 GB 的 25 10000-RPM 硬碟，使用下列設定</span><span class="sxs-lookup"><span data-stu-id="292aa-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292aa-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="292aa-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="292aa-273"><strong>RAID 設定</strong></span><span class="sxs-lookup"><span data-stu-id="292aa-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="292aa-274"><strong>磁片數目</strong></span><span class="sxs-lookup"><span data-stu-id="292aa-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-275">單一磁片磁碟機上的 CDR、QoE 及封存資料庫資料檔案</span><span class="sxs-lookup"><span data-stu-id="292aa-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="292aa-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="292aa-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="292aa-277">16 </span><span class="sxs-lookup"><span data-stu-id="292aa-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-278">CDR 資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="292aa-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="292aa-279">1</span><span class="sxs-lookup"><span data-stu-id="292aa-279">1</span></span></p></td>
<td><p><span data-ttu-id="292aa-280">2</span><span class="sxs-lookup"><span data-stu-id="292aa-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-281">QoE 資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="292aa-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="292aa-282">1</span><span class="sxs-lookup"><span data-stu-id="292aa-282">1</span></span></p></td>
<td><p><span data-ttu-id="292aa-283">2</span><span class="sxs-lookup"><span data-stu-id="292aa-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292aa-284">封存資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="292aa-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="292aa-285">1</span><span class="sxs-lookup"><span data-stu-id="292aa-285">1</span></span></p></td>
<td><p><span data-ttu-id="292aa-286">2</span><span class="sxs-lookup"><span data-stu-id="292aa-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292aa-287">網路</span><span class="sxs-lookup"><span data-stu-id="292aa-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="292aa-288">1個雙埠網路介面卡，建議使用 1 Gbps 以上的 (2，需要搭配單一 MAC 位址和單一 IP 位址進行搭配) </span><span class="sxs-lookup"><span data-stu-id="292aa-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="292aa-289">本章節內容</span><span class="sxs-lookup"><span data-stu-id="292aa-289">In This Section</span></span>

  - [<span data-ttu-id="292aa-290">評估 Lync Server 2013 的語音使用狀況和流量</span><span class="sxs-lookup"><span data-stu-id="292aa-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="292aa-291">Lync Server 2013 中轉送伺服器的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="292aa-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

