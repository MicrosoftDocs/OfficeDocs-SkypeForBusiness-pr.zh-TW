---
title: Lync Server 2013： 委派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9d9f5473f94f093d92cce1b4664f54d6f32430d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="6510f-102">Lync Server 2013 中的委派</span><span class="sxs-lookup"><span data-stu-id="6510f-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6510f-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="6510f-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="6510f-104">在 Lync 中的委派功能都受到位置型的路由，以下列方式：</span><span class="sxs-lookup"><span data-stu-id="6510f-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="6510f-105">當委派啟用位置型路由 places 代表管理員在呼叫時，代理人的語音原則用來授權通話和代理人的站台語音路由原則會用來路由傳送來電</span><span class="sxs-lookup"><span data-stu-id="6510f-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="6510f-106">傳入 PSTN 通話的管理員，適用於相同規則來電轉接或同時響鈴會套用在來電轉接和轉寄和 Simultaneous 響鈴主題所述。</span><span class="sxs-lookup"><span data-stu-id="6510f-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="6510f-107">當委派設定 PSTN 端點做為管理員] 中的內送呼叫的同時響鈴目標給傳入主幹相關聯之網站的語音路由原則將用來將呼叫路由至代理人的 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="6510f-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="6510f-108">委派，建議您，主管和其相關聯的代理人，通常位於相同的網路網站。</span><span class="sxs-lookup"><span data-stu-id="6510f-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6510f-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6510f-109">See Also</span></span>


[<span data-ttu-id="6510f-110">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="6510f-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

