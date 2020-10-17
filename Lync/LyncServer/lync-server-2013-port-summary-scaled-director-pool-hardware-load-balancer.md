---
title: Lync Server 2013：埠摘要-調整式 Director 集區（硬體負載平衡器）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91c1970b85b5b0c76174dfbc9d6dcec9ac24cc4d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534060"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-調整式 Director 集區（硬體負載平衡器）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

Director 集區的防火牆埠需求包含的埠，用來從 Edge Server 的內部介面或反向 proxy 的內部介面，建立與 Director 的通訊。 Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。 此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。 SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。 一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>適用於防火牆的 Director 連接埠和通訊協定定義

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端伺服器或前端集區</p></td>
<td><p>Director HLB VIP 與前端伺服器之間的伺服器間通訊</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>Director 為內部及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>Director 為內部及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>從 Edge Server 到 Director 和前端伺服器的 SIP 通訊。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

