---
title: Lync Server 2013：媒體旁路和中繼伺服器
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
ms.openlocfilehash: bf57bd94925ef5337656afc1b7cf4aa1ebc8ab17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="4d1fe-102">Lync Server 2013 中的媒體旁路和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4d1fe-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1fe-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4d1fe-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4d1fe-104">[媒體旁路] 是一種 Lync 伺服器功能，可讓系統管理員將呼叫路由設定為直接在使用者端點與公用交換電話網絡（PSTN）閘道之間流動，而不需要遍歷中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="4d1fe-105">媒體旁路可減少延遲、不必要的翻譯、資料包遺失的可能性，以及潛在的故障點數，以改善通話品質。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="4d1fe-106">如果不含轉送伺服器的遠端網站是透過受限制頻寬的一個或多個 WAN 連結連線到中央網站，則媒體略過減少頻寬需求，只要從遠端網站上的用戶端啟用媒體，就能直接流向本機閘道，而不需要首先，必須在中央網站和返回轉送伺服器的 WAN 連結之間流動。媒體處理的減少也會補充轉送伺服器控制多個閘道的能力。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="4d1fe-107">[媒體旁路] 和 [通話許可控制] （CAC）是互斥的。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-107">Media bypass and call admission control (CAC) are mutually exclusive.</span></span> <span data-ttu-id="4d1fe-108">如果在通話中使用媒體旁路，就不會針對該通話執行 CAC。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-108">If media bypass is employed for a call, CAC is not performed for that call.</span></span> <span data-ttu-id="4d1fe-109">假設通話中沒有受限制頻寬的連結。</span><span class="sxs-lookup"><span data-stu-id="4d1fe-109">The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d1fe-110">請參閱</span><span class="sxs-lookup"><span data-stu-id="4d1fe-110">See Also</span></span>


[<span data-ttu-id="4d1fe-111">Lync Server 2013 中的通話許可控制和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4d1fe-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="4d1fe-112">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4d1fe-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

