---
title: DNS 摘要-SIP，XMPP 同盟及 public instant messaging
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
ms.openlocfilehash: 9c2ccaab6d1d3bcb1cf597bef076601544f47aad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS 摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-03-09_

會定義與 Office Communications Server 或 Lync Server 的協力廠商的同盟所需的網域名稱系統 (DNS) 記錄取決於您的決定，若要允許的其他觀點來看協力廠商網域的 DNS 的自動探索。 如果您將發佈\_sipfederationtls。\_tcp。 * \<SIP 網域名稱\>* SRV 記錄，任何其他 SIP 同盟的網域將能夠 「 探索 」 同盟。 您可以控制哪些同盟的網域可以與彼此您藉由使用允許的網域和封鎖的網域設定 Lync Server 控制台中，或設定使用 Lync Server 管理命令介面和**取得**、**設定**、**新增**、**移除 CsAllowedDomain**及**New-csblockeddomain** PowerShell cmdlet 的允許或封鎖的網域組態。 如需如何進行這些設定以及 PowerShell Cmdlet 的用法之詳細資訊，請參閱本主題最後的**相關主題**。

DNS 記錄摘要表格會說明針對開放或可公開同盟的必要輸入。 如果您不想要實作同盟探索，您可以決定未設定\_sipfederationtls。\_tcp。 * \<SIP 網域名稱\>* 記錄。

<div>


> [!IMPORTANT]
> 有特定案例，您必須有 _sipfederationtls._tcp。 <EM> &lt;SIP 網域名稱&gt;</EM>SRV 記錄，但您不想讓探索同盟。 其中一種情況是您為您的使用者部署行動性的位置。 行動推播通知結算所 (PNCH) 是一種特殊類型的 Apple iPhone 或 iPad 使用 Lync 2010 Mobile 用戶端或使用 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 上的 Microsoft Lync 行動用戶端所用同盟。 _Sipfederationtls._tcp。 <EM> &lt;SIP 網域名稱&gt;</EM>SRV 記錄會在行動性和推入通知的情況下使用。 若要降低此問題，並控制您可測知性，清除 [<STRONG>啟用協力廠商網域探索</STRONG>] 以關閉 [探索] 設定。



</div>

若要設定可延伸訊息和顯示狀態通訊協定 (XMPP) 部署，您可以建立兩個網域名稱系統 (DNS) 記錄會將記錄解析至 Edge Server 或 Edge 集區的 [Access Edge service 的外部 DNS 伺服器中。

當您設定網域名稱系統 (DNS) 的 public instant messaging 連線時，您會發現支援外部使用者的設定將支援公用 IM 連線。 如果您已設定您的 Edge Server 或 Edge 集區，您應該有支援公用 IM 連線所需的 DNS 記錄。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 摘要-SIP 同盟包括 Public Instant Messaging 連線


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
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge service 的外部介面所需的 DNS 自動探索其他潛在同盟協力廠商同盟，就所謂的 「 允許的 SIP 網域 」 （先前版本稱為增強型的同盟）。啟用 Lync 之使用者的所有 SIP 網域，依需要重複執行</p>



> [!IMPORTANT]
> 行動性和推播通知結算所都必須使用此 SRV 記錄。 在情況下是多個 SIP 網域，建立及發佈會有 Lync 行動用戶端的每個網域的 SRV 記錄。 推入通知服務和 Apple 推播通知服務可能無法運作如預期般是否有不部署支援的每個 SIP 網域的明確 SRV 記錄。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 摘要-Extensible Messaging and Presence Protocol (XMPP)


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
[設定 Lync Server 2013 中的推入通知](lync-server-2013-configuring-for-push-notifications.md)  
[啟用或停用 Lync Server 2013 中的同盟協力廠商的探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定針對 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[管理 Lync Server 2013 中組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

