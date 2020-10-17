---
title: Lync Server 2013：埠摘要-DNS 與 HLB 負載平衡
description: Lync Server 2013：埠摘要-DNS 與 HLB 負載平衡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543129"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-DNS 與 HLB 負載平衡

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

單一 Director 的防火牆埠需求包含用於從反向 proxy 的內部介面或內部的網路與 Director 建立通訊的埠。 Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。 此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。 SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。 一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>防火牆定義的單一 Director 埠和通訊協定

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
<td><p>由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director 硬體負載平衡器 VIP</p></td>
<td><p>由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端集區或前端伺服器</p></td>
<td><p>Director HLB VIP 和前端伺服器或前端伺服器之間的伺服器間通訊。</p></td>
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
<td><p>Director</p></td>
<td><p>從 Edge Server 到 Director 及前端伺服器的 SIP 通訊。</p></td>
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

