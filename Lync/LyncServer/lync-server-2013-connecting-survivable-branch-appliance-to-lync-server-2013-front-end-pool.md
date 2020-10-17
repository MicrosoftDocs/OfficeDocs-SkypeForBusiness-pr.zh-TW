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
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502020"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="b701b-102">將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區</span><span class="sxs-lookup"><span data-stu-id="b701b-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b701b-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b701b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b701b-104">每個 Survivable Branch 裝置 (SBA) 都與前端集區相關聯，以充當 SBA 的備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="b701b-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="b701b-105">當前端集區升級至 Lync Server 2013 時，當前端集區升級時，SBA 必須與前端集區解除關聯。</span><span class="sxs-lookup"><span data-stu-id="b701b-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="b701b-106">在升級前端集區之後，即可使用前端集區 reassociated SBA。</span><span class="sxs-lookup"><span data-stu-id="b701b-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="b701b-107">這牽涉到在拓撲產生器中從拓撲刪除 SBA，然後再新增 SBA 到拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="b701b-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="b701b-108">位於 SBA 上的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="b701b-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="b701b-109">將 SBA 新增回拓撲之後，可以再將使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="b701b-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="b701b-110">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="b701b-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="b701b-111">將位於 SBA 的分支使用者移至另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="b701b-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="b701b-112">從拓撲移除 SBA，以解除現有前端集區與備份註冊機的關聯。</span><span class="sxs-lookup"><span data-stu-id="b701b-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="b701b-113">將前端集區升級至 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b701b-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="b701b-114">將 SBA 新增回拓撲。</span><span class="sxs-lookup"><span data-stu-id="b701b-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="b701b-115">將新的前端集區與 SBA 做為備份註冊機關聯。</span><span class="sxs-lookup"><span data-stu-id="b701b-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="b701b-116">將分支使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="b701b-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b701b-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b701b-117">In This Section</span></span>

  - [<span data-ttu-id="b701b-118">將 Lync Server 2013 Survivable 分支裝置分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="b701b-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="b701b-119">將 Lync Server 2010 Survivable 分支裝置分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="b701b-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

