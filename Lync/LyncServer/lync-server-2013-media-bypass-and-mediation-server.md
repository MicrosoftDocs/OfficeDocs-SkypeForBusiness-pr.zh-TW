---
title: Lync Server 2013： 媒體旁路和中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d346948fc40298f7825a2d141432583a1c2e08
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="d81d3-102">媒體旁路和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d81d3-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d81d3-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="d81d3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d81d3-104">媒體旁路的 Lync Server 功能，可讓系統管理員設定通話路由傳送至使用者的端點與公用交換的電話網路 (PSTN) 閘道之間的直接流通而周遊中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d81d3-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="d81d3-105">媒體旁路能改善通話品質以減少延遲、 不需要轉譯、 封包遺失的可能性和潛在的失敗點的數目。</span><span class="sxs-lookup"><span data-stu-id="d81d3-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="d81d3-106">媒體旁路其中沒有中繼伺服器的遠端網站透過一或多個與頻寬限制的 WAN 連結連接至中央網站，以啟用媒體直接流向本地閘道不在遠端站台的用戶端降低頻寬需求第一次不必流程跨 WAN 連結至中央網站中繼伺服器和備份。此減少的媒體處理也補充控制多個閘道中繼伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="d81d3-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="d81d3-107">媒體旁路和通話許可控制 (CAC) 都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="d81d3-107">Media bypass and call admission control (CAC) are mutually exclusive.</span></span> <span data-ttu-id="d81d3-108">如果採用媒體旁路的通話，則不會該通話的執行 CAC。</span><span class="sxs-lookup"><span data-stu-id="d81d3-108">If media bypass is employed for a call, CAC is not performed for that call.</span></span> <span data-ttu-id="d81d3-109">假設是沒有頻寬限制連結參與通話。</span><span class="sxs-lookup"><span data-stu-id="d81d3-109">The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d81d3-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d81d3-110">See Also</span></span>


[<span data-ttu-id="d81d3-111">通話許可控制和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d81d3-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="d81d3-112">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="d81d3-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

