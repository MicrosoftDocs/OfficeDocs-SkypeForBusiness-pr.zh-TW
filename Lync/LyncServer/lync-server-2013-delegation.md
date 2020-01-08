---
title: Lync Server 2013：委派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="560cc-102">Lync Server 2013 中的委派</span><span class="sxs-lookup"><span data-stu-id="560cc-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="560cc-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="560cc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="560cc-104">Lync 中的委派功能會以下列方式受到以位置為基礎的路由影響：</span><span class="sxs-lookup"><span data-stu-id="560cc-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="560cc-105">當您為以位置為基礎的路由啟用代理人代表管理員進行呼叫時，代理人的語音原則會用來授權通話，而代理人的網站語音路由原則則將用於路由通話</span><span class="sxs-lookup"><span data-stu-id="560cc-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="560cc-106">針對主管的內送 PSTN 呼叫，適用于來電轉接或同時撥打的相同規則將按照來電轉接與轉移及同時撥打主題中的說明進行。</span><span class="sxs-lookup"><span data-stu-id="560cc-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="560cc-107">當代理人將 PSTN 端點設定為同時振鈴目標時，針對來電給 manager，就會使用與內向幹線相關的網站語音路由原則，將呼叫路由到代理人的 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="560cc-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="560cc-108">若是委派，建議管理員與他的相關委派通常位於同一個網路網站中。</span><span class="sxs-lookup"><span data-stu-id="560cc-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="560cc-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="560cc-109">See Also</span></span>


[<span data-ttu-id="560cc-110">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="560cc-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

