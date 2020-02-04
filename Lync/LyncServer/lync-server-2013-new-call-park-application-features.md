---
title: Lync Server 2013：新通話駐留應用程式功能
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
ms.openlocfilehash: ed681497eee3033ea18cdac0487257f02052491c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="10c39-102">Lync Server 2013 中的新通話駐留應用程式功能</span><span class="sxs-lookup"><span data-stu-id="10c39-102">New Call Park application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10c39-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="10c39-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="10c39-104">通話駐留應用程式可讓企業語音使用者保留通話，稍後再從任何電話取回通話。</span><span class="sxs-lookup"><span data-stu-id="10c39-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="10c39-105">停用通話的使用者可以撥打電話寄存提供的軌道編號，以取得寄存式通話，或使用外部機制（例如立即訊息（IM）或分頁系統）來要求其他人取回通話。</span><span class="sxs-lookup"><span data-stu-id="10c39-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="10c39-106">Lync Server 2013 以容錯移轉與回切處理常式的形式提供新的災害復原機制。</span><span class="sxs-lookup"><span data-stu-id="10c39-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="10c39-107">這些容錯移轉及回切處理常式支援通話駐留功能的復原，方法是允許駐留在主要池中的使用者在主要池中發生中斷時，利用 [備份] 池的呼叫駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="10c39-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="10c39-108">已啟用通話駐留應用程式災害復原的支援，作為成對的前端池配置和部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="10c39-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="10c39-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="10c39-109">See Also</span></span>


[<span data-ttu-id="10c39-110">在 Lync Server 2013 中規劃通話駐留</span><span class="sxs-lookup"><span data-stu-id="10c39-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

