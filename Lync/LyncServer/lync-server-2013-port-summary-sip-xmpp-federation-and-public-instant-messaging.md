---
title: 連接埠摘要-SIP，XMPP 同盟及 public instant messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8fd24bab9596f12060c87937d98cc2a57d0c887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>連接埠摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-15_

Microsoft Lync Server 2013、 Lync Server 2010 與 Office Communications Server 同盟的連接埠、 通訊協定和防火牆需求都是類似於已部署的 Edge Server。 用戶端起始與 Access Edge service 通訊，透過 TLS/SIP/TCP 443。 不過，同盟協力廠商將會引發 Access Edge service 通訊透過 MTLS/SIP/TCP 5061。

若要設定防火牆連接埠和通訊協定支援公用立即訊息連線必要，請先注意 SIP/MTLS/TCP 5061 是雙向帳戶中的公用 IM 提供者的連絡人能夠連絡 Lync 用戶端，或連絡公用 IM 連絡人的 Lync。

Windows Live Messenger 可以參與音訊/視訊通訊與 Lync 用戶端。 此帳戶，您通常會有支援外部使用者的 Lync 用戶端防火牆上非常類似防火牆連接埠和通訊協定設定。

<div>


> [!IMPORTANT]
> 多個曾經 Lync 是功能強大的工具，可將跨組織及與個人世界各地的連線。 與 Windows Live Messenger 同盟需要任何其他的使用者/裝置的授權超過 Lync 標準用戶端存取授權 (CAL)。 Skype 同盟會新增至這份清單，讓 Lync 使用者可達到數百個數百萬的人員 IM 與語音。<BR>同盟與 Messenger 用戶端連絡人最終會將正式在 2013 年 3 月 15 日，但不包括在中國大陸。 Skype 會變成先前用信差同盟用戶端的同盟使用者。



</div>

連接埠和通訊協定可延伸訊息與顯示狀態通訊協定 (XMPP) proxy 部署 Edge Server 上定義允許的 XMPP 同盟協力廠商的通訊的 Edge server，並以 XMPP 也允許來自您的 Edge Server 的通訊同盟協力廠商。 內部向防火牆從前端伺服器或前端集區到 Edge Server 或 Edge 集區上也定義規則。

<div>

## <a name="firewall-summary---sip-federation"></a>防火牆摘要-SIP 同盟


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
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Access Edge Service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火牆摘要 - 公用立即訊息連線


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
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>使用 SIP 的同盟和公用 IM 連線。</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>使用 SIP 的同盟和公用 IM 連線。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) / TCP/443</p></td>
<td><p>用戶端</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>外部使用者存取的用戶端對伺服器 SIP 流量。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>所需的 Windows Live Messenger 與公用 IM 進行連線。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>Edge Server 存取介面</p></td>
<td><p>所需的 Windows Live Messenger 與公用 IM 進行連線。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>防火牆摘要-Extensible Messaging and Presence Protocol (XMPP)


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


[Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定外部 A / V 防火牆和連接埠需求 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[管理 Lync Server 2013 中的 XMPP 同盟協力廠商](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

