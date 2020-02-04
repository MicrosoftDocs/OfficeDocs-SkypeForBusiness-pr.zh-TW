---
title: 使用使用者模型的 Lync Server 2013 容量規劃
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
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="18c1b-102">使用使用者模型的 Lync Server 2013 容量規劃</span><span class="sxs-lookup"><span data-stu-id="18c1b-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c1b-103">_**主題上次修改日期：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="18c1b-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="18c1b-104">本節將根據在[Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中所述的使用方式，提供在網站上需要多少伺服器來取得該網站的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="18c1b-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="18c1b-105">已測試的硬體平臺</span><span class="sxs-lookup"><span data-stu-id="18c1b-105">Tested Hardware Platform</span></span>

<span data-ttu-id="18c1b-106">本節中的所有效能結果和部署建議都是以執行下表所述之硬體的伺服器上的效能測試為基礎。</span><span class="sxs-lookup"><span data-stu-id="18c1b-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="18c1b-107">我們建議您使用類似的硬體。</span><span class="sxs-lookup"><span data-stu-id="18c1b-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="18c1b-108">如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能較差。</span><span class="sxs-lookup"><span data-stu-id="18c1b-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="18c1b-109">請注意，這些硬體建議的版本高於舊版 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="18c1b-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="18c1b-110">效能測試中使用的硬體</span><span class="sxs-lookup"><span data-stu-id="18c1b-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-111">硬體元件</span><span class="sxs-lookup"><span data-stu-id="18c1b-111">Hardware component</span></span></th>
<th><span data-ttu-id="18c1b-112">採用</span><span class="sxs-lookup"><span data-stu-id="18c1b-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-113">CPU</span><span class="sxs-lookup"><span data-stu-id="18c1b-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="18c1b-114">64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本</span><span class="sxs-lookup"><span data-stu-id="18c1b-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="18c1b-115">Lync Server server 角色不支援 Intel 安騰處理器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-116">儲存體</span><span class="sxs-lookup"><span data-stu-id="18c1b-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="18c1b-117">32千百萬位元組（英國）</span><span class="sxs-lookup"><span data-stu-id="18c1b-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-118">光碟</span><span class="sxs-lookup"><span data-stu-id="18c1b-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18c1b-119">8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="18c1b-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="18c1b-120">兩個磁片應該使用 RAID 1，而6則應使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="18c1b-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="18c1b-121">-或</span><span class="sxs-lookup"><span data-stu-id="18c1b-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="18c1b-122">固態硬碟（SSDs），可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="18c1b-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-123">網路</span><span class="sxs-lookup"><span data-stu-id="18c1b-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18c1b-124">1個雙埠網路介面卡、1 Gbps 或更新版本（2個建議，需要搭配單一 MAC 位址和單一 IP 位址進行分組）</span><span class="sxs-lookup"><span data-stu-id="18c1b-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="18c1b-125">結果摘要</span><span class="sxs-lookup"><span data-stu-id="18c1b-125">Summary of Results</span></span>

