---
title: Lync Server 2013：媒體旁路的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f59e0c025935ca8c2cd341549cdb58a44e7dbb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="5de45-102">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="5de45-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de45-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5de45-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5de45-104">針對每個 PSTN 呼叫，中繼伺服器會決定是否可以直接將來自 Lync 端點的媒體傳送到中繼伺服器對等，而不需要遍歷轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="5de45-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="5de45-105">對等可以是網際網路電話服務提供者（ITSP）上的 PSTN 閘道、IP PBX 或會話邊界控制器（SBC），與呼叫路由的中繼伺服器之間的主幹產生關聯。</span><span class="sxs-lookup"><span data-stu-id="5de45-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="5de45-106">當符合下列需求時，可以使用「媒體旁路」：</span><span class="sxs-lookup"><span data-stu-id="5de45-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="5de45-107">中繼伺服器對等必須支援媒體略過所需的功能，最重要的是處理多個分叉回應（稱為「早期對話方塊」）。</span><span class="sxs-lookup"><span data-stu-id="5de45-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="5de45-108">請與您的閘道或 PBX 製造商或您的 ITSP，以取得閘道、PBX 或 SBC 可接受的最大早期對話方塊數量詞。</span><span class="sxs-lookup"><span data-stu-id="5de45-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="5de45-109">中繼伺服器對等必須直接從 Lync 端點接受媒體流量。</span><span class="sxs-lookup"><span data-stu-id="5de45-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="5de45-110">許多 ITSPs 只允許其 SBC 接收來自中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="5de45-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="5de45-111">請與您的 ITSP，以判斷其 SBC 是否直接從 Lync 端點接受媒體流量。</span><span class="sxs-lookup"><span data-stu-id="5de45-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="5de45-112">Lync 用戶端和中繼伺服器對等都必須有良好的連線，這表示它們要麼位於相同的網路區域，或是在連線到區域的網路網站上，這些連結都沒有頻寬限制</span><span class="sxs-lookup"><span data-stu-id="5de45-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5de45-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="5de45-113">See Also</span></span>


[<span data-ttu-id="5de45-114">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="5de45-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="5de45-115">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="5de45-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

