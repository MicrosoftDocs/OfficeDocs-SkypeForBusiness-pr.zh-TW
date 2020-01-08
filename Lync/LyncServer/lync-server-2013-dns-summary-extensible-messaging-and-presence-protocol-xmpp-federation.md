---
title: DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中的 DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-08_

若要為您的部署設定可擴展的訊息和目前狀態通訊協定（XMPP），您可以在外部 DNS 伺服器中建立兩個網域名稱系統（DNS）記錄，將記錄解析成 Edge 伺服器或 Edge 池的存取邊緣服務。

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的 DNS 摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>稱</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-_tcp. .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。 您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。 如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com （例如）</p></td>
<td><p>Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</p></td>
<td><p>指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。 通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)  


[針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