<span data-ttu-id="18c1b-126">下表摘要說明這些建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-127">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="18c1b-127">Server role</span></span></th>
<th><span data-ttu-id="18c1b-128">支援的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="18c1b-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-129">具有十二個前端伺服器和一台後端伺服器，或一對後端伺服器的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="18c1b-130">80000不重複的使用者同時登入，加上50% 的目前狀態（MPOP）（代表非行動實例），加上40% 的使用者，以行動給總的152000端點。</span><span class="sxs-lookup"><span data-stu-id="18c1b-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-131">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="18c1b-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="18c1b-132">前端池所提供的 A/V 會議服務支援池的會議，其會議大小最大為250使用者，且一次只能執行一個此類大型會議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="18c1b-133">此外，您可以使用兩個前端伺服器來部署個別的前端池來託管大型會議，以支援250與1000使用者之間的大型會議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="18c1b-134">如需詳細資訊，請參閱<A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支援大型會議</A>。</span><span class="sxs-lookup"><span data-stu-id="18c1b-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-135">一台邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="18c1b-136">12000併發遠端使用者</span><span class="sxs-lookup"><span data-stu-id="18c1b-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-137">單一控制器</span><span class="sxs-lookup"><span data-stu-id="18c1b-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="18c1b-138">12000併發遠端使用者</span><span class="sxs-lookup"><span data-stu-id="18c1b-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-139">監控和封存</span><span class="sxs-lookup"><span data-stu-id="18c1b-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="18c1b-140">在 Lync Server 2013 中，[監視及存檔前端服務] 現在會在每個前端伺服器上執行，而不是個別的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="18c1b-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="18c1b-141">監視及封存每個仍需要自己的資料庫存放區。</span><span class="sxs-lookup"><span data-stu-id="18c1b-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="18c1b-142">如果您同時執行 Exchange 2013，您可以在 Exchange 中保留您的存檔資料，而不是在專用的 SQL 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="18c1b-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-143">一個中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="18c1b-144">使用前端伺服器的中繼伺服器 collocated 會在池中的每個前端伺服器上執行，而且應該為池中的使用者提供足夠的容量。</span><span class="sxs-lookup"><span data-stu-id="18c1b-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="18c1b-145">若是獨立的中繼伺服器，請參閱本主題稍後的「轉送伺服器」一節。</span><span class="sxs-lookup"><span data-stu-id="18c1b-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-146">一個標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="18c1b-147">我們強烈建議您，如果您使用標準版伺服器來主持使用者，則您一定會使用兩個伺服器，搭配在<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中規劃高可用性和災難</a>復原的建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="18c1b-148">該配對中的每個伺服器都可託管至2500個使用者，如果一個伺服器失敗，其他伺服器就能在容錯移轉案例中支援5000使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="18c1b-149">如果您的部署包含大量的音訊或視頻流量，伺服器效能可能會隨著每個伺服器超過2500個使用者而受到影響。</span><span class="sxs-lookup"><span data-stu-id="18c1b-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="18c1b-150">在這種情況下，您應該考慮新增更多標準版伺服器或移至 Lync Server 企業版。</span><span class="sxs-lookup"><span data-stu-id="18c1b-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="18c1b-151">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-152">此伺服器角色不支援延伸池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="18c1b-153">在前端池中，您應該針對駐留在該池中的每個6660使用者安裝一個前端伺服器，假設該池中的所有伺服器都已啟用超執行緒，且伺服器硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="18c1b-154">一個前端池中的使用者數目上限為80000，假設已在該池中的所有伺服器上啟用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="18c1b-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="18c1b-155">如果網站上有超過80000的使用者，您可以部署多個 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="18c1b-156">當您考慮了前端池中的使用者數目時，請在與此前端池關聯的分支辦公室中，加入 Survivable 分支裝置上的使用者，以及 Survivable 分支伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="18c1b-157">當作用中伺服器無法使用時，其連線會自動轉移至池中的其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="18c1b-158">例如，如果您有30000使用者和5個前端伺服器，則如果有一個伺服器無法使用，6000使用者的連線就必須傳送到其他四個伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="18c1b-159">其餘四個伺服器每個都有7500使用者，這比建議的數大。</span><span class="sxs-lookup"><span data-stu-id="18c1b-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="18c1b-160">如果您已開始將6個前端伺服器用於30000使用者，隨後一個伺服器變為無法使用，則會將總共5000個使用者移至其餘的五台伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="18c1b-161">這五個伺服器會將每個主機6000使用者（在建議的範圍內）。</span><span class="sxs-lookup"><span data-stu-id="18c1b-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="18c1b-162">前端池中的使用者數目上限為80000。</span><span class="sxs-lookup"><span data-stu-id="18c1b-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="18c1b-163">池中最多可有12個前端伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="18c1b-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="18c1b-164">針對80000使用者的前端池，在[Lync Server 2013 中遵循使用者模型](lync-server-2013-user-models.md)的一般部署中，十二個前端伺服器的效能就足夠了。</span><span class="sxs-lookup"><span data-stu-id="18c1b-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="18c1b-165">專為支援災害復原容錯移轉而設計的部署，假設您最多可以在兩個成對的前端池內託管40000使用者，其中每個池都有足夠的前端伺服器來容納兩個池中的使用者，這時必須有一個池需要失敗移到另一個。</span><span class="sxs-lookup"><span data-stu-id="18c1b-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="18c1b-166">根據特定前端池，以良好效能支援的使用者數目，可能會因為下列原因而與這些數位不同：</span><span class="sxs-lookup"><span data-stu-id="18c1b-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="18c1b-167">前端伺服器的硬體不符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="18c1b-168">貴組織的使用方式與使用者模型有很大的差異，例如大量的會議流量。</span><span class="sxs-lookup"><span data-stu-id="18c1b-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18c1b-169">在 Lync Server 2013 中，目前狀態資料庫現已託管在前端伺服器上，而不是在 Lync Server 2010 中託管在後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="18c1b-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="18c1b-170">這表示前端伺服器的磁片效能和容量不應受到此區段前面所列的建議，以及<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>（無論您的前端伺服器所託管的使用者數目）。</span><span class="sxs-lookup"><span data-stu-id="18c1b-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="18c1b-171">下表顯示使用者模型[在 Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中定義的 IM 和目前狀態的平均頻寬。</span><span class="sxs-lookup"><span data-stu-id="18c1b-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-172">每個使用者的平均頻寬</span><span class="sxs-lookup"><span data-stu-id="18c1b-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="18c1b-173">每個前端伺服器的頻寬需求與6660使用者</span><span class="sxs-lookup"><span data-stu-id="18c1b-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="18c1b-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="18c1b-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="18c1b-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-176">若要改善在您的前端伺服器上歸置的 A/V 會議與轉送伺服器功能的媒體效能，您應該在前端伺服器的網路介面卡上啟用接收端縮放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="18c1b-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="18c1b-177">RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。</span><span class="sxs-lookup"><span data-stu-id="18c1b-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="18c1b-178">如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。</span><span class="sxs-lookup"><span data-stu-id="18c1b-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="18c1b-179">如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="18c1b-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="18c1b-180">最大會議</span><span class="sxs-lookup"><span data-stu-id="18c1b-180">Conferencing Maximums</span></span>

