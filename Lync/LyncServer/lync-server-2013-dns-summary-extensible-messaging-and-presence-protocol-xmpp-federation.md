---
title: DNS 摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9aa17374de29c2b7f1f144b45322d075164ab4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>DNS 摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-04-08_

若要設定可延伸訊息和顯示狀態通訊協定 (XMPP) 部署，您可以建立兩個網域名稱系統 (DNS) 記錄會將記錄解析至 Edge Server 或 Edge 集區的 [Access Edge service 的外部 DNS 伺服器中。

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和目前狀態通訊協定的 DNS 摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/連接埠</th>
<th>FQDN</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP proxy 外部介面的 Access Edge 服務或 Edge 集區。視您的 Lync 所有內部 SIP 網域重複啟用與 XMPP 連絡人的連絡人允許透過全域原則、 使用者所在的網站原則或使用者原則套用到的外部存取原則設定的位置的使用者啟用 Lync 功能的使用者。 允許的 XMPP 網域也必須設定 XMPP 同盟協力廠商原則中。 請參閱如需詳細資訊<strong>請參閱</strong>主題</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (範例)</p></td>
<td><p>IP 位址的 Access Edge service 上您的 Edge Server 或 Edge 集區裝載 XMPP proxy</p></td>
<td><p>指向 Access Edge service 或裝載 XMPP proxy 服務的 Edge 集區。 一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[設定 Lync Server 2013 中的 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)  


[決定針對 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

