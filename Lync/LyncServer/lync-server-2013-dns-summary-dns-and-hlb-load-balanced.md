---
title: Lync Server 2013：DNS 摘要 - DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - DNS 與 HLB 負載平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

下表包含支援 DNS 負載平衡與硬體負載平衡控制器所需的 DNS 記錄摘要。 Director 的角色需要類似的 DNS 記錄做為前端伺服器。 所需的記錄數會反映在主管憑證上所需的使用中的替代名稱。 與前端伺服器不同的是，控制器池不會主持使用者帳戶或主持行動服務。

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>使用 DNS 負載平衡和硬體負載平衡器的控制器池所需的 DNS 記錄

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
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>用於複製和伺服器到伺服器的控制器主機記錄</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>主管池</p></td>
<td><p>伺服器到伺服器的 DNS 負載平衡控制器池的主機記錄</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>主管池</p></td>
<td><p>來自 Edge 伺服器內部介面的入站會話初始通訊協定（SIP）</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器泳池 HLB VIP</p></td>
<td><p>從反向 proxy 發佈的硬體負載平衡發佈的 web 服務</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器泳池 HLB VIP</p></td>
<td><p>已發佈的硬體負載平衡已公佈從反向 proxy 的 web 服務</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器泳池 HLB VIP</p></td>
<td><p>硬體負載平衡發佈，且由主管池的反向 proxy Web 入場券外部 Web 服務所定義</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

