---
title: Lync Server 2013：連接埠摘要 - DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要 - DNS 與 HLB 負載平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

單一控制器的防火牆埠需求是由用來從內部介面或反向 proxy 的內部介面網路與主管建立通訊的埠。 Microsoft Lync Server 2013 預設會要求將埠 HTTP/TCP 8080 和 HTTPS/TCP 4443 從反向 proxy 開啟至控制器，以及前端池和前端伺服器。 此外，您必須從 Edge 伺服器內部介面將會話初始通訊協定（SIP）與主管及前端池和前端伺服器進行通訊。 SIP 通訊協定會將 SIP/MTLS/TCP 5061 從 Edge 伺服器使用到前端池和前端伺服器。 您也必須建立一個規則，讓來自 Director、前端池和前端伺服器的 SIP/MTLS/TCP 5061 通訊也必須建立。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>針對防火牆定義的單一控制器埠和通訊協定

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
<td><p>從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 和前端伺服器 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 proxy 內部介面</p></td>
<td><p>控制器硬體負載平衡器 VIP</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 和前端伺服器 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端池或前端伺服器</p></td>
<td><p>控制器 HLB VIP 與前端伺服器或前端伺服器之間的伺服器間通訊。</p></td>
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
<td><p>Director</p></td>
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

