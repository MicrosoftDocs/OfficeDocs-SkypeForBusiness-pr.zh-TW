---
title: Lync Server 2013 伺服器硬體平臺
description: Lync Server 2013 伺服器硬體平臺。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55deec50994d70cf305b794662a630c16c3af14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551379"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="da0df-103">Lync Server 2013 的伺服器硬體平臺</span><span class="sxs-lookup"><span data-stu-id="da0df-103">Server hardware platforms for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da0df-104">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="da0df-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="da0df-105">Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要64位硬體。</span><span class="sxs-lookup"><span data-stu-id="da0df-105">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="da0df-106">Lync Server 2013 部署所使用的特定硬體，會因大小和使用需求而異。</span><span class="sxs-lookup"><span data-stu-id="da0df-106">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="da0df-107">本節說明建議的硬體。</span><span class="sxs-lookup"><span data-stu-id="da0df-107">This section describes the recommended hardware.</span></span> <span data-ttu-id="da0df-108">雖然這些是建議，不是需求，但使用不符合這些建議的硬體，可能會導致嚴重的效能問題和其他問題。</span><span class="sxs-lookup"><span data-stu-id="da0df-108">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="da0df-109">建議的硬體平臺</span><span class="sxs-lookup"><span data-stu-id="da0df-109">Recommended Hardware Platform</span></span>

