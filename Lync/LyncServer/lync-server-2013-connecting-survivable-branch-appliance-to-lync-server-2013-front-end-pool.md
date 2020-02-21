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
ms.openlocfilehash: a148b63438710c5faf599b6053dcaf4cce7d0bad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="7b641-102">將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區</span><span class="sxs-lookup"><span data-stu-id="7b641-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b641-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="7b641-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7b641-104">每個 Survivable Branch Appliance (SBA) 相關聯的前端集區，其作為備份登錄器 SBA。</span><span class="sxs-lookup"><span data-stu-id="7b641-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="7b641-105">當 to Lync Server 2013 升級的前端集區時，SBA 必須分離從前端集區，而升級前端集區。</span><span class="sxs-lookup"><span data-stu-id="7b641-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="7b641-106">前端集區將會在升級之後，SBA 可以再重新關聯與前端集區。</span><span class="sxs-lookup"><span data-stu-id="7b641-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="7b641-107">這牽涉到在拓撲產生器中從拓撲刪除 SBA，然後再新增 SBA 到拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="7b641-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="7b641-108">使用者位於 SBA 必須移至另一個前端集區從拓撲移除 SBA 之前。</span><span class="sxs-lookup"><span data-stu-id="7b641-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="7b641-109">將 SBA 新增回拓撲之後，可以再將使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="7b641-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="7b641-110">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="7b641-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="7b641-111">移至另一個前端集區隸屬於 SBA 的分支使用者。</span><span class="sxs-lookup"><span data-stu-id="7b641-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="7b641-112">移除 SBA 從拓撲，以作為備份登錄器，切斷現有前端集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="7b641-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="7b641-113">升級至 Microsoft Lync Server 2013 的前端集區。</span><span class="sxs-lookup"><span data-stu-id="7b641-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="7b641-114">將 SBA 新增回拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b641-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="7b641-115">將 SBA 的新前端集區產生關聯作為備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="7b641-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="7b641-116">將分支使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="7b641-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b641-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7b641-117">In This Section</span></span>

  - [<span data-ttu-id="7b641-118">將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="7b641-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="7b641-119">將 Lync Server 2010 Survivable Branch Appliance 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="7b641-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

