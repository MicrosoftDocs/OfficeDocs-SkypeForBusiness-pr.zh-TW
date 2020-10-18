---
title: DNS 摘要-SIP、XMPP 同盟和公用立即訊息
description: DNS 摘要-SIP、XMPP 同盟和公用立即訊息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572759"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

網域名稱系統 (DNS) 使用 Office 通訊伺服器或 Lync Server 合作夥伴定義同盟所需的記錄，是由您決定是否允許其他全景夥伴對您的網域進行自動 DNS 探索。 如果您發佈的是 \_ sipfederationtls。 \_Tcp。 *\<SIP domain name\>* SRV 記錄，任何其他 SIP 同盟網域都可以「探索」同盟。 您可以使用 Lync server [控制台] 中的 [允許網域與封鎖的網域] 設定，或是使用 Lync Server 管理命令介面和 **Get**、 **Set**、 **New**、 **Remove-CsAllowedDomain** 及 **-CsBlockedDomain** PowerShell Cmdlet 來設定允許或封鎖的網域設定，控制哪些同盟網域可以與您通訊。 如需如何進行這些設定以及 PowerShell Cmdlet 的用法之詳細資訊，請參閱本主題最後的**相關主題**。

DNS 記錄摘要表格會說明針對開放或可公開同盟的必要輸入。 如果您不想要實施同盟探索，您可以決定不設定 \_ sipfederationtls。 \_Tcp。 *\<SIP domain name\>* 記錄。

<div>


> [!IMPORTANT]
> 您必須具有 _sipfederationtls _tcp 的特定案例。 <EM> &lt; SIP 功能變數名稱 &gt; </EM> SRV 記錄，但您不想要有可調查的同盟。 其中一個實例是您為使用者部署行動性的位置。 行動推播通知 clearinghouse (PNCH) 是一種特殊類型的同盟，可供 Apple iPhone 或 iPad 上的 Microsoft Lync Mobile 用戶端使用 lync 2010 行動裝置或 Lync 2013 行動用戶端使用 Lync 2010 Mobile client 或 Windows Phone。 _Sipfederationtls _tcp。 <EM> &lt; SIP 功能變數名稱 &gt; </EM> SRV 記錄是用於行動及推播通知的情況。 若要緩解此問題並控制您的可搜尋性，請清除設定 [ <STRONG>啟用夥伴網域探索</STRONG> ] 以關閉探索。



</div>

若要為您的部署設定可延伸的訊息和顯示狀態通訊協定 (XMPP) ，您可以在外部 DNS 伺服器中建立兩個網域名稱系統 (DNS) 記錄，以將記錄解析為 Edge Server 或 Edge 集區的 Access Edge service。

當您設定網域名稱系統 (用於公用立即訊息連線的 DNS) 時，您會發現支援外部使用者的設定將支援公用 IM 連線。 如果您已設定 Edge Server 或 Edge 集區，則應具備支援公用 IM 連線所需的 DNS 記錄。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 摘要-SIP 同盟（包括公用立即訊息連線）


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
<th>FQDN</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge service 外部介面，可自動將同盟的 DNS 探索至其他潛在同盟協力廠商，也稱為「允許的 SIP 網域」 (在舊版版本) 中稱為「增強型同盟」。視需要針對具有啟用 Lync 功能之使用者的所有 SIP 網域重複</p>



> [!IMPORTANT]
> 行動性和推播通知結算所都必須使用此 SRV 記錄。 在有多個 SIP 網域的情況下，為每一個要具有 Lync 行動用戶端的網域建立併發布 SRV 記錄。 如果部署所支援的每個 SIP 網域沒有明確的 SRV 記錄，推播通知服務和 Apple Push Notification 服務可能無法如預期的方式運作。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 


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
<th>FQDN</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。 您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。 如需其他詳細資料，請參閱另 <strong>請</strong> 參閱主題</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (範例)</p></td>
<td><p>Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</p></td>
<td><p>指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。 一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)  
[在 Lync Server 2013 中設定推播通知](lync-server-2013-configuring-for-push-notifications.md)  
[在 Lync Server 2013 中啟用或停用同盟協力廠商的探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

