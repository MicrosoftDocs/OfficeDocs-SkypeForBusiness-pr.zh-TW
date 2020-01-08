---
title: Lync Server 2013：憑證摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b21c8b09d93f8d2788424f2c8f440e1dec66b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>認證摘要-Lync Server 2013 中的可擴展訊息和目前狀態通訊協定（XMPP）同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-23_

啟用和建立使用可擴展訊息和目前狀態通訊協定（XMPP）合作夥伴的憑證需求，需要您 XMPP 網域的其他記錄。 在證書中作為消費者備用名稱（SAN）所包含的記錄，就是可參與 XMPP 通訊的網域。 網域可以是根層級網域（例如，contoso.com），如果您想要為整個網域啟用 XMPP，或可以選取子域（例如，corp.contoso.com、finance.contoso.com），如果您要為使用者的子集啟用 XMPP。

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的憑證摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>消費者名稱</th>
<th>Subject 替代名稱（SAN）/Order</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指派給 Edge 伺服器或 Edge 池的存取邊緣服務</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>前三個 SAN 專案是完整邊緣伺服器的一般 SAN 專案。 Contoso.com 是在根網域層級與 XMPP 夥伴聯盟所需的專案。 此專案將允許 XMPP 所有網域的 [尾碼 contoso.com]。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)  


[針對 Lync Server 2013 設定 Edge 憑證](lync-server-2013-set-up-edge-certificates.md)  
[要求-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

