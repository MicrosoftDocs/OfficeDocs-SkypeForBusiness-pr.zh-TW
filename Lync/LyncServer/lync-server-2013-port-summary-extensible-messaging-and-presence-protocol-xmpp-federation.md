---
title: 埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中的埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

針對在 Edge 伺服器部署的可擴展訊息和目前狀態通訊協定（XMPP） proxy 所定義的埠和通訊協定，允許從 XMPP 聯盟夥伴傳送到 Edge 伺服器，也可讓您從邊緣伺服器與 XMPP 進行通訊。聯盟合作夥伴。 您也可以在內部防火牆上，從前端伺服器或頂層端池中，在邊緣伺服器或 Edge 池中定義規則。

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的防火牆摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/埠</th>
<th>來源（IP 位址）</th>
<th>目的地（IP 位址）</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>每</p></td>
<td><p>Access Edge 服務介面 IP 位址</p></td>
<td><p>XMPP 的標準伺服器與伺服器通訊埠。 允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge 服務介面 IP 位址</p></td>
<td><p>每</p></td>
<td><p>XMPP 的標準伺服器與伺服器通訊埠。 允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>每</p></td>
<td><p>內部邊緣伺服器介面 IP</p></td>
<td><p>從前端伺服器或頂層池的 XMPP 閘道到 Edge 伺服器的內部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