<span data-ttu-id="18c1b-181">如果使用者模型中有5% 的使用者在某個時間池中可能處於會議中，一次80000使用者可以同時在會議中擁有4000個使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="18c1b-182">這些會議預期是混合式媒體（一些僅限 IM、某些音訊/視頻、一些音訊/影片等）及參與者人數。</span><span class="sxs-lookup"><span data-stu-id="18c1b-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="18c1b-183">實際所允許的會議數沒有硬性限制，且實際使用量決定實際效能。</span><span class="sxs-lookup"><span data-stu-id="18c1b-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="18c1b-184">例如，如果您的組織有許多比在使用者模型中所採用的混合模式會議，您可能需要部署多於本檔中的建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="18c1b-185">如需使用者模型中假設的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="18c1b-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="18c1b-186">一般 Lync Server 2013 前端池所託管的受支援的最大會議大小，也是由250參與者所承載。</span><span class="sxs-lookup"><span data-stu-id="18c1b-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="18c1b-187">在發生250使用者會議的情況下，該池仍支援其他會議，例如，總計5% 的池使用者都在並行會議中。</span><span class="sxs-lookup"><span data-stu-id="18c1b-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="18c1b-188">例如，在十二個前端伺服器和80000使用者的池中，Lync Server 支援3750其他參與較小會議250的使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="18c1b-189">不論駐留在前臺端池或標準版伺服器上的使用者數目為何，Lync Server 最少支援125在同一個池或伺服器上參與，且正在託管250使用者會議的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="18c1b-190">若要在250和1000使用者之間啟用會議，您可以設定個別的 [前端] 池來主持這些會議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="18c1b-191">這個前端池不會託管任何使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="18c1b-192">如需詳細資訊，請參閱[使用 Lync Server 2013 支援大型會議](lync-server-2013-supporting-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="18c1b-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="18c1b-193">如果貴組織的混合模式會議數超過使用者模型中的假設，您可能需要部署多於此檔中的建議（最多12個 FEs）的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="18c1b-194">如需使用者模型中假設的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="18c1b-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="18c1b-195">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-196">此伺服器角色不支援延伸池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="18c1b-197">您應該針對將同時存取網站的每個12000遠端使用者，部署一個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="18c1b-198">至少我們建議使用兩個 Edge 伺服器來提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="18c1b-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="18c1b-199">這些建議假設 Edge 伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="18c1b-200">當您要考慮邊緣伺服器的使用者數目時，請將駐留在 Survivable 分支裝置上的使用者，以及與此網站上的 [前端] 池相關聯的分支機搆 Survivable 分支伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-201">若要改善 Edge 伺服器上的 A/V 會議 Edge 服務效能，您應該在 Edge 伺服器的網路介面卡上啟用接收端縮放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="18c1b-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="18c1b-202">RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。</span><span class="sxs-lookup"><span data-stu-id="18c1b-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="18c1b-203">如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。</span><span class="sxs-lookup"><span data-stu-id="18c1b-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="18c1b-204">如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="18c1b-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="18c1b-205">Director</span><span class="sxs-lookup"><span data-stu-id="18c1b-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-206">此伺服器角色不支援延伸池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="18c1b-207">如果您部署控制器伺服器角色，建議您針對將同時存取網站的每個12000遠端使用者，部署一個主管。</span><span class="sxs-lookup"><span data-stu-id="18c1b-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="18c1b-208">至少我們建議使用兩個控制器來提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="18c1b-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="18c1b-209">這些建議假設 Edge 伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。</span><span class="sxs-lookup"><span data-stu-id="18c1b-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="18c1b-210">當您考慮控制器的使用者數目時，請將駐留在 Survivable 分支裝置上的使用者，以及與此網站上的 [前端] 池關聯的分支辦公室中的 Survivable 分支伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c1b-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="18c1b-211">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-212">此伺服器角色不支援延伸池。</span><span class="sxs-lookup"><span data-stu-id="18c1b-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="18c1b-213">如果您 collocate 的是前端伺服器的中繼伺服器，則會在池中的每個前端伺服器上執行轉送伺服器，而且應該為池中的使用者提供足夠的容量。</span><span class="sxs-lookup"><span data-stu-id="18c1b-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="18c1b-214">如果您部署獨立的中繼伺服器池，部署的中繼伺服器數量取決於許多因素，包括用於中繼伺服器的硬體、您擁有的 VoIP 使用者數目，以及每個中繼伺服器池的閘道對等數目。控制措施、透過這些閘道的繁忙工時流量，以及繞過中繼伺服器的媒體通話百分比。</span><span class="sxs-lookup"><span data-stu-id="18c1b-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="18c1b-215">下清單格提供一種準則，說明對於中繼伺服器可以處理多少併發呼叫，假設中繼伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)需求，且已啟用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="18c1b-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="18c1b-216">如需有關中繼伺服器可伸縮性的詳細資料，請參閱在 Lync server 2013 中[估計 Lync server 2013 的語音使用與通訊](lync-server-2013-estimating-voice-usage-and-traffic.md)，以及[中繼伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="18c1b-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="18c1b-217">下列所有表格假設在[Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中總結了使用方式。</span><span class="sxs-lookup"><span data-stu-id="18c1b-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="18c1b-218">獨立的中繼伺服器容量：70% 內部使用者、30% 的外部使用者，不使用撥號容量（由中繼伺服器執行的媒體轉碼）</span><span class="sxs-lookup"><span data-stu-id="18c1b-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-219">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="18c1b-219">Server hardware</span></span></th>
<th><span data-ttu-id="18c1b-220">最大通話數</span><span class="sxs-lookup"><span data-stu-id="18c1b-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="18c1b-221">最大 T1 行數</span><span class="sxs-lookup"><span data-stu-id="18c1b-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="18c1b-222">E1 線數目上限</span><span class="sxs-lookup"><span data-stu-id="18c1b-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-223">雙處理器、十六進位核心、2.26 GHz 超執行緒、含<strong>超執行緒</strong>的 CPU，以及 32 GB 記憶體和一個雙埠網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="18c1b-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="18c1b-224">1100</span><span class="sxs-lookup"><span data-stu-id="18c1b-224">1100</span></span></p></td>
<td><p><span data-ttu-id="18c1b-225">46</span><span class="sxs-lookup"><span data-stu-id="18c1b-225">46</span></span></p></td>
<td><p><span data-ttu-id="18c1b-226">35</span><span class="sxs-lookup"><span data-stu-id="18c1b-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-227">雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU、32 GB 記憶體和一個雙埠網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="18c1b-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="18c1b-228">1500</span><span class="sxs-lookup"><span data-stu-id="18c1b-228">1500</span></span></p></td>
<td><p><span data-ttu-id="18c1b-229">63</span><span class="sxs-lookup"><span data-stu-id="18c1b-229">63</span></span></p></td>
<td><p><span data-ttu-id="18c1b-230">47</span><span class="sxs-lookup"><span data-stu-id="18c1b-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-231">雖然使用 32 GB 記憶體的伺服器用於效能測試，但有 16 GB 記憶體的伺服器支援獨立的中繼伺服器，且足以提供此表格所示的效能。</span><span class="sxs-lookup"><span data-stu-id="18c1b-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="18c1b-232">轉送伺服器容量（使用前端伺服器的中繼伺服器 Collocated）70% 內部使用者、30% 外部使用者、無旁路通話容量（由中繼伺服器執行的媒體處理）</span><span class="sxs-lookup"><span data-stu-id="18c1b-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-233">伺服器硬體</span><span class="sxs-lookup"><span data-stu-id="18c1b-233">Server hardware</span></span></th>
<th><span data-ttu-id="18c1b-234">最大通話數</span><span class="sxs-lookup"><span data-stu-id="18c1b-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-235">雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 的記憶體和2個1GB 網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="18c1b-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="18c1b-236">150</span><span class="sxs-lookup"><span data-stu-id="18c1b-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-237">這個數位比獨立的中繼伺服器的數位少許多，因為前端伺服器除了語音通話所需的轉碼外，還必須處理其他的6600使用者功能和功能。</span><span class="sxs-lookup"><span data-stu-id="18c1b-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="18c1b-238">若要改善中繼伺服器的效能，您應該在您的中繼伺服器的網路介面卡上啟用接收端縮放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="18c1b-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="18c1b-239">RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。</span><span class="sxs-lookup"><span data-stu-id="18c1b-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="18c1b-240">如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。</span><span class="sxs-lookup"><span data-stu-id="18c1b-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="18c1b-241">如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="18c1b-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="18c1b-242">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="18c1b-242">Back End Server</span></span>

<span data-ttu-id="18c1b-243">在 Lync Server 2013 中，目前狀態資料庫位於前端伺服器上，而不是在後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="18c1b-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="18c1b-244">這對 Lync Server 2013 中的每個後端伺服器所產生的需求更加簡單，相當於前端伺服器的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="18c1b-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="18c1b-245">將此與 Lync Server 2010 對比，即需要將後端伺服器設為高達25個磁片的伺服器等級。</span><span class="sxs-lookup"><span data-stu-id="18c1b-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="18c1b-246">不過，後端伺服器的工作負荷仍然如此，因此您應該不會因本區段以及[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)中所列的硬體建議而不符合您的要求。</span><span class="sxs-lookup"><span data-stu-id="18c1b-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="18c1b-247">為了提供後端伺服器的高可用性，我們建議您部署伺服器鏡像。</span><span class="sxs-lookup"><span data-stu-id="18c1b-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="18c1b-248">如需詳細資訊，請參閱[Lync Server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="18c1b-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="18c1b-249">監控和封存</span><span class="sxs-lookup"><span data-stu-id="18c1b-249">Monitoring and Archiving</span></span>

<span data-ttu-id="18c1b-250">在 Lync Server 2013 中，如果您部署 [監視] 或 [封存]，這些服務的前端功能會在前端伺服器上執行，而不是個別的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="18c1b-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="18c1b-251">監視和歸檔每個仍使用自己的資料庫存放區，與後端存放區分開。</span><span class="sxs-lookup"><span data-stu-id="18c1b-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="18c1b-252">或者，如果您已部署 Exchange 2013，您可以將即時消息歸檔資料儲存在 Exchange 中，而不是儲存在專用的 SQL store 中。</span><span class="sxs-lookup"><span data-stu-id="18c1b-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="18c1b-253">下表說明每個使用者每天大約需要多少資料庫儲存空間，以監控及封存資料。</span><span class="sxs-lookup"><span data-stu-id="18c1b-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="18c1b-254"><strong>CDR （監視）</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="18c1b-255"><strong>QoE （監視）</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="18c1b-256"><strong>封存</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-257">每位使用者每天所需的磁碟空間</span><span class="sxs-lookup"><span data-stu-id="18c1b-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="18c1b-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="18c1b-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="18c1b-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="18c1b-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="18c1b-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="18c1b-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18c1b-261">Microsoft 使用下表中的硬體，在其效能測試期間進行監視與歸檔。</span><span class="sxs-lookup"><span data-stu-id="18c1b-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="18c1b-262">測試收集了兩個前端池的資料，每個都包含80000使用者。</span><span class="sxs-lookup"><span data-stu-id="18c1b-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="18c1b-263">在監視及封存效能測試中使用的硬體</span><span class="sxs-lookup"><span data-stu-id="18c1b-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c1b-264">硬體元件</span><span class="sxs-lookup"><span data-stu-id="18c1b-264">Hardware component</span></span></th>
<th><span data-ttu-id="18c1b-265">採用</span><span class="sxs-lookup"><span data-stu-id="18c1b-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-266">CPU</span><span class="sxs-lookup"><span data-stu-id="18c1b-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="18c1b-267">64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本</span><span class="sxs-lookup"><span data-stu-id="18c1b-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-268">儲存體</span><span class="sxs-lookup"><span data-stu-id="18c1b-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="18c1b-269">48千百萬位元組（英國）</span><span class="sxs-lookup"><span data-stu-id="18c1b-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-270">光碟</span><span class="sxs-lookup"><span data-stu-id="18c1b-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="18c1b-271">每個磁片都有 300 GB 的 25 10000 RPM 硬碟磁片磁碟機，且具有下列配置</span><span class="sxs-lookup"><span data-stu-id="18c1b-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="18c1b-272"><strong>軟盤機</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="18c1b-273"><strong>RAID 設定</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="18c1b-274"><strong>磁片數量</strong></span><span class="sxs-lookup"><span data-stu-id="18c1b-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-275">在單一磁片磁碟機上的 CDR、QoE 及封存資料庫資料檔</span><span class="sxs-lookup"><span data-stu-id="18c1b-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="18c1b-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="18c1b-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="18c1b-277">位</span><span class="sxs-lookup"><span data-stu-id="18c1b-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-278">CDR 資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="18c1b-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="18c1b-279">1</span><span class="sxs-lookup"><span data-stu-id="18c1b-279">1</span></span></p></td>
<td><p><span data-ttu-id="18c1b-280">2</span><span class="sxs-lookup"><span data-stu-id="18c1b-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-281">QoE 資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="18c1b-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="18c1b-282">1</span><span class="sxs-lookup"><span data-stu-id="18c1b-282">1</span></span></p></td>
<td><p><span data-ttu-id="18c1b-283">2</span><span class="sxs-lookup"><span data-stu-id="18c1b-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c1b-284">封存資料庫記錄檔</span><span class="sxs-lookup"><span data-stu-id="18c1b-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="18c1b-285">1</span><span class="sxs-lookup"><span data-stu-id="18c1b-285">1</span></span></p></td>
<td><p><span data-ttu-id="18c1b-286">2</span><span class="sxs-lookup"><span data-stu-id="18c1b-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c1b-287">網路</span><span class="sxs-lookup"><span data-stu-id="18c1b-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18c1b-288">1個雙埠網路介面卡、1 Gbps 或更新版本（2個建議，需要搭配單一 MAC 位址和單一 IP 位址進行分組）</span><span class="sxs-lookup"><span data-stu-id="18c1b-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="18c1b-289">本節內容</span><span class="sxs-lookup"><span data-stu-id="18c1b-289">In This Section</span></span>

  - [<span data-ttu-id="18c1b-290">針對 Lync Server 2013 評估語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="18c1b-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="18c1b-291">Lync Server 2013 中的中繼伺服器部署指導方針</span><span class="sxs-lookup"><span data-stu-id="18c1b-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

