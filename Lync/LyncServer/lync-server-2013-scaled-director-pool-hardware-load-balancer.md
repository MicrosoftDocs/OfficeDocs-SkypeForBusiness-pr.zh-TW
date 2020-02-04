---
title: Lync Server 2013：調整式 Director 集區 - 硬體負載平衡器
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
ms.openlocfilehash: f3fc699a5d0904b3ed308928e5edec612b3af03c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的調整式 Director 集區 - 硬體負載平衡器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

已縮放的控制器池（會部署一個以上的控制器來處理額外的容量，並提供高可用性）需要負載平衡，才能將用戶端與伺服器通訊發佈至該池的所有成員。 控制器主機 web 服務的方式與前端池非常類似。 Web 服務需要硬體負載平衡。

下列主題說明使用硬體負載平衡來部署控制器池的規劃考慮。 如果您想要針對主管池使用硬體負載平衡和 DNS 負載平衡，請參閱[Lync Server 2013 中的 [縮放後的控制器池-DNS 負載平衡] 和 [硬體負載平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)]，描述該拓撲的規劃需求。

![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的連接埠摘要 - 調整式 Director 集區 (硬體負載平衡器)](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的 DNS 摘要 - 調整式 Director 集區 (硬體負載平衡器)](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

