---
title: Lync Server 2013：委派
description: Lync Server 2013：委派。
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
ms.openlocfilehash: 6dc25d0ea3dfd64ee1b71677e6bac55c1cb1ca32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567449"
---
# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="4e76a-103">Lync Server 2013 中的委派</span><span class="sxs-lookup"><span data-stu-id="4e76a-103">Delegation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e76a-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4e76a-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4e76a-105">Lync 的委派功能會受到以下列方式 Location-Based 路由的影響：</span><span class="sxs-lookup"><span data-stu-id="4e76a-105">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="4e76a-106">啟用 Location-Based 路由的代理人代表管理員撥打電話時，代理人的語音原則會用來授權通話，並使用代理人的網站語音路由原則路由傳送通話</span><span class="sxs-lookup"><span data-stu-id="4e76a-106">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="4e76a-107">針對主管的內送 PSTN 電話，可依照通話轉接及轉接及同時響鈴的主題所述，套用適用于來電轉接或同時振鈴的相同規則。</span><span class="sxs-lookup"><span data-stu-id="4e76a-107">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="4e76a-108">當代理人將 PSTN 端點設定為同時振鈴目標時，如果是對管理員的來電，就會使用與傳入主幹相關聯之網站的語音路由原則，將通話路由傳送至代理人的 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="4e76a-108">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="4e76a-109">為了進行委派，建議管理員和其相關聯的代理人通常位於相同的網路網站。</span><span class="sxs-lookup"><span data-stu-id="4e76a-109">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4e76a-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e76a-110">See Also</span></span>


[<span data-ttu-id="4e76a-111">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="4e76a-111">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

