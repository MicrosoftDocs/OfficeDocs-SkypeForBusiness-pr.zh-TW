---
title: 憑證摘要-SIP、XMPP 同盟和公用立即訊息
description: 憑證摘要-SIP、XMPP 同盟和公用立即訊息。
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
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572139"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-15_

您所需要的憑證是與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行同盟，通常是由您設定、要求並指派給 Edge Server 的憑證所滿足。

使用可延伸訊息和顯示狀態通訊協定來啟用及建立通訊的憑證需求 (XMPP) 合作夥伴需要加入 XMPP 網域的專案。  (SAN) 中包含在憑證上的記錄，都是可參與 XMPP 通訊的網域。 網域可以是根層級網域 (例如) ，如果您想要對整個網域啟用 XMPP，或可以選取子域 (例如，corp.contoso.com、finance.contoso.com) （如果您為使用者的子集啟用 XMPP）。

若要設定公用立即訊息連線的憑證，請注意，除了北美線上 (AOL) 需要憑證或憑證 (的憑證或憑證，) 也包含用戶端 EKU 時，與其他 SIP 同盟類型或甚至標準 Edge Server 憑證沒有任何不同之處。 用戶端 EKU 是憑證的新增，也是指派給 Edge Server 的外部公用憑證的一部分。

若要確認您是否符合 Edge Server 部署的正確憑證需求，請參閱一節中所列的主題，如 **另**列所列。

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
<th>主體名稱</th>
<th>主體替代名稱 (SAN)</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/Access Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> 若要支援 contoso.com XMPP 命名空間


<p>sip.fabrikam.com</p>



> [!NOTE]
> 若要支援 fabrikam.com SIP 命名空間


<p>fabrikam.com</p>



> [!NOTE]
> 若要支援 fabrikam.com XMPP 命名空間

</td>
<td><p>憑證必須來自公用 CA，而且若要部署與 AOL 的公用 IM 連線，則必須具有伺服器 EKU 和用戶端 EKU。 此憑證會指派給下列專案的外部 Edge Server 介面：</p>
<ul>
<li><p>Access Edge Service</p></li>
<li><p>Web Conferencing Edge service</p></li>
<li><p>A/V Edge service</p></li>
</ul>



> [!NOTE]
> 從技術上而言，憑證並未指派給 A/V Edge。 安全通訊和驗證是透過媒體轉送驗證服務 (MRAS) 來管理。 MRAS 使用指派給 Edge Server 內部介面的憑證。


<p>請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 中的憑證摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的憑證摘要-單一合併 edge （利用公用 IP 位址）](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013 中的憑證摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Lync Server 2013 中的憑證摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013 的憑證摘要-調整式合併 edge （含硬體負載平衡器）](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

