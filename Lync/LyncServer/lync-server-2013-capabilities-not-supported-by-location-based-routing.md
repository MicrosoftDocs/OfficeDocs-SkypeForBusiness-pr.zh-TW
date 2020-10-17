---
title: Lync Server 2013： Location-Based 路由不支援的功能
description: Lync Server 2013：不支援 Location-Based 路由的功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9cd03a8cbdd50e136605c4f172598b2ad3f523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565159"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2aa54-103">Lync Server 2013 中 Location-Based 路由不支援的功能</span><span class="sxs-lookup"><span data-stu-id="2aa54-103">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa54-104">_**主題上次修改日期：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="2aa54-104">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="2aa54-105">Location-Based 路由不適用於下列類型的互動。</span><span class="sxs-lookup"><span data-stu-id="2aa54-105">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="2aa54-106">當 Lync 端點使用這些功能與 PSTN 端點互動時，不會強制執行 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="2aa54-106">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="2aa54-107">PSTN 電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="2aa54-107">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="2aa54-108">透過回應群組的呼入和呼出 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="2aa54-108">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="2aa54-109">透過通話駐留通話駐留或檢索 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="2aa54-109">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="2aa54-110">對宣告服務的打入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="2aa54-110">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="2aa54-111">透過群組呼叫收取的打入的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="2aa54-111">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="2aa54-112">若要對下列清單中的互動類型執行 Location-Based 路由規則，您必須為會議啟用 Location-Based 路由：</span><span class="sxs-lookup"><span data-stu-id="2aa54-112">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="2aa54-113">來自會議的 PSTN 撥出</span><span class="sxs-lookup"><span data-stu-id="2aa54-113">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="2aa54-114">從對等音訊交談上報至涉及 PSTN 端點的會議</span><span class="sxs-lookup"><span data-stu-id="2aa54-114">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="2aa54-115">涉及 PSTN 端點的諮詢轉移</span><span class="sxs-lookup"><span data-stu-id="2aa54-115">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="2aa54-116">若要啟用會議的 Location-Based 路由，請參閱 [Lync Server 2013 中的會議位置基礎路由](lync-server-2013-location-based-routing-for-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="2aa54-116">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2aa54-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2aa54-117">See Also</span></span>


[<span data-ttu-id="2aa54-118">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="2aa54-118">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

