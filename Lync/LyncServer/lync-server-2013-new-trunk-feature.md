---
title: Lync Server 2013： 新主幹功能
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
ms.openlocfilehash: 693b228eb0065375bd01cb9eedabed46ec1833a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="fd0ea-102">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="fd0ea-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd0ea-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="fd0ea-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fd0ea-104">在 Microsoft Lync Server 2013 中，您可以定義中繼伺服器和閘道之間的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="fd0ea-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="fd0ea-105">Microsoft Lync Server 2010 只允許單一中繼伺服器和 PSTN 閘道之間主幹。</span><span class="sxs-lookup"><span data-stu-id="fd0ea-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="fd0ea-106">這項功能提供的彈性來定義其他主幹。</span><span class="sxs-lookup"><span data-stu-id="fd0ea-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="fd0ea-107">主幹是邏輯之間的關聯性中繼伺服器 FQDN 和聆聽連接埠與 PSTN 閘道 FQDN 的聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="fd0ea-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="fd0ea-108">這項新功能可讓簡單主幹定義恢復能力 （其中多部中繼伺服器可用來將通話路由傳送至相同的 PSTN 閘道），PBX 交互操作性，之間可以使用多個主幹與不同相關聯的原則和IP PBX 和中繼伺服器，以及在不同站台的中繼伺服器必須參照相同電訊廠商 FQDN 電訊廠商 SIP 主幹的位置的 SIP 主幹組態。</span><span class="sxs-lookup"><span data-stu-id="fd0ea-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fd0ea-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd0ea-109">See Also</span></span>


[<span data-ttu-id="fd0ea-110">Lync Server 2013 中的新 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="fd0ea-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

