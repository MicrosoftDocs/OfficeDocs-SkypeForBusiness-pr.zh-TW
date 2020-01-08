---
title: DNS 摘要-SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

使用 Office 通訊伺服器或 Lync Server 合作夥伴定義同盟時所需的網域名稱系統（DNS）記錄，是由您決定是否允許其他全景夥伴自動 DNS 探索您的網域。 如果您發佈\_sipfederationtls。\_tcp。 * \<SIP 功能變數名稱\> *SRV 記錄，任何其他 SIP 聯盟網域將能夠「探索」您的同盟。 您可以透過使用 lync Server [控制台] 中的 [允許網域和封鎖網域] 設定，或使用 Lync Server 管理命令介面以及 [**取得**]、[**設定**]、[**新增**]、[ **CsAllowedDomain** ] 及 [ **CsBlockedDomain** PowerShell] Cmdlet 來控制哪些聯盟網域可以與您通訊。 如需有關如何設定這些設定及如何使用 PowerShell Cmdlet 的其他資訊，請參閱本主題結尾的**相關主題**。

[DNS 記錄] 摘要表格描述開啟或可探索的同盟聯盟所需的專案。 如果您不想要實施同盟探索，您可以決定不設定\_sipfederationtls。\_tcp。 *SIP 功能變數名稱\> \< *

<div>


> [!IMPORTANT]
> 在特定情況下，您必須有 _sipfederationtls _tcp。 <EM> &lt;SIP 功能變數名稱&gt; </EM>SRV 記錄，但您不想有可探索的同盟。 其中一個實例就是您為使用者部署行動性的位置。 行動推播通知 clearinghouse （PNCH）是一種特殊類型的同盟，在 Apple iPhone 或 iPad 上使用 Lync 2010 行動用戶端2010或 lync 2013 行動用戶端的 Microsoft Lync Mobile 用戶端使用。 _Sipfederationtls. _tcp。 <EM> &lt;SIP 功能變數名稱&gt; </EM>SRV 記錄是在行動與推播通知的情況下使用。 若要緩解此問題並控制您的可搜尋性，請清除 [<STRONG>啟用合作夥伴網域探索</STRONG>的設定]，以關閉探索。



</div>

若要為您的部署設定可擴展的訊息和目前狀態通訊協定（XMPP），您可以在外部 DNS 伺服器中建立兩個網域名稱系統（DNS）記錄，將記錄解析成 Edge 伺服器或 Edge 池的存取邊緣服務。

當您設定網域名稱系統（DNS）以取得公用立即訊息連線時，您會發現支援外部使用者的設定將支援公用 IM 連線。 如果您已設定 Edge 伺服器或 Edge 池，您應該擁有支援公用 IM 連線所需的 DNS 記錄。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 摘要-SIP 同盟，包括公用立即訊息連線


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
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge 服務外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</p>



> [!IMPORTANT]
> 行動與推播通知結算所需要這個 SRV 記錄。 在有多個 SIP 網域的情況下，為每一個要有 Lync 行動用戶端的網域建立併發布 SRV 記錄。 如果部署支援的每個 SIP 網域沒有明確的 SRV 記錄，則推播通知服務和 Apple 推播通知服務可能無法如期運作。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）


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
[在 Lync Server 2013 中設定推播通知](lync-server-2013-configuring-for-push-notifications.md)  
[在 Lync Server 2013 中啟用或停用探索同盟協力廠商](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

