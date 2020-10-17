---
title: 埠摘要-SIP、XMPP 同盟和公用立即訊息
description: 埠摘要-SIP、XMPP 同盟和公用立即訊息。
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
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566352"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-15_

與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器同盟相關的埠、通訊協定及防火牆需求，類似于已部署的 Edge Server。 用戶端會透過 TLS/SIP/TCP 443，與 Access Edge service 發起通訊。 同盟合作夥伴但是會透過 MTLS/SIP/TCP 5061，發起與 Access Edge service 的通訊。

若要為您的防火牆設定支援公用立即訊息連線所需的埠和通訊協定，請先注意 SIP/MTLS/TCP 5061 是雙向的，可讓公用 IM 提供者中的連絡人能夠聯繫 Lync 用戶端，或與 Lync 聯繫以取得公用 IM 連絡人。

Windows Live Messenger 可以與 Lync 用戶端參與音訊/視頻通訊。 這會針對一般具有防火牆的防火牆埠和通訊協定設定，以支援 Lync 用戶端的外部使用者使用。

<div>


> [!IMPORTANT]
> Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟除了 Lync Standard Client Access License (CAL) 之外，不需要額外的使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。<BR>與 Messenger 用戶端連絡人的同盟會在2013年3月15日（中國大陸除外）正式結束。 Skype 會成為先前使用信使的同盟使用者的同盟用戶端。



</div>

在 Edge Server 上部署的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy 所定義的埠和通訊協定，允許從 XMPP 同盟協力廠商到 Edge Server 的通訊，也允許從 Edge Server 到 XMPP 同盟合作夥伴的通訊。 規則也會定義在內部的防火牆上，從前端伺服器或前端集區到 Edge Server 或 Edge 集區。

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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>適用于使用 SIP 的同盟與公用 IM 連線。</p></td>
</tr>
<tr class="even">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>適用于使用 SIP 的同盟與公用 IM 連線。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>用戶端</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>外部使用者存取的用戶端對伺服器 SIP 流量。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>Edge Server Access 介面</p></td>
<td><p>使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>防火牆摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 


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
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Access Edge service 介面 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任何</p></td>
<td><p>內部 Edge Server 介面 IP</p></td>
<td><p>從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 的內部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[在 Lync Server 2013 中管理 XMPP 同盟協力廠商](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

