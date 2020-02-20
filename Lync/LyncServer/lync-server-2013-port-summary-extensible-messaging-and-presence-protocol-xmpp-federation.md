---
title: 連接埠摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>連接埠摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

連接埠和通訊協定可延伸訊息與顯示狀態通訊協定 (XMPP) proxy 部署 Edge Server 上定義允許的 XMPP 同盟協力廠商的通訊的 Edge server，並以 XMPP 也允許來自您的 Edge Server 的通訊同盟協力廠商。 內部向防火牆從前端伺服器或前端集區到 Edge Server 或 Edge 集區上也定義規則。

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Extensible Messaging and Presence Protocol 的防火牆摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 (IP 位址)</th>
<th>目的地 (IP 位址)</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>Access Edge service 介面 IP 位址</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge service 介面 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任何</p></td>
<td><p>內部 Edge Server 介面 IP</p></td>
<td><p>內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道至 Edge Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 – 與 Google Talk 的 XMPP 同盟中 XMPP 設定範例](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[管理 Lync Server 2013 中的 XMPP 同盟協力廠商](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

