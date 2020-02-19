---
title: Lync Server 2013： 連接埠摘要-DNS 與 HLB 負載平衡
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
ms.openlocfilehash: b6c58a9b2e4932087945322db0bd8980191c7c5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要-DNS 與 HLB 負載平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

單一 Director 的防火牆連接埠需求是由用來建立從內部介面或反向 proxy 內部面向網路 Director 與通訊的連接埠所組成。 預設的 Microsoft Lync Server 2013 所預期的 HTTP/TCP 8080 和 HTTPS/TCP 4443 指向 Director，開啟從反向 proxy 的連接埠以及前端集區與前端伺服器。 此外，必須是工作階段初始通訊協定 (SIP) 通訊的 Edge Server 內部介面從指向 Director 與前端集區和前端伺服器。 SIP 通訊協定使用 SIP/MTLS/TCP 5061 從 Edge Server 至前端集區與前端伺服器。 也必須建立允許 SIP/MTLS/TCP 5061 通訊來自 Director、 前端集區與前端伺服器到 Edge Server 內部介面的規則。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>單一 Director 連接埠和防火牆定義的通訊協定

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
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director 的硬體負載平衡器 VIP</p></td>
<td><p>先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 與前端伺服器 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director 的硬體負載平衡器 VIP</p></td>
<td><p>先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 與前端伺服器 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端集區或前端伺服器</p></td>
<td><p>Director HLB VIP 與前端伺服器或前端伺服器之間的伺服器間通訊。</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director 的硬體負載平衡器 VIP</p></td>
<td><p>Director 內部以及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director 的硬體負載平衡器 VIP</p></td>
<td><p>Director 內部以及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Director</p></td>
<td><p>從 SIP 通訊 Edge Server Director，以及前端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Director</p></td>
<td><p>Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

