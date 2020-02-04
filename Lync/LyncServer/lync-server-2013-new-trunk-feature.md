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
ms.openlocfilehash: 962da42567ffcc1c0d541b74266ac5bb1b4653c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="e7363-102">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="e7363-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7363-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e7363-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e7363-104">在 Microsoft Lync Server 2013 中，可以定義在中繼伺服器和閘道之間的多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="e7363-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="e7363-105">Microsoft Lync Server 2010 只允許在中繼伺服器與 PSTN 閘道之間的單一主幹中使用。</span><span class="sxs-lookup"><span data-stu-id="e7363-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="e7363-106">這個功能提供了定義其他 trunks 的彈性。</span><span class="sxs-lookup"><span data-stu-id="e7363-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="e7363-107">主幹是中繼伺服器 FQDN 與偵聽埠與 PSTN 閘道 FQDN 與偵聽埠之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="e7363-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="e7363-108">這項新功能可讓您輕鬆地進行復原（多個轉送伺服器可用於將呼叫路由至同一個 PSTN 閘道），以進行 PBX 互通性，在與之間可以使用多個具有不同關聯原則的 trunks。IP-PBX 與中繼伺服器，以及適用于不同網站的中繼伺服器將 SIP trunks 給同一個運營商 FQDN 所參照之載波的 SIP 幹線配置。</span><span class="sxs-lookup"><span data-stu-id="e7363-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e7363-109">請參閱</span><span class="sxs-lookup"><span data-stu-id="e7363-109">See Also</span></span>


[<span data-ttu-id="e7363-110">Lync Server 2013 中的新企業語音功能</span><span class="sxs-lookup"><span data-stu-id="e7363-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

