---
title: Lync Server 2013： 連接埠摘要-公用立即訊息連線
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
ms.openlocfilehash: bfc057f4d41104dcebc89003ff77eb75622ee3c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>連接埠摘要-公用立即訊息 [Lync Server 2013 中的連線能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-16_

若要設定防火牆連接埠和通訊協定支援公用立即訊息連線必要，請先注意 SIP/MTLS/TCP 5061 是雙向帳戶中的公用 IM 提供者的連絡人能夠連絡 Lync 用戶端，或連絡公用 IM 連絡人的 Lync。

Windows Live Messenger 可以參與音訊/視訊通訊與 Lync 用戶端。 此帳戶，您通常會有支援外部使用者的 Lync 用戶端防火牆上非常類似防火牆連接埠和通訊協定設定。

<div>


> [!IMPORTANT]  
> 多個曾經 Lync 是功能強大的工具，可將跨組織及與個人世界各地的連線。 與 Windows Live Messenger 同盟需要任何其他的使用者/裝置的授權超過 Lync 標準用戶端存取授權 (CAL)。 Skype 同盟會新增至這份清單，讓 Lync 使用者可達到數百個數百萬的人員 IM 與語音。<BR>同盟與 Messenger 用戶端連絡人最終會將正式在 2013 年 3 月 15 日，但不包括在中國大陸。 Skype 會變成先前用信差同盟用戶端的同盟使用者。



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

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定外部 A / V 防火牆和連接埠需求 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

