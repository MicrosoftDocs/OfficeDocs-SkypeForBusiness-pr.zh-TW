---
title: Lync Server 2013：新的通話駐留應用程式功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Call Park application features
ms:assetid: bddff13c-92cc-47fd-bfd4-6e8bfbfed11b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412927(v=OCS.15)
ms:contentKeyID: 48185277
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4210eb5560563c9ef509bb6c4c5256f8b885a6e5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505330"
---
# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="ca54e-102">Lync Server 2013 中新的通話駐留應用程式功能</span><span class="sxs-lookup"><span data-stu-id="ca54e-102">New Call Park application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca54e-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="ca54e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="ca54e-104">通話駐留應用程式可讓企業語音使用者呼叫暫止，然後再從任何電話取回。</span><span class="sxs-lookup"><span data-stu-id="ca54e-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="ca54e-105">停用通話的使用者可以撥打通話保留所提供的軌道編號，以取得寄存通話，或使用外部機制（如立即訊息 (IM) 或分頁系統）來要求其他人取得通話。</span><span class="sxs-lookup"><span data-stu-id="ca54e-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="ca54e-106">Lync Server 2013 會以容錯移轉和回切處理常式的形式提供新的嚴重損壞修復機制。</span><span class="sxs-lookup"><span data-stu-id="ca54e-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="ca54e-107">當主要集區中發生中斷時，這些容錯移轉和容錯移轉程式可支援通話駐留功能的復原，方法是讓駐留在主要集區中的使用者利用備份組區的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="ca54e-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="ca54e-108">在設定及部署成對的前端集區時，會啟用通話駐留應用程式的嚴重損壞復原支援。</span><span class="sxs-lookup"><span data-stu-id="ca54e-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ca54e-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ca54e-109">See Also</span></span>


[<span data-ttu-id="ca54e-110">在 Lync Server 2013 中規劃通話駐留</span><span class="sxs-lookup"><span data-stu-id="ca54e-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

