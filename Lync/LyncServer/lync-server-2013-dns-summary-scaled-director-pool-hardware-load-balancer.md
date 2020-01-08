---
title: Lync Server 2013：DNS 摘要 - 調整式 Director 集區 (硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff76d69952d08db72e5647b58e38a43b4181c8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 調整式 Director 集區 (硬體負載平衡器)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

下表包含支援硬體負載平衡控制器所需的 DNS 記錄摘要。 Director 的角色需要類似的 DNS 記錄做為前端伺服器。 所需的記錄數會反映在主管憑證上所需的使用中的替代名稱。 與前端伺服器不同的是，控制器池不會主持使用者帳戶或主持行動服務。

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>使用硬體負載平衡器和 DNS 負載平衡的主管池所需的 DNS 記錄

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
<td><p>用於複製和伺服器與伺服器通訊的控制器主機記錄</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>控制器泳池 HLB VIP</p></td>
<td><p>DNS 負載平衡控制器池的主機記錄</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>控制器泳池 HLB VIP</p></td>
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

