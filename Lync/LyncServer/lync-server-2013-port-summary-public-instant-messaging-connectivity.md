---
title: Lync Server 2013：埠摘要-公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>埠摘要-Lync Server 2013 中的公用立即訊息連線能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-16_

若要針對支援公用立即訊息連線的埠和通訊協定設定您的防火牆，請先注意，SIP/MTLS/TCP 5061 是雙向的，以將公用 IM 提供者的連絡人連線到 Lync 用戶端，或是 Lync 與公用 IM 連絡人聯繫。

Windows Live Messenger 可以使用 Lync 用戶端參與音訊/視頻通訊。 這個帳戶是您在防火牆上通常會有的類似防火牆埠和通訊協定設定，以支援 Lync 用戶端作為外部使用者。

<div>


> [!IMPORTANT]  
> Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準用戶端存取授權（CAL）之外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。<BR>與 Messenger 用戶端連絡人的同盟將于2013年3月15日正式結束，除了中國大陸以外。 Skype 將成為先前使用 Messenger 之聯盟使用者的同盟用戶端。



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

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

