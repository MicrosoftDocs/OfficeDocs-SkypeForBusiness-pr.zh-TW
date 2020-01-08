---
title: 埠摘要-SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-15_

使用 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行聯盟的埠、通訊協定和防火牆需求與已部署的 Edge 伺服器類似。 用戶端以 TLS/SIP/TCP 443 的存取邊緣服務啟動通訊。 但是，同盟夥伴會啟動與整個 MTLS/SIP/TCP 5061 的存取邊緣服務的通訊。

若要針對支援公用立即訊息連線的埠和通訊協定設定您的防火牆，請先注意，SIP/MTLS/TCP 5061 是雙向的，以將公用 IM 提供者的連絡人連線到 Lync 用戶端，或是 Lync 與公用 IM 連絡人聯繫。

Windows Live Messenger 可以使用 Lync 用戶端參與音訊/視頻通訊。 這個帳戶是您在防火牆上通常會有的類似防火牆埠和通訊協定設定，以支援 Lync 用戶端作為外部使用者。

<div>


> [!IMPORTANT]
> Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準用戶端存取授權（CAL）之外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。<BR>與 Messenger 用戶端連絡人的同盟將于2013年3月15日正式結束，除了中國大陸以外。 Skype 將成為先前使用 Messenger 之聯盟使用者的同盟用戶端。



</div>

針對在 Edge 伺服器部署的可擴展訊息和目前狀態通訊協定（XMPP） proxy 所定義的埠和通訊協定，允許從 XMPP 聯盟夥伴傳送到 Edge 伺服器，也可讓您從邊緣伺服器與 XMPP 進行通訊。聯盟合作夥伴。 您也可以在內部防火牆上，從前端伺服器或頂層端池中，在邊緣伺服器或 Edge 池中定義規則。

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
<th>角色/通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火牆摘要–公用立即訊息連線能力


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
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>公用 IM 連線性合作夥伴</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>針對使用 SIP 的同盟與公用 IM 連線。</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>公用 IM 連線性合作夥伴</p></td>
<td><p>針對使用 SIP 的同盟與公用 IM 連線。</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>台</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>供外部使用者存取的用戶端到伺服器 SIP 流量。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>Edge 伺服器存取介面</p></td>
<td><p>對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>防火牆摘要-可擴展的訊息和目前狀態通訊協定（XMPP）


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


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

