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
ms.openlocfilehash: 8bce3413e7e41e3784cb0ba300c621a7c042b618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534160"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-公用立即訊息連線

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-16_

若要為您的防火牆設定支援公用立即訊息連線所需的埠和通訊協定，請先注意 SIP/MTLS/TCP 5061 是雙向的，可讓公用 IM 提供者中的連絡人能夠聯繫 Lync 用戶端，或與 Lync 聯繫以取得公用 IM 連絡人。

Windows Live Messenger 可以與 Lync 用戶端參與音訊/視頻通訊。 這會針對一般具有防火牆的防火牆埠和通訊協定設定，以支援 Lync 用戶端的外部使用者使用。

<div>


> [!IMPORTANT]  
> Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟除了 Lync Standard Client Access License (CAL) 之外，不需要額外的使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。<BR>與 Messenger 用戶端連絡人的同盟會在2013年3月15日（中國大陸除外）正式結束。 Skype 會成為先前使用信使的同盟使用者的同盟用戶端。



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

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

