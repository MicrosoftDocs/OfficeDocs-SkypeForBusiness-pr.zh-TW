---
title: Lync Server 2013 的伺服器硬體平台
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
ms.openlocfilehash: 7e352153e4cc2386a159ac11f27f8ba4f5beb09f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="8ccc2-102">Lync Server 2013 的伺服器硬體平台</span><span class="sxs-lookup"><span data-stu-id="8ccc2-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ccc2-103">_**主題上次修改日期：** 2016年-07-28_</span><span class="sxs-lookup"><span data-stu-id="8ccc2-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="8ccc2-104">Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要 64 位元硬體。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="8ccc2-105">用於 Lync Server 2013 部署的特定硬體而異，視大小和使用方式的需求而定。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="8ccc2-106">本節說明建議的硬體。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="8ccc2-107">雖然這些建議，不需求，使用不符合這些建議的硬體可能會導致嚴重的效能問題和其他問題。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="8ccc2-108">建議的硬體平台</span><span class="sxs-lookup"><span data-stu-id="8ccc2-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="8ccc2-109">為了達到最佳效能，建議您以符合下表所列需求的硬體的伺服器上執行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="8ccc2-110">如果您使用較少功能強大的硬體時，您可能會遇到功能的問題或效能不佳。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="8ccc2-111">請注意，這些硬體需求高於的舊版 Lync Server，主要是因為在 Lync Server 2013 中，所有前端伺服器執行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ccc2-112">NIC 小組，以提高為支援，而且應該不會察覺到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="8ccc2-113">如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server 或 Lync Server 和網路介面卡協力作業</A>。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="8ccc2-114">前端伺服器、 後端伺服器、 Standard Edition Server、 Persistent Chat Server 和常設聊天室存放區及常設聊天室規範存放區 （常設聊天室伺服器的後端伺服器角色） 的建議的硬體</span><span class="sxs-lookup"><span data-stu-id="8ccc2-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ccc2-115">硬體元件</span><span class="sxs-lookup"><span data-stu-id="8ccc2-115">Hardware component</span></span></th>
<th><span data-ttu-id="8ccc2-116">建議</span><span class="sxs-lookup"><span data-stu-id="8ccc2-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ccc2-117">CPU</span><span class="sxs-lookup"><span data-stu-id="8ccc2-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="8ccc2-118">64 位元雙處理器、 十六進位-核心、 2.26 ghz 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8ccc2-119">Lync Server 的伺服器角色不支援 Intel Itanium 處理器。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ccc2-120">記憶體</span><span class="sxs-lookup"><span data-stu-id="8ccc2-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="8ccc2-121">32 gb (GB)。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ccc2-122">磁碟</span><span class="sxs-lookup"><span data-stu-id="8ccc2-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ccc2-123">8 或多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8ccc2-124">兩個磁碟使用 RAID 1 和第六個應該使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="8ccc2-125">-或-</span><span class="sxs-lookup"><span data-stu-id="8ccc2-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8ccc2-126">固態硬碟 (Ssd)，其提供類似 8 個 10000 RPM 機械式磁碟機的效能。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ccc2-127">網路</span><span class="sxs-lookup"><span data-stu-id="8ccc2-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ccc2-128">1 雙連接埠網路介面卡，1 Gbps 或更高層級 （建議使用 2，需要與單一 MAC 位址和單一 IP 位址的聯合）。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8ccc2-129">前端伺服器、 後端伺服器、 Standard Edition server 和常設聊天室伺服器不支援雙重或多重主目錄的設定。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="8ccc2-130">ILO-SETT/DRAC/等連線不公開給作業系統，而且用來監視和管理伺服器硬體無法構成多重主目錄伺服器，並因此支援。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="8ccc2-131">Edge Server、 獨立中繼伺服器和 Director 的建議的硬體</span><span class="sxs-lookup"><span data-stu-id="8ccc2-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ccc2-132">硬體元件</span><span class="sxs-lookup"><span data-stu-id="8ccc2-132">Hardware component</span></span></th>
<th><span data-ttu-id="8ccc2-133">建議</span><span class="sxs-lookup"><span data-stu-id="8ccc2-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ccc2-134">CPU</span><span class="sxs-lookup"><span data-stu-id="8ccc2-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ccc2-135">64 位元雙處理器、 四核心、 2.0 ghz 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8ccc2-136">-或-</span><span class="sxs-lookup"><span data-stu-id="8ccc2-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8ccc2-137">64 位元 4 向處理器、 雙核心、 2.0 GHz 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="8ccc2-138">Lync Server 的伺服器角色不支援 Intel Itanium 處理器。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ccc2-139">記憶體</span><span class="sxs-lookup"><span data-stu-id="8ccc2-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="8ccc2-140">16 gb (GB)。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ccc2-141">磁碟</span><span class="sxs-lookup"><span data-stu-id="8ccc2-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ccc2-142">4 個或多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8ccc2-143">2x RAID 1 設定應為磁碟。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="8ccc2-144">-或-</span><span class="sxs-lookup"><span data-stu-id="8ccc2-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8ccc2-145">固態硬碟 (Ssd)，其提供類似 4 個 10000 RPM 機械式磁碟機的效能。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ccc2-146">網路</span><span class="sxs-lookup"><span data-stu-id="8ccc2-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ccc2-147">1 雙連接埠網路介面卡，1 Gbps 或更高層級 （建議使用 2，需要與單一 MAC 位址和單一 IP 位址的聯合）。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="8ccc2-148">2 的網路介面所需要的 Edge Server，並在獨立中繼伺服器上受支援。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="8ccc2-149">Director 不支援雙重或多重主目錄的設定。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="8ccc2-150">ILO-SETT/DRAC/等連線不公開給作業系統，而且用來監視和管理伺服器硬體無法構成多重主目錄伺服器，並因此支援。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="8ccc2-151">Edge Server 時，需要兩個網路介面的雙連接埠網路介面卡，1 Gbps 或更高層級 （或兩個成對的網路介面卡，總計四，正在使用單一的 MAC 位址和單一 IP 位址，兩個配對總計，以每一對）。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="8ccc2-152">獨立中繼伺服器都支援安裝額外的網路介面卡 (Nic)，以允許特定 PSTN IP 位址的設定。</span><span class="sxs-lookup"><span data-stu-id="8ccc2-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