<span data-ttu-id="da0df-110">為了達到最佳效能，建議您在具有符合下表中需求之硬體的伺服器上執行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="da0df-110">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="da0df-111">如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能不良。</span><span class="sxs-lookup"><span data-stu-id="da0df-111">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="da0df-112">請注意，這些硬體需求高於舊版的 Lync Server，主要是因為在 Lync Server 2013 中，所有前端伺服器都執行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="da0df-112">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da0df-113">支援 NIC 組合，且對 Lync Server 而言應該是透明的。</span><span class="sxs-lookup"><span data-stu-id="da0df-113">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="da0df-114">如需詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">通訊伺服器或 Lync server 和網路介面卡組合</A>。</span><span class="sxs-lookup"><span data-stu-id="da0df-114">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="da0df-115">前端伺服器、後端伺服器、Standard Edition Server、Persistent Chat Server 和 persistent chat store 及 Persistent chat 合規性存放區的建議硬體，會 (後端伺服器角色，以用於 Persistent Chat Server) </span><span class="sxs-lookup"><span data-stu-id="da0df-115">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da0df-116">硬體元件</span><span class="sxs-lookup"><span data-stu-id="da0df-116">Hardware component</span></span></th>
<th><span data-ttu-id="da0df-117">建議</span><span class="sxs-lookup"><span data-stu-id="da0df-117">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da0df-118">CPU</span><span class="sxs-lookup"><span data-stu-id="da0df-118">CPU</span></span></p></td>
<td><p><span data-ttu-id="da0df-119">64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="da0df-119">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="da0df-120">Lync Server server role 不支援 Intel Itanium 處理器。</span><span class="sxs-lookup"><span data-stu-id="da0df-120">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da0df-121">記憶體</span><span class="sxs-lookup"><span data-stu-id="da0df-121">Memory</span></span></p></td>
<td><p><span data-ttu-id="da0df-122">32 gb (GB) 。</span><span class="sxs-lookup"><span data-stu-id="da0df-122">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da0df-123">磁片</span><span class="sxs-lookup"><span data-stu-id="da0df-123">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da0df-124">8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="da0df-124">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="da0df-125">磁片的兩個應該使用 RAID 1，而六個應該使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="da0df-125">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="da0df-126">- 或</span><span class="sxs-lookup"><span data-stu-id="da0df-126">- OR -</span></span></p></li>
<li><p><span data-ttu-id="da0df-127">固態硬碟 (Ssd) ，可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="da0df-127">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da0df-128">網路</span><span class="sxs-lookup"><span data-stu-id="da0df-128">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da0df-129">1個雙埠網路介面卡，建議使用 1 Gbps 或以上 (2，這需要搭配單一 MAC 位址和單一 IP 位址) 。</span><span class="sxs-lookup"><span data-stu-id="da0df-129">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="da0df-130">前端伺服器、後端伺服器、Standard Edition server 和 Persistent Chat Server 不支援雙重或多穴設定。</span><span class="sxs-lookup"><span data-stu-id="da0df-130">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="da0df-131">ILO/DRAC/etc。對作業系統未公開且用來監視和管理伺服器硬體的連線不會組成多穴伺服器，因此也是受支援的。</span><span class="sxs-lookup"><span data-stu-id="da0df-131">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="da0df-132">Edge Server、獨立轉送伺服器及 Director 的建議硬體</span><span class="sxs-lookup"><span data-stu-id="da0df-132">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da0df-133">硬體元件</span><span class="sxs-lookup"><span data-stu-id="da0df-133">Hardware component</span></span></th>
<th><span data-ttu-id="da0df-134">建議</span><span class="sxs-lookup"><span data-stu-id="da0df-134">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da0df-135">CPU</span><span class="sxs-lookup"><span data-stu-id="da0df-135">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da0df-136">64位雙處理器、四核心、2.0 ghz (GHz) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="da0df-136">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="da0df-137">- 或</span><span class="sxs-lookup"><span data-stu-id="da0df-137">- OR -</span></span></p></li>
<li><p><span data-ttu-id="da0df-138">64位4路處理器、雙核2.0GHz 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="da0df-138">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="da0df-139">Lync Server server role 不支援 Intel Itanium 處理器。</span><span class="sxs-lookup"><span data-stu-id="da0df-139">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da0df-140">記憶體</span><span class="sxs-lookup"><span data-stu-id="da0df-140">Memory</span></span></p></td>
<td><p><span data-ttu-id="da0df-141">16 gb (GB) 。</span><span class="sxs-lookup"><span data-stu-id="da0df-141">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da0df-142">磁片</span><span class="sxs-lookup"><span data-stu-id="da0df-142">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da0df-143">4個以上的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="da0df-143">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="da0df-144">磁片應該是2倍速的 RAID 1 設定。</span><span class="sxs-lookup"><span data-stu-id="da0df-144">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="da0df-145">- 或</span><span class="sxs-lookup"><span data-stu-id="da0df-145">- OR -</span></span></p></li>
<li><p><span data-ttu-id="da0df-146">固態硬碟 (Ssd) ，可提供與 4 10000 RPM 機械磁片磁碟機類似的效能。</span><span class="sxs-lookup"><span data-stu-id="da0df-146">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da0df-147">網路</span><span class="sxs-lookup"><span data-stu-id="da0df-147">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da0df-148">1個雙埠網路介面卡，建議使用 1 Gbps 或以上 (2，這需要搭配單一 MAC 位址和單一 IP 位址) 。</span><span class="sxs-lookup"><span data-stu-id="da0df-148">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="da0df-149">2 Edge Server 上需要網路介面，且在獨立轉送伺服器上支援。</span><span class="sxs-lookup"><span data-stu-id="da0df-149">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="da0df-150">Director 不支援雙穴或多穴設定。</span><span class="sxs-lookup"><span data-stu-id="da0df-150">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="da0df-151">ILO/DRAC/etc。對作業系統未公開且用來監視和管理伺服器硬體的連線不會組成多穴伺服器，因此也是受支援的。</span><span class="sxs-lookup"><span data-stu-id="da0df-151">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="da0df-152">Edge Server 需要兩個網路介面為雙埠網路介面卡、1 Gbps 或更高的 (或兩個配對的網路介面卡（總共四個），每一組都是以單一 MAC 位址和單一 IP 位址組成，每個組的總數都是兩對) 。</span><span class="sxs-lookup"><span data-stu-id="da0df-152">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="da0df-153">安裝額外的網路介面卡 (Nic) 以允許在獨立轉送伺服器上支援特定 PSTN IP 位址的設定。</span><span class="sxs-lookup"><span data-stu-id="da0df-153">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

