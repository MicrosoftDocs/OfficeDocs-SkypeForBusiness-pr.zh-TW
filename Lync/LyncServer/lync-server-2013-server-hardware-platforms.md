---
title: Lync Server 2013 伺服器硬體平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="16306-102">Lync Server 2013 的伺服器硬體平台</span><span class="sxs-lookup"><span data-stu-id="16306-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16306-103">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="16306-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="16306-104">Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要64位的硬體。</span><span class="sxs-lookup"><span data-stu-id="16306-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="16306-105">Lync Server 2013 部署所用的特定硬體會依大小和使用需求而有所不同。</span><span class="sxs-lookup"><span data-stu-id="16306-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="16306-106">本節將說明建議的硬體。</span><span class="sxs-lookup"><span data-stu-id="16306-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="16306-107">雖然這些是建議，而不是要求，但使用不符合這些建議的硬體，可能會導致嚴重的效能問題及其他問題。</span><span class="sxs-lookup"><span data-stu-id="16306-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="16306-108">建議的硬體平臺</span><span class="sxs-lookup"><span data-stu-id="16306-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="16306-109">為了獲得最佳效能，建議您在伺服器上執行的 Lync Server 符合下表中的需求。</span><span class="sxs-lookup"><span data-stu-id="16306-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="16306-110">如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能較差。</span><span class="sxs-lookup"><span data-stu-id="16306-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="16306-111">請注意，這些硬體需求高於舊版 Lync Server 的需求，主要是因為在 Lync Server 2013 中，所有前端伺服器都執行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="16306-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16306-112">NIC 組合是受支援的，而且對於 Lync Server 而言應該是透明的。</span><span class="sxs-lookup"><span data-stu-id="16306-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="16306-113">如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">通訊伺服器或 Lync 伺服器與網路介面卡組合</A>。</span><span class="sxs-lookup"><span data-stu-id="16306-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="16306-114">適用于前端伺服器、後端伺服器、標準版伺服器、持續聊天伺服器以及持續聊天規範儲存區（持久聊天伺服器的後端伺服器角色）的建議硬體</span><span class="sxs-lookup"><span data-stu-id="16306-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16306-115">硬體元件</span><span class="sxs-lookup"><span data-stu-id="16306-115">Hardware component</span></span></th>
<th><span data-ttu-id="16306-116">採用</span><span class="sxs-lookup"><span data-stu-id="16306-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16306-117">CPU</span><span class="sxs-lookup"><span data-stu-id="16306-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="16306-118">64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="16306-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="16306-119">Lync Server server 角色不支援 Intel 安騰處理器。</span><span class="sxs-lookup"><span data-stu-id="16306-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16306-120">儲存體</span><span class="sxs-lookup"><span data-stu-id="16306-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="16306-121">32千百萬位元組（GB）。</span><span class="sxs-lookup"><span data-stu-id="16306-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16306-122">光碟</span><span class="sxs-lookup"><span data-stu-id="16306-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16306-123">8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="16306-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="16306-124">兩個磁片應該使用 RAID 1，而6則應使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="16306-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="16306-125">-或</span><span class="sxs-lookup"><span data-stu-id="16306-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="16306-126">固態硬碟（SSDs），可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="16306-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16306-127">網路</span><span class="sxs-lookup"><span data-stu-id="16306-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16306-128">1個雙埠網路介面卡、1 Gbps 或更新版本（2個是建議的，這需要使用單一 MAC 位址和單一 IP 位址進行分組）。</span><span class="sxs-lookup"><span data-stu-id="16306-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="16306-129">前端伺服器、後端伺服器、標準版伺服器及持久聊天伺服器不支援雙或多穴設定。</span><span class="sxs-lookup"><span data-stu-id="16306-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="16306-130">ILO/DRAC/etc. 未向作業系統公開且用於監視及管理伺服器硬體的連線不構成多穴伺服器，因此受到支援。</span><span class="sxs-lookup"><span data-stu-id="16306-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="16306-131">適用于 Edge 伺服器、獨立轉送伺服器和控制器的建議硬體</span><span class="sxs-lookup"><span data-stu-id="16306-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16306-132">硬體元件</span><span class="sxs-lookup"><span data-stu-id="16306-132">Hardware component</span></span></th>
<th><span data-ttu-id="16306-133">採用</span><span class="sxs-lookup"><span data-stu-id="16306-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16306-134">CPU</span><span class="sxs-lookup"><span data-stu-id="16306-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16306-135">64位雙處理器、四核、2.0 十億位元（GHz）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="16306-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="16306-136">-或</span><span class="sxs-lookup"><span data-stu-id="16306-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="16306-137">64位4路處理器、雙核、2.0 GHz 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="16306-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="16306-138">Lync Server server 角色不支援 Intel 安騰處理器。</span><span class="sxs-lookup"><span data-stu-id="16306-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16306-139">儲存體</span><span class="sxs-lookup"><span data-stu-id="16306-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="16306-140">16 gb。</span><span class="sxs-lookup"><span data-stu-id="16306-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16306-141">光碟</span><span class="sxs-lookup"><span data-stu-id="16306-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16306-142">4個以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="16306-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="16306-143">磁片應該是 2x RAID 1 配置。</span><span class="sxs-lookup"><span data-stu-id="16306-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="16306-144">-或</span><span class="sxs-lookup"><span data-stu-id="16306-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="16306-145">固態硬碟（SSDs），可提供與 4 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="16306-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16306-146">網路</span><span class="sxs-lookup"><span data-stu-id="16306-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="16306-147">1個雙埠網路介面卡、1 Gbps 或更新版本（2個是建議的，這需要使用單一 MAC 位址和單一 IP 位址進行分組）。</span><span class="sxs-lookup"><span data-stu-id="16306-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="16306-148">在邊緣伺服器上需要2個網路介面，且在獨立的轉送伺服器上支援。</span><span class="sxs-lookup"><span data-stu-id="16306-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="16306-149">控制器不支援雙穴或多穴設定。</span><span class="sxs-lookup"><span data-stu-id="16306-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="16306-150">ILO/DRAC/etc. 未向作業系統公開且用於監視及管理伺服器硬體的連線不構成多穴伺服器，因此受到支援。</span><span class="sxs-lookup"><span data-stu-id="16306-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="16306-151">Edge 伺服器需要兩個雙埠網路介面卡、1 Gbps 或更高（或兩個成對式網路介面卡）的網路介面，每個配對都是以單一 MAC 位址與單一 IP 位址組成兩個組。</span><span class="sxs-lookup"><span data-stu-id="16306-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="16306-152">安裝額外的網路介面卡（Nic），允許在獨立的轉送伺服器上支援特定 PSTN IP 位址的設定。</span><span class="sxs-lookup"><span data-stu-id="16306-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

