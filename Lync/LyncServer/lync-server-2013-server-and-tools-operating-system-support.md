---
title: Lync Server 2013：伺服器及工具作業系統支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495ac4ba1b09b6a58a146882d54e17a8f3dd70bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510370"
---
# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="57839-102">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="57839-102">Server and tools operating system support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57839-103">_**主題上次修改日期：** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="57839-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="57839-104">Lync Server 2013 只適用于64位，需要有64位的硬體和64版本的 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="57839-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="57839-105">這表示所有執行 Lync Server 2013 系統管理工具的伺服器角色和電腦都執行64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="57839-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="57839-106">伺服器角色的作業系統</span><span class="sxs-lookup"><span data-stu-id="57839-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="57839-107">Lync Server 2013 支援 Lync Server 2013 中的所有伺服器角色之下列作業系統的64位版本：</span><span class="sxs-lookup"><span data-stu-id="57839-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="57839-108">Windows Server 2008 R2 Service Pack 1 (SP1) Standard 作業系統 (必要) 或最新的 service Pack (建議) </span><span class="sxs-lookup"><span data-stu-id="57839-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="57839-109"> (所需) 或最新的 service pack () 建議的 Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="57839-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="57839-110">Windows Server 2008 R2 （含 SP1 Datacenter 作業系統） (必要) 或最新的 service pack (建議) </span><span class="sxs-lookup"><span data-stu-id="57839-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="57839-111">Windows Server 2012 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="57839-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="57839-112">Windows Server 2012 Datacenter 作業系統</span><span class="sxs-lookup"><span data-stu-id="57839-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="57839-113">Lync Server 2013 的累計更新支援 Windows Server 2012 R2 作業系統：10月2013。</span><span class="sxs-lookup"><span data-stu-id="57839-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="57839-114">Lync Server 2013 不支援下列各項：</span><span class="sxs-lookup"><span data-stu-id="57839-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="57839-115">Windows Server 2008 R2 或 Windows Server 2012 的伺服器核心安裝選項</span><span class="sxs-lookup"><span data-stu-id="57839-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="57839-116">Windows Web Server 2008 R2 作業系統或 Windows Web Server 2012 作業系統</span><span class="sxs-lookup"><span data-stu-id="57839-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="57839-117">Windows Server 2008 R2 HPC Edition 或 Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="57839-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="57839-118">其他作業系統的系統管理工具</span><span class="sxs-lookup"><span data-stu-id="57839-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="57839-119">Lync Server 2013 預設會在執行 Lync Server 2013 的伺服器上安裝系統管理工具，但您可以在其他執行 Windows 作業系統的電腦上分別安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="57839-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="57839-120">其中包括下列的64位版本的下列作業系統，此外，除了上一節) 所述，還支援部署伺服器角色所 (的64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="57839-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="57839-121">需要 SP1 作業系統的 Windows 7 作業系統 () 或最新的 service pack (建議) </span><span class="sxs-lookup"><span data-stu-id="57839-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="57839-122">建議使用 Windows 8 作業系統或最新的 service pack () </span><span class="sxs-lookup"><span data-stu-id="57839-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="57839-123">建議使用 Windows 8.1 作業系統或最新的 service pack () </span><span class="sxs-lookup"><span data-stu-id="57839-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="57839-124">部署中其他伺服器的作業系統</span><span class="sxs-lookup"><span data-stu-id="57839-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="57839-125">如需有關後端伺服器與其他資料庫伺服器需求的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="57839-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="57839-126">如需對 Edge 部署)  (的反向 proxy 伺服器需求的詳細資訊，請參閱 [Lync Server 2013 中的 IIS 支援](lync-server-2013-iis-support.md)。</span><span class="sxs-lookup"><span data-stu-id="57839-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="57839-127">如需其他軟體需求（包括基礎結構和虛擬化支援）的詳細資訊，請參閱 [Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)中的其他主題。</span><span class="sxs-lookup"><span data-stu-id="57839-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

