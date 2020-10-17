---
title: Lync Server 2013：開發備份與還原策略及規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Developing a backup and restoration strategy and plan
ms:assetid: 17599b76-1a84-4dd6-b695-c19637deb8a6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202164(v=OCS.15)
ms:contentKeyID: 51541447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d60ab06ec2367b9cd88f85ce0e0e85decad71c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522520"
---
# <a name="developing-a-backup-and-restoration-strategy-and-plan-for-lync-server-2013"></a><span data-ttu-id="36cfb-102">開發 Lync Server 2013 的備份與還原策略及規劃</span><span class="sxs-lookup"><span data-stu-id="36cfb-102">Developing a backup and restoration strategy and plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36cfb-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="36cfb-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="36cfb-104">您的 Lync Server 備份和還原作業的效能取決於您的備份與還原策略及規劃。</span><span class="sxs-lookup"><span data-stu-id="36cfb-104">The effectiveness of your Lync Server backup and restoration operations depends on your backup and restoration strategy and plan.</span></span> <span data-ttu-id="36cfb-105">您應該建立一個策略，以備份及還原與組織的整體策略相符的 Lync Server，以及備份資料和設定的完整、簡明計畫，而且在中斷時，是要還原服務的計畫。</span><span class="sxs-lookup"><span data-stu-id="36cfb-105">You should establish a strategy for backing up and restoring Lync Server that fits with your organization's overall strategy, and a comprehensive, concise plan for backing up data and settings, and, in the event of an outage, a plan for restoring service.</span></span>

<span data-ttu-id="36cfb-106">如需最強健的前端集區災難復原，請使用 Lync Server 2013 中所引進的配對集區嚴重損壞修復拓撲。</span><span class="sxs-lookup"><span data-stu-id="36cfb-106">For the most robust disaster recovery of a Front End Pool, use the paired-pool disaster recovery topology introduced in Lync Server 2013.</span></span> <span data-ttu-id="36cfb-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="36cfb-107">For more information, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36cfb-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="36cfb-108">In This Section</span></span>

  - [<span data-ttu-id="36cfb-109">建立 Lync Server 2013 的備份與還原策略</span><span class="sxs-lookup"><span data-stu-id="36cfb-109">Establishing a backup and restoration strategy for Lync Server 2013</span></span>](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)

  - [<span data-ttu-id="36cfb-110">建立 Lync Server 2013 的備份與還原方案</span><span class="sxs-lookup"><span data-stu-id="36cfb-110">Establishing a backup and restoration plan for Lync Server 2013</span></span>](lync-server-2013-establishing-a-backup-and-restoration-plan.md)

  - [<span data-ttu-id="36cfb-111">設定 Lync Server 2013 的備份位置</span><span class="sxs-lookup"><span data-stu-id="36cfb-111">Setting up a backup location for Lync Server 2013</span></span>](lync-server-2013-setting-up-a-backup-location.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

