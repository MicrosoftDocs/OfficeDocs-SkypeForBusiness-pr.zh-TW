---
title: Lync Server 2013：埠摘要-單一 Director
description: Lync Server 2013：埠摘要-單一 Director。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566369"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-單一 Director

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

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
<td><p>Director</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到 Director 和前端伺服器 web 服務</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向 Proxy 內部介面</p></td>
<td><p>Director</p></td>
<td><p>從反向 proxy 的外部端開始，通訊會傳送到 Director 和前端伺服器 web 服務</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>前端伺服器或前端集區</p></td>
<td><p>Director 與前端伺服器之間的伺服器間通訊</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director web 服務</p></td>
<td><p>Director 為內部及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>內部用戶端</p></td>
<td><p>Director web 服務</p></td>
<td><p>Director 為內部及外部用戶端提供 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Director</p></td>
<td><p>從 Edge Server 到 Director 和前端伺服器的 SIP 通訊。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

