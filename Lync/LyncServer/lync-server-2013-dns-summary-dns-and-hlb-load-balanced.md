---
title: Lync Server 2013： DNS 摘要-DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532150"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-DNS 與 HLB 負載平衡

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

下表包含支援 DNS 負載平衡與硬體負載平衡 Director 所需之 DNS 記錄的摘要。 Director 的角色需要與前端伺服器類似的 DNS 記錄。 所需的記錄數目會反映在 Director 憑證所需的主體替代名稱中。 與前端伺服器不同的是，Director 集區不會主控使用者帳戶或主控行動性服務。

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>使用 DNS 負載平衡與硬體負載平衡器之 Director 集區所需的 DNS 記錄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>FQDN/DNS 記錄</th>
<th>IP 位址/FQDN</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>用於複寫和伺服器對伺服器的 Director 主機記錄</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Director pool</p></td>
<td><p>伺服器至伺服器之 DNS 負載平衡 Director 集區的主機記錄</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director pool</p></td>
<td><p>來自 Edge Server 內部介面的輸入會話初始通訊協定 (SIP) </p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director 集區 HLB VIP</p></td>
<td><p>來自反向 Proxy 的硬體負載平衡發行撥入式 Web 服務</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director 集區 HLB VIP</p></td>
<td><p>來自反向 Proxy 的硬體負載平衡發行會議 Web 服務</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director 集區 HLB VIP</p></td>
<td><p>針對 Director 集區的反向 proxy Web 票證外部 Web 服務發行及定義的硬體負載平衡</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

