---
title: Lync Server 2013：Director 的軟硬體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="2f637-102">Lync Server 2013 中 Director 的軟硬體需求</span><span class="sxs-lookup"><span data-stu-id="2f637-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f637-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2f637-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2f637-104">本節詳細說明控制器的硬體和軟體需求，以及主管所支援的 collocation 案例。</span><span class="sxs-lookup"><span data-stu-id="2f637-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="2f637-105">主管的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2f637-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="2f637-106">下表列出控制器的硬體需求：</span><span class="sxs-lookup"><span data-stu-id="2f637-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="2f637-107">主管的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2f637-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f637-108">硬體元件</span><span class="sxs-lookup"><span data-stu-id="2f637-108">Hardware component</span></span></th>
<th><span data-ttu-id="2f637-109">最低需求</span><span class="sxs-lookup"><span data-stu-id="2f637-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f637-110">CPU</span><span class="sxs-lookup"><span data-stu-id="2f637-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f637-111">64-位處理器、四核、2.0 GHz 或更新版本</span><span class="sxs-lookup"><span data-stu-id="2f637-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="2f637-112">64位雙處理器、雙核、2.0 GHz 或更新版本</span><span class="sxs-lookup"><span data-stu-id="2f637-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f637-113">儲存體</span><span class="sxs-lookup"><span data-stu-id="2f637-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="2f637-114">4 gb</span><span class="sxs-lookup"><span data-stu-id="2f637-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f637-115">光碟</span><span class="sxs-lookup"><span data-stu-id="2f637-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f637-116">10K RPM 硬碟（HDD）</span><span class="sxs-lookup"><span data-stu-id="2f637-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="2f637-117">高性能固態磁片磁碟機（SSD），性能等於或優於 10K RPM 硬碟</span><span class="sxs-lookup"><span data-stu-id="2f637-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="2f637-118">資料庫資料檔案的 2x RAID 10 （帶狀與鏡像） 15K RPM 磁片</span><span class="sxs-lookup"><span data-stu-id="2f637-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f637-119">網路</span><span class="sxs-lookup"><span data-stu-id="2f637-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f637-120">雙1十億位元/秒（Gbps）網路介面卡（建議使用）</span><span class="sxs-lookup"><span data-stu-id="2f637-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="2f637-121">單一 1 Gbps 網路介面卡（支援）</span><span class="sxs-lookup"><span data-stu-id="2f637-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="2f637-122">主管的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2f637-122">Software Requirements for the Director</span></span>

<span data-ttu-id="2f637-123">Director 角色只能部署在執行 Lync Server 2013 企業版的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="2f637-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="2f637-124">控制器需要下列其中一種64位作業系統：</span><span class="sxs-lookup"><span data-stu-id="2f637-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="2f637-125">Windows Server 2008 R2 標準作業系統（含 Service Pack 1）</span><span class="sxs-lookup"><span data-stu-id="2f637-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2f637-126">Windows Server 2008 R2 Enterprise 作業系統（含 Service Pack 1）</span><span class="sxs-lookup"><span data-stu-id="2f637-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2f637-127">Windows Server 2008 R2 Datacenter 作業系統（含 Service Pack 1）</span><span class="sxs-lookup"><span data-stu-id="2f637-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2f637-128">Windows Server 2012 標準作業系統</span><span class="sxs-lookup"><span data-stu-id="2f637-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="2f637-129">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="2f637-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="2f637-130">Lync Server 2013 也需要安裝下列程式，並詳細說明[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)主題。</span><span class="sxs-lookup"><span data-stu-id="2f637-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="2f637-131">支援的 Collocation</span><span class="sxs-lookup"><span data-stu-id="2f637-131">Supported Collocation</span></span>

<span data-ttu-id="2f637-132">在 Lync Server 2013 中，控制器伺服器角色無法與任何其他伺服器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="2f637-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="2f637-133">不過，如果您不部署控制器，前端伺服器將會假設角色。</span><span class="sxs-lookup"><span data-stu-id="2f637-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

