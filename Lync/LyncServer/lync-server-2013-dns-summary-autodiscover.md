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
ms.openlocfilehash: b72e52927b8c84f5ad9cb869cd680f057e1618f8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-13_

自動探索是一種彈性服務，它會接受透過 HTTP 或 HTTPS 的通訊。 為了達到此目的，網域名稱系統 (DNS) ，而且必須正確地設定裝載自動探索服務之伺服器所使用的憑證。 憑證需求會在[Lync Server 2013 的憑證摘要-自動](lync-server-2013-certificate-summary-autodiscover.md)探索中講述。

<div>


> [!IMPORTANT]  
> Lync Server 用戶端的 DNS 查閱邏輯使用特定的解決順序。 您應無條件同時包含 lyncdiscoverinternal。 &lt;網域 &gt; 和 lyncdiscover。 &lt;&gt;DNS 中的網域。 排除 lyncdiscoverinternal。 &lt;網域 &gt; 記錄會導致內部用戶端無法連線至預定服務，或接收不正確的自動探索回應。



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
<td><p>Lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</p></td>
<td><p>Director 集區的內部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</p></td>
</tr>
<tr class="even">
<td><p> (主機，如果是 IPv6，AAAA) </p></td>
<td><p>lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</p></td>
<td><p>當您使用 Director 集區的負載平衡器) 時（如果您有一個或多個前端集區，則為 [內部 Web 服務] IP 位址 (虛擬 IP (VIP) 位址）。</p></td>
</tr>
</tbody>
</table>


您需要建立下列其中一項外部 DNS 記錄：

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
<td><p>lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>Director 集區的外部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</p></td>
</tr>
<tr class="even">
<td><p> (主機，如果是 IPv6，AAAA) </p></td>
<td><p>lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>反向 proxy 的外部或公用 IP 位址。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 外部流量會通過反向 Proxy。



</div>

<div>


> [!NOTE]  
> 行動裝置用戶端不支援來自不同網域的多個 Secure Sockets Layer (SSL) 憑證。 因此，不支援透過 HTTPS 將 CNAME 重新導向至不同的網域。 例如，不支援透過 HTTPS 將 lyncdiscover.contoso.com 的 DNS CNAME 記錄重新導向至 director.contoso.net 的位址。 在這樣的拓撲中，行動裝置用戶端需要使用 HTTP 來進行第一個要求，以透過 HTTP 來解析 CNAME 重新導向。 後續的要求則會使用 HTTPS。 若要支援此案例，您需要以連接埠 80 的 Web 發行規則來設定反向 Proxy (HTTP)。 如需詳細資訊，請參閱在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定行動的反向 proxy</A>中的「為埠80建立 web 發行規則」。 支援透過 HTTPS 將 CNAME 重新導向至相同網域。 在此情況下，目的網域的憑證會涵蓋原始網域。



</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定行動的反向 proxy](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Lync Server 2013 中的憑證摘要-自動探索](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

