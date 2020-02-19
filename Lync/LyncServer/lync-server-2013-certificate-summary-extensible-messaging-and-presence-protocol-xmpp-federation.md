---
title: Lync Server 2013： 憑證摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e13b3a126b952ade0a422039a225970eb9bafbe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>憑證摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12 月 23 日_

啟用的憑證需求，建立與可延伸訊息與顯示狀態通訊協定 (XMPP) 的通訊合作夥伴需要 XMPP 網域的其他記錄。 包含在憑證的主體替代名稱 (SAN) 的記錄會是可以參與 XMPP 通訊的網域。 網域可以是根層級網域 (例如，contoso.com)，如果您想要啟用 XMPP 的整個網域，或可選取的子網域 （例如，corp.contoso.com、 finance.contoso.com），如果您要啟用 XMPP 使用者的子集。

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和顯示狀態通訊協定的憑證摘要


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
<th>主體名稱</th>
<th>主體替代名稱 (SAN)/順序</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指派給 Access Edge service 之 Edge Server 或 Edge 集區</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>前三個 SAN 項目是完整的 Edge server 的一般 SAN 項目。 contoso.com 是在根網域層級與 XMPP 協力廠商同盟的必要項目。 這個項目會允許 XMPP 具有尾碼 contoso.com 的所有網域。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 – 與 Google Talk 的 XMPP 同盟中 XMPP 設定範例](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Lync Server 2013 中的 Edge Server 憑證計劃](lync-server-2013-plan-for-edge-server-certificates.md)  


[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)  
[Request-cscertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

