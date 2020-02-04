---
title: 將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="c8e2d-102">將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區</span><span class="sxs-lookup"><span data-stu-id="c8e2d-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8e2d-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c8e2d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c8e2d-104">每個 Survivable 分支裝置（SBA）都與一個前端池相關聯，可充當 SBA 的備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="c8e2d-105">當前端池升級至 Lync Server 2013 時，必須在升級前端池時，解除與前端池的 SBA。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="c8e2d-106">在前端池升級之後，可以使用 [前端] 池 reassociated SBA。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="c8e2d-107">這涉及從拓撲建立器中的拓撲刪除 SBA，然後再將 SBA 新增到拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="c8e2d-108">在從拓撲中移除 SBA 之前，駐留在 SBA 上的使用者必須先移至另一個前端池。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="c8e2d-109">將 SBA 新增回拓撲之後，這些使用者就可以移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="c8e2d-110">下列步驟摘要如下所示：</span><span class="sxs-lookup"><span data-stu-id="c8e2d-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="c8e2d-111">將駐留在 SBA 的分支使用者移至另一個前端池。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="c8e2d-112">從拓撲中移除 SBA，以解除現有的前端池與備份註冊機構的關聯。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="c8e2d-113">將 [前端] 池升級至 [Microsoft Lync Server 2013]。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="c8e2d-114">將 SBA 新增到您的拓撲結構中。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="c8e2d-115">將新的前端池與 SBA 做為備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="c8e2d-116">將分支使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="c8e2d-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8e2d-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="c8e2d-117">In This Section</span></span>

  - [<span data-ttu-id="c8e2d-118">將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="c8e2d-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="c8e2d-119">將 Lync Server 2010 Survivable Branch Appliance 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="c8e2d-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

