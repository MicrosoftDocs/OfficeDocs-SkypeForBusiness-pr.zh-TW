---
title: 調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器
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
ms.openlocfilehash: e36cb2036a15dd18263e8714a10122b76aaebace
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

調整式的 Director 集區，其中有一個以上的 Director 部署處理更大的容量，並提供高可用性，需要負載平衡來發佈至的集區的所有成員的用戶端和伺服器通訊。 Director 主機 web 服務非常類似的前端集區。 若要提供負載平衡，您可以使用任一硬體負載平衡或網域名稱系統 (DNS) 負載平衡與硬體負載平衡。 硬體負載平衡需要的 web 服務，且 DNS 負載平衡單獨不提供的 web 服務所需的功能。

下列主題說明部署 Director 集區使用 DNS 負載平衡搭配硬體負載平衡的規劃考量。 如果您想要使用硬體負載平衡，但不是 DNS 負載平衡 Director 集區，請參閱[調整式 Director 集區-硬體負載平衡器 Lync Server 2013 中](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)的主題會說明該拓撲的規劃需求。

![調整式 Director 集區](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "調整式 Director 集區")

<div>

## <a name="in-this-section"></a>本章節內容

  - [憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的連接埠摘要-DNS 與 HLB 負載平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要-DNS 與 HLB 負載平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

