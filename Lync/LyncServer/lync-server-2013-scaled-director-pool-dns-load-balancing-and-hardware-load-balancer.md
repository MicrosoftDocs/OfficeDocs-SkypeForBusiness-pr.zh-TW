---
title: 調整式 Director 集區-DNS 負載平衡與硬體負載平衡器
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
ms.openlocfilehash: d05e579d8c4a2c54342b926b34ff20bbd722524c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510970"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的調整式 Director 集區-DNS 負載平衡與硬體負載平衡器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

調整式 Director 集區，其中有一個以上的 Director 可用於處理額外的容量並提供高可用性，需要負載平衡才能將用戶端和伺服器通訊散佈至集區中的所有成員。 Director 主控 web 服務的方式很像前端集區。 若要提供負載平衡，您可以使用硬體負載平衡或網域名稱系統 (DNS) 負載平衡與硬體負載平衡。 Web 服務的硬體負載平衡是必要的，而且 DNS 負載平衡只會提供 web 服務所需的功能。

下列主題說明使用 DNS 負載平衡與硬體負載平衡一起部署 Director 集區的規劃考慮。 如果您想要使用硬體負載平衡（但不是 Director 集區的 DNS 負載平衡），請參閱 [Lync Server 2013 中的「調整式 Director 集區-硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 」，描述該拓撲的規劃需求。

![調整式 Director 集區](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "調整式 Director 集區")

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的憑證摘要-DNS 與 HLB 負載平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的埠摘要-DNS 與 HLB 負載平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要-DNS 與 HLB 負載平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

