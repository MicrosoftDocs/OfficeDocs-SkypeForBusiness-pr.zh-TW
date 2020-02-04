---
title: 調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16203f7e291b7957793e71872483c93f2d1d04d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

已縮放的控制器池（已部署一個以上的控制器來處理額外的容量並提供高可用性）需要負載平衡，才能將用戶端與伺服器通訊發佈到該池的所有成員。 控制器主機 web 服務的方式與前端池非常類似。 若要提供負載平衡，您可以使用硬體負載平衡或網域名稱系統（DNS）負載平衡與硬體負載平衡。 對於 web 服務來說，硬體負載平衡是必要的，而且 DNS 負載平衡本身並不提供 web 服務所需的功能。

下列主題說明使用 DNS 負載平衡結合硬體負載平衡來部署控制器池的規劃考慮。 如果您想要使用硬體負載平衡，但不是主管池的 DNS 負載平衡，請參閱[Lync Server 2013 中的 [縮放後的控制器池-硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)]，描述該拓撲的規劃需求。

![調整式 Director 集區](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "調整式 Director 集區")

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的憑證摘要 - DNS 與 HLB 負載平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的連接埠摘要 - DNS 與 HLB 負載平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要 - DNS 與 HLB 負載平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

