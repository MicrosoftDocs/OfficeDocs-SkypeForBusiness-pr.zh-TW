---
title: 'Lync Server 2013: Director 的硬體和軟體需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e0c75135d1ccfbb544c14c5cdc530b4e9a67b47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="2aabc-102">Lync Server 2013 中 director 的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="2aabc-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aabc-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="2aabc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2aabc-104">本節詳細說明 Director 的硬體及軟體需求和 Director 支援的組合案例。</span><span class="sxs-lookup"><span data-stu-id="2aabc-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="2aabc-105">Director 的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2aabc-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="2aabc-106">下表列出 Director 的硬體需求：</span><span class="sxs-lookup"><span data-stu-id="2aabc-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="2aabc-107">Director 的硬體需求</span><span class="sxs-lookup"><span data-stu-id="2aabc-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aabc-108">硬體元件</span><span class="sxs-lookup"><span data-stu-id="2aabc-108">Hardware component</span></span></th>
<th><span data-ttu-id="2aabc-109">基本需求</span><span class="sxs-lookup"><span data-stu-id="2aabc-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aabc-110">CPU</span><span class="sxs-lookup"><span data-stu-id="2aabc-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2aabc-111">64 位元處理器、四核心、2.0 GHz 或更快速度</span><span class="sxs-lookup"><span data-stu-id="2aabc-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="2aabc-112">64 位元雙處理器、四核心、2.0 GHz 或更快速度</span><span class="sxs-lookup"><span data-stu-id="2aabc-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aabc-113">記憶體</span><span class="sxs-lookup"><span data-stu-id="2aabc-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="2aabc-114">4 GB</span><span class="sxs-lookup"><span data-stu-id="2aabc-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aabc-115">磁碟</span><span class="sxs-lookup"><span data-stu-id="2aabc-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2aabc-116">10K RPM 硬碟 (HDD)</span><span class="sxs-lookup"><span data-stu-id="2aabc-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="2aabc-117">高效能固態硬碟 (SSD)，效能等於或優於 10K RPM HDD</span><span class="sxs-lookup"><span data-stu-id="2aabc-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="2aabc-118">2x RAID 10 (等量和鏡像)，15K RPM 磁碟用於資料庫資料檔</span><span class="sxs-lookup"><span data-stu-id="2aabc-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aabc-119">網路</span><span class="sxs-lookup"><span data-stu-id="2aabc-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2aabc-120">雙埠 1 Gbps 的網路介面卡 (建議)</span><span class="sxs-lookup"><span data-stu-id="2aabc-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="2aabc-121">單一 1 Gbps 網路介面卡 (支援)</span><span class="sxs-lookup"><span data-stu-id="2aabc-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="2aabc-122">Director 的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2aabc-122">Software Requirements for the Director</span></span>

<span data-ttu-id="2aabc-123">Director 角色可以部署只在執行 Lync Server 2013 Enterprise Edition 的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="2aabc-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="2aabc-124">下列其中一個下列 64 位元作業系統是 director 需要：</span><span class="sxs-lookup"><span data-stu-id="2aabc-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="2aabc-125">Windows Server 2008 R2 Standard 作業系統 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="2aabc-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2aabc-126">Windows Server 2008 R2 Enterprise 作業系統 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="2aabc-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2aabc-127">Windows Server 2008 R2 Datacenter 作業系統 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="2aabc-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="2aabc-128">Windows Server 2012 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="2aabc-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="2aabc-129">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="2aabc-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="2aabc-130">Lync Server 2013 也需要安裝下列程式和[其他伺服器支援和 Lync Server 2013 中的 requirements](lync-server-2013-additional-server-support-and-requirements.md)主題中詳述的更新。</span><span class="sxs-lookup"><span data-stu-id="2aabc-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="2aabc-131">支援的組合</span><span class="sxs-lookup"><span data-stu-id="2aabc-131">Supported Collocation</span></span>

<span data-ttu-id="2aabc-132">Director 伺服器角色不能與 Lync Server 2013 中的任何其他伺服器角色組合。</span><span class="sxs-lookup"><span data-stu-id="2aabc-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="2aabc-133">不過，如果您不要部署 Director、 前端伺服器將會採用角色。</span><span class="sxs-lookup"><span data-stu-id="2aabc-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

