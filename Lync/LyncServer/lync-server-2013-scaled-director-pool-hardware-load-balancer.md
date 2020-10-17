---
title: Lync Server 2013：調整式 Director 集區-硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c812f1276a4f8ac9a23298e3b747e9ba97085378
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510950"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的調整式 Director 集區-硬體負載平衡器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

調整式 Director 集區，其中有多個 Director 可用於處理其他容量並提供高可用性，需要負載平衡才能將用戶端和伺服器通訊散佈至集區中的所有成員。 Director 主控 web 服務的方式很像前端集區。 Web 服務需要硬體負載平衡。

下列主題說明使用硬體負載平衡來部署 Director 集區的規劃考慮。 如果您想要使用硬體負載平衡及 Director 集區的 DNS 負載平衡，請參閱 [Lync Server 2013 中的「調整式 Director 集區-DNS 負載平衡與硬體負載平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) 」，描述該拓撲的規劃需求。

![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的憑證摘要-調整式 Director 集區（硬體負載平衡器）](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的埠摘要-調整式 Director 集區（硬體負載平衡器）](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的 DNS 摘要-調整式 Director 集區（硬體負載平衡器）](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

