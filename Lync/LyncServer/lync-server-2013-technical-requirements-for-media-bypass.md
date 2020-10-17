---
title: Lync Server 2013：媒體旁路的技術需求
description: Lync Server 2013：媒體旁路的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559439"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d918e-103">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="d918e-103">Technical requirements for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d918e-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d918e-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d918e-105">在每次呼叫 PSTN 時，轉送伺服器會判斷從來源的 Lync 端點媒體是否可以直接傳送給轉送伺服器對等，而不需遍歷轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="d918e-105">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="d918e-106">對等可以是 PSTN 閘道、IP-PBX 或網際網路電話服務提供者 (ITSP) 上的工作階段邊界控制器 (SBC) 與路由通話之中繼伺服器之間的主幹關聯。</span><span class="sxs-lookup"><span data-stu-id="d918e-106">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="d918e-107">符合下列需求時，可以使用媒體旁路：</span><span class="sxs-lookup"><span data-stu-id="d918e-107">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="d918e-108">轉送伺服器對等必須支援媒體旁路所需的功能，最重要的是處理多個分叉回應 (稱為「早期對話方塊」 ) 。</span><span class="sxs-lookup"><span data-stu-id="d918e-108">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="d918e-109">請連絡閘道或 PBX 製造商或是 ITSP，以取得閘道、PBX 或 SBC 可以接受的早期對話數上限值。</span><span class="sxs-lookup"><span data-stu-id="d918e-109">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="d918e-110">轉送伺服器對等必須直接接受來自 Lync 端點的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="d918e-110">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="d918e-111">許多 ITSPs 都允許其 SBC 只從轉送伺服器接收流量。</span><span class="sxs-lookup"><span data-stu-id="d918e-111">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="d918e-112">請與您的 ITSP 聯繫，以判斷其 SBC 是否直接接受來自 Lync 端點的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="d918e-112">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="d918e-113">Lync 用戶端和轉送伺服器對等必須已正確連接，這表示它們位於相同網路地區或網路網站，這些連結是以沒有頻寬限制的 WAN 連結連線至區域。</span><span class="sxs-lookup"><span data-stu-id="d918e-113">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d918e-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d918e-114">See Also</span></span>


[<span data-ttu-id="d918e-115">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="d918e-115">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="d918e-116">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="d918e-116">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

