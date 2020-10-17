---
title: Lync Server 2013：新主幹功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0feda45fd6c035209783d173da3a85dec3876e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505280"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="cd706-102">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="cd706-102">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd706-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cd706-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cd706-104">在 Microsoft Lync Server 2013 中，您可以定義多個轉送伺服器與閘道之間的主幹。</span><span class="sxs-lookup"><span data-stu-id="cd706-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="cd706-105">僅允許對轉送伺服器和 PSTN 閘道之間的單一主幹使用 Microsoft Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="cd706-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="cd706-106">這項功能可讓您靈活地定義其他主幹。</span><span class="sxs-lookup"><span data-stu-id="cd706-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="cd706-107">主幹是轉送伺服器 FQDN 和接聽埠與 PSTN 閘道 FQDN 和聆聽埠之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="cd706-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="cd706-108">這項新功能可讓您輕鬆地進行恢復 (的主幹定義，在此情況下，可使用多個轉送伺服器將通話路由傳送至相同的 PSTN 閘道) ，以進行 PBX 互通性，其中有多個具有不同相關原則的主幹可以在和 IP-PBX 和轉送伺服器之間使用，也就是不同網站上的轉送伺服器具有 SIP 主幹的 SIP</span><span class="sxs-lookup"><span data-stu-id="cd706-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cd706-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cd706-109">See Also</span></span>


[<span data-ttu-id="cd706-110">Lync Server 2013 中新的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="cd706-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

