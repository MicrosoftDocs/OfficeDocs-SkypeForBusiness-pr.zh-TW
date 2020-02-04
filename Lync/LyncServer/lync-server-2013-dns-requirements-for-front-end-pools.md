---
title: Lync Server 2013：前端池的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b763f9b01e070fc434dae997bc1e2da68dcbc26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 中前端池的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-07_

本節說明部署前端池所需的網域名稱系統（DNS）記錄。

<div>

## <a name="dns-records-for-front-end-pools"></a>前端池的 DNS 記錄

下表指定 Lync Server 2013 前端池部署的 DNS 需求。

### <a name="dns-requirements-for-a-front-end-pool"></a>前端池的 DNS 需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署案例</th>
<th>DNS 需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>具有多個前端伺服器和硬體負載平衡器的前端池（無論是否也在該池中部署 DNS 負載平衡）</p></td>
<td><p>同時使用 DNS 負載平衡與硬體負載平衡器時，您必須裝載（A）記錄。 建立可解析 DNS 負載平衡之前端池的完整功能變數名稱（FQDN）的內部 A 記錄。 在負載平衡器的虛擬 IP （VIP）位址建立內部 Web 服務的內部主機（A）記錄。 您必須使用 [拓撲建立器] 中定義的內部 Web 服務名稱。</p>
<p>例如，如果您同時使用 [DNS 負載平衡] 和 [硬體負載平衡]，您將會在 DNS 負載平衡的池中有一份記錄，並將內部 Web 服務的記錄指向硬體負載平衡器的虛擬 IP:</p>
<ul>
<li><p>DNS 負載平衡： Pool01.contoso.net pool 10.10.10.5 的 IP 位址</p>
<div>

> [!WARNING]  
> 每個前端伺服器也會有不同的 A 記錄：


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10。1</p></li>
<li><p>FE02.contoso.net 10.10.10。2</p></li>
<li><p>FE03.contoso.net 10.10.10。3</p></li>
<li><p>FE04.contoso.net 10.10.10。4</p></li>
</ol></li>
<li><p>硬體負載平衡： WebInternal.contoso.net HLB VIP 192.168.10.5 的 IP 位址</p></li>
</ul>
<p>除 HTTP/HTTPS 流量以外的所有流量，都將使用 Pool01.contoso.net 記錄。 HTTP/HTTPS 流量將使用已定義的內部 Web 服務位址192.168.10。5</p></td>
</tr>
<tr class="even">
<td><p>已部署 DNS 負載平衡的前端池</p></td>
<td><p>一組內部 A 記錄，可將池的 FQDN 解析為池中每個伺服器的 IP 位址。 池中的每個伺服器都必須有一個記錄。</p></td>
</tr>
<tr class="odd">
<td><p>已部署 DNS 負載平衡的前端池</p></td>
<td><p>一組內部 A 記錄，可將池中每個伺服器的 FQDN 解析為該伺服器的 IP 位址。 如需詳細資訊，請參閱規劃檔中的<a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 DNS 負載平衡</a>。</p></td>
</tr>
<tr class="even">
<td><p>具有單一前端伺服器與專用後端資料庫但沒有負載平衡器的前端池</p></td>
<td><p>內部 A 記錄，可將前端池的 FQDN 解析為單一企業版前端伺服器的 IP 位址。</p></td>
</tr>
<tr class="odd">
<td><p>自動用戶端登入</p></td>
<td><p>針對每個支援的 SIP 網域，_sipinternaltls _tcp 的 SRV 記錄。&lt;埠&gt; 5061 上的網域會對應到前端池的 FQDN，以驗證並重新導向用戶端的登入要求。 如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自動用戶端登入 DNS 需求</a>。</p></td>
</tr>
<tr class="even">
<td><p>透過整合通訊（UC）裝置進行的裝置更新 Web 服務探索</p></td>
<td><p>含 name ucupdates-r2 的內部 A 記錄。&lt;可解析&gt;為主機裝置更新 Web 服務之前端池之 IP 位址的 SIP 網域。 在已開啟 UC 裝置但使用者從未登入裝置的情況下，A 記錄可讓裝置探索前端池託管裝置更新 Web 服務並取得更新。 否則，裝置會在使用者第一次登入時，透過頻帶內配來取得此資訊。</p>
<div>

> [!IMPORTANT]  
> 如果您已在 Lync Server 2010 中部署裝置更新 Web 服務，就表示您已使用名稱 ucupdates 建立了一個內部 A 記錄。&lt;SIP 網域&gt;。 若是 Microsoft Office 通訊伺服器 2007 R2，您必須使用 name ucupdates-R2 建立額外的 DNS A 記錄。&lt;SIP 網域&gt;。


</div></td>
</tr>
<tr class="odd">
<td><p>支援 HTTP 流量的反向 proxy</p></td>
<td><p>外部 A 記錄，可將外部 web farm FQDN 解析成反向 proxy 的外部 IP 位址。 用戶端和 UC 裝置使用此記錄連線到反向 proxy。 如需詳細資訊，請參閱在規劃檔中<a href="lync-server-2013-determine-dns-requirements.md">判斷 Lync Server 2013 的 DNS 需求</a>。</p></td>
</tr>
</tbody>
</table>


下表顯示內部網站集群 FQDN 所需的 DNS 記錄範例。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>內部網路場 FQDN 的 DNS 記錄範例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>內部網站伺服器陣列 FQDN</th>
<th>池 FQDN</th>
<th>DNS A 記錄（s）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Ee-pool.contoso.com 的 DNS A 記錄，可解析為前端伺服器所使用之負載平衡器的 VIP 位址。</p>
<p>DNS A webcon.contoso.com 的記錄，可解析為前端伺服器所使用之負載平衡器的 VIP 位址。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS A ee-pool.contoso.com 的記錄，可解析為 [前端] 池中的企業版前端伺服器所使用之負載平衡器的虛擬 IP （VIP）位址。</p>
<p>請注意，如果您使用的是此 pool 的 DNS 負載平衡，您的前臺池和內部網路群不能有相同的 FQDN。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

