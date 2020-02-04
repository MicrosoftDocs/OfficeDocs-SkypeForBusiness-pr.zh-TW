---
title: 憑證摘要-SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>認證摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-15_

您要用來與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行聯盟所需的憑證，通常會受到您設定、要求並指派給 Edge 伺服器的憑證。

啟用和建立使用可擴展訊息和目前狀態通訊協定（XMPP）合作夥伴的憑證需求，您必須加入 XMPP 網域的專案。 在證書中作為消費者備用名稱（SAN）所包含的記錄，就是可參與 XMPP 通訊的網域。 網域可以是根層級網域（例如，contoso.com），如果您想要為整個網域啟用 XMPP，或可以選取子域（例如，corp.contoso.com、finance.contoso.com），如果您要為使用者的子集啟用 XMPP。

若要設定公用立即訊息連線的憑證，請注意，除了北美線上（AOL）需要證書或憑證之外，其他 SIP 同盟類型或甚至標準邊緣伺服器憑證沒有什麼不同（在邊緣池的大小寫）也包含用戶端 EKU。 用戶端 EKU 是憑證的補充，而且是指派給 Edge 伺服器的外部公用憑證的一部分。

若要確認您已符合 Edge 伺服器部署的正確證書需求，請參閱標題為 [**另請參閱**] 區段中所列的主題。

<div>



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
<th>消費者備用名稱（SAN）</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/存取邊緣</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> 支援 contoso.com XMPP 命名空間


<p>sip.fabrikam.com</p>



> [!NOTE]
> 支援 fabrikam.com SIP 命名空間


<p>fabrikam.com</p>



> [!NOTE]
> 支援 fabrikam.com XMPP 命名空間

</td>
<td><p>證書必須來自公用 CA，而且如果要部署與 AOL 的公用 IM 連線，則必須擁有伺服器 EKU 和用戶端 EKU。 已將證書指派給外部邊緣伺服器介面，以進行下列作業：</p>
<ul>
<li><p>存取邊緣服務</p></li>
<li><p>網路會議 Edge 服務</p></li>
<li><p>A/V 邊緣服務</p></li>
</ul>



> [!NOTE]
> 從技術角度來看，憑證沒有指派給 A/V 邊緣。 安全通訊與驗證是透過媒體轉送驗證服務（MRAS）的方式來管理。 MRAS 使用指派給 Edge 伺服器內部介面的憑證。


<p>請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。 您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。 Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 中的憑證摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的憑證摘要 - 含公用 IP 位址的單一合併 Edge](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (利用硬體負載平衡器)](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

