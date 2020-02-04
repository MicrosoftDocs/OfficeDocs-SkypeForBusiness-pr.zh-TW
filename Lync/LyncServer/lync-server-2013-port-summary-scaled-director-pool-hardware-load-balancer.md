---
title: Lync Server 2013：連接埠摘要 - 調整式 Director 集區 (硬體負載平衡器)
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
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要 - 調整式 Director 集區 (硬體負載平衡器)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

控制器池的防火牆埠需求是由用來從邊緣伺服器內部介面或反向 proxy 的內部介面中與控制器建立通訊的埠。 Microsoft Lync Server 2013 預設會要求將埠 HTTP/TCP 8080 和 HTTPS/TCP 4443 從反向 proxy 開啟至控制器，以及前端池和前端伺服器。 此外，您必須從 Edge 伺服器內部介面將會話初始通訊協定（SIP）與主管及前端池和前端伺服器進行通訊。 SIP 通訊協定會將 SIP/MTLS/TCP 5061 從 Edge 伺服器使用到前端池和前端伺服器。 您也必須建立一個規則，讓來自 Director、前端池和前端伺服器的 SIP/MTLS/TCP 5061 通訊也必須建立。

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>防火牆定義的控制器埠和通訊協定

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>反向 proxy 內部介面</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 與前端伺服器 web 服務</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 proxy 內部介面</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 與前端伺服器 web 服務</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端伺服器或前端池</p></td>
<td><p>控制器 HLB VIP 與前端伺服器之間的伺服器間通訊</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>內部用戶端</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>控制器為內部和外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>內部用戶端</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>控制器為內部和外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>從邊緣伺服器到控制器的 SIP 通訊，以及前端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>每</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>每</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>每</p></td>
<td><p>Director</p></td>
<td><p>集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

