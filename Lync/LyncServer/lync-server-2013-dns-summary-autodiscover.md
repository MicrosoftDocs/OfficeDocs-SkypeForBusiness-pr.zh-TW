---
title: Lync Server 2013： DNS 摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS 摘要-Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-13_

自動探索是一種靈活的服務，因為它會接受經由 HTTP 或 HTTPS 進行通訊。 若要完成這項作業，必須正確設定作為自動探索服務之宿主伺服器所使用的網域名稱系統（DNS）與證書。 證書需求已在[Lync Server 2013 的 [認證摘要] 自動](lync-server-2013-certificate-summary-autodiscover.md)探索中講述。

<div>


> [!IMPORTANT]  
> Lync Server 用戶端的 DNS 查閱邏輯使用特定的解析度順序。 您永遠都必須包含 lyncdiscoverinternal。&lt;[&gt;網域] 和 [lyncdiscover]。&lt;您&gt;的 DNS 中的網域。 不包括 lyncdiscoverinternal。&lt;網域&gt;記錄會導致內部用戶端無法連線至預期的服務，或接收不正確的自動探索回應。



</div>

### <a name="internal-dns-records"></a>內部 DNS 記錄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>記錄類型</th>
<th>主機名稱</th>
<th>解析為</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.&lt;內部網功能變數名稱稱&gt;</p></td>
<td><p>如果您有控制器池的內部 Web 服務 FQDN （如果有的話），或是您的 [前端] 池（如果您沒有主管）。</p></td>
</tr>
<tr class="even">
<td><p>A （如果是 IPv6、AAAA，則是主機）</p></td>
<td><p>lyncdiscoverinternal.&lt;內部網功能變數名稱稱&gt;</p></td>
<td><p>如果您沒有主管，則內部 Web 服務 IP 位址（虛擬 IP （VIP）位址是使用負載平衡器）（如果您有一個或多個 [前端] 池）。</p></td>
</tr>
</tbody>
</table>


您需要建立下列其中一個外部 DNS 記錄：

### <a name="external-dns-records"></a>外部 DNS 記錄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>記錄類型</th>
<th>主機名稱</th>
<th>解析為</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>如果您有控制器池的外部 Web 服務 FQDN （如果有的話），或是您的 [前端] 池（如果您沒有主管）。</p></td>
</tr>
<tr class="even">
<td><p>A （如果是 IPv6、AAAA，則是主機）</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>反向 proxy 的外部或公用 IP 位址。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 外部流量透過反向 proxy。



</div>

<div>


> [!NOTE]  
> 行動裝置用戶端不支援來自不同網域的多個安全通訊端層（SSL）憑證。 因此，不支援在 HTTPS 上對不同網域進行 CNAME 重新導向。 例如，在 HTTPS 中不支援重新導向 director.contoso.net 位址的 lyncdiscover.contoso.com 的 DNS CNAME 記錄。 在這種拓撲中，行動裝置用戶端必須針對第一個要求使用 HTTP，才能透過 HTTP 解析 CNAME 重新導向。 後續要求接著使用 HTTPS。 若要支援這種情況，您必須使用埠80（HTTP）的 web 發佈規則來設定您的反向 proxy。 如需詳細資訊，請參閱在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定反向 proxy 以進行行動</A>中的 [針對埠80建立 web 發佈規則]。 在 HTTPS 上支援 CNAME 重新導向至同一個網域。 在這種情況下，目的地網域的憑證會涵蓋來源網域。



</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定行動的反向 Proxy](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[憑證摘要-Lync Server 2013 中的自動探索](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

