---
title: Lync Server 2013： 前端集區的 DNS 需求
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
ms.openlocfilehash: 12fc719c52434e07599fb4b65604ea832dc95f7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 中的前端集區的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-07_

本節描述部署前端集區所需的網域名稱系統 (DNS) 記錄。

<div>

## <a name="dns-records-for-front-end-pools"></a>前端集區的 DNS 記錄

下表指定 Lync Server 2013 前端集區部署的 DNS 需求。

### <a name="dns-requirements-for-a-front-end-pool"></a>前端集區的 DNS 需求

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
<td><p>前端集區使用多個前端伺服器和硬體負載平衡器 （無論該集區上也部署 DNS 負載平衡）</p></td>
<td><p>使用 DNS 負載平衡與硬體負載平衡器，您需要主機 (A) 記錄。 建立內部完整的網域名稱 (FQDN) 解析一筆記錄的 DNS 負載平衡的前端集區。 建立負載平衡器的虛擬 IP (VIP) 位址的內部主機 (A) 記錄的內部 Web 服務。 拓撲產生器中所定義，您必須使用的內部 Web 服務名稱。</p>
<p>例如，如果您使用 DNS 負載平衡與硬體負載平衡，您會有每個前端伺服器的 DNS 負載平衡集區中的記錄以及指向硬體負載平衡器虛擬 IP 的內部 Web 服務之 A 記錄:</p>
<ul>
<li><p>DNS 負載平衡： 集區 10.10.10.5 的 Pool01.contoso.net IP 位址</p>
<div>

> [!WARNING]  
> 每個前端伺服器也會有不同的記錄：


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>硬體負載平衡： WebInternal.contoso.net IP 位址 HLB VIP 192.168.10.5 的</p></li>
</ul>
<p>HTTP/HTTPS 流量除外的所有流量將都使用的 Pool01.contoso.net 筆記錄。 用以定義內部 Web 服務位址 192.168.10.5 的 HTTP/HTTPS 流量。</p></td>
</tr>
<tr class="even">
<td><p>前端集區的 DNS 負載平衡部署</p></td>
<td><p>內部的一組記錄集區中的每一部伺服器的 IP 位址的集區 FQDN 必須解決。 那里必須針對每部伺服器集區中的一個 A 記錄。</p></td>
</tr>
<tr class="odd">
<td><p>前端集區的 DNS 負載平衡部署</p></td>
<td><p>內部的一組記錄在該伺服器的 IP 位址的集區中，該解決每部伺服器的 FQDN。 如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-dns-load-balancing.md">DNS 負載平衡 Lync Server 2013 中</a>。</p></td>
</tr>
<tr class="even">
<td><p>前端集區具有單一前端伺服器和專用的後端資料庫但無負載平衡器</p></td>
<td><p>一筆內部 A 記錄，解析為前端集區的 FQDN 為單一 Enterprise Edition 前端伺服器的 IP 位址。</p></td>
</tr>
<tr class="odd">
<td><p>自動用戶端登入</p></td>
<td><p>每個支援的 SIP 網域，_sipinternaltls._tcp 的 SRV 記錄。&lt;網域&gt;透過連接埠 5061，對應到驗證，並將登入的用戶端要求重新導向的前端集區的 FQDN。 如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS 需求的用戶端自動登入 Lync Server 2013 中</a>。</p></td>
</tr>
<tr class="even">
<td><p>整合通訊 (UC) 裝置的裝置更新 Web 服務探索</p></td>
<td><p>一筆內部 A 記錄名稱 ucupdates-r2。&lt;SIP 網域&gt;，解析為前端集區主控的裝置更新 Web 服務的 IP 位址。 在其中 UC 裝置已開啟，但使用者永遠不登入裝置情況下，A 記錄可讓探索主控裝置更新 Web 服務的前端集區，並取得更新的裝置。 否則，裝置取得這項資訊，但是頻內佈建使用者登入第一次。</p>
<div>

> [!IMPORTANT]  
> 如果您有裝置更新 Web 服務的現有部署 Lync Server 2010 中，您已經建立一筆內部 A 記錄與名稱 ucupdates-r2。&lt;SIP 網域&gt;。 對於 Microsoft Office Communications Server 2007 R2，您必須建立額外的 DNS A 記錄與名稱 ucupdates-r2。&lt;SIP 網域&gt;。


</div></td>
</tr>
<tr class="odd">
<td><p>支援 HTTP 流量的反向 Proxy</p></td>
<td><p>一筆外部 A 記錄，將外部 Web 伺服陣列 FQDN 解析為反向 Proxy 的外部 IP 位址。 用戶端和 UC 裝置會使用這個記錄來連線至反向 Proxy。 如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 的判斷 DNS 需求</a>。</p></td>
</tr>
</tbody>
</table>


下表顯示所需的內部 web 伺服陣列 FQDN 的 DNS 記錄範例。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>內部 Web 伺服陣列 FQDN 的 DNS 記錄範例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>內部 web 伺服陣列 FQDN</th>
<th>集區 FQDN</th>
<th>DNS A 記錄</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Ee-pool.contoso.com 的解析為前端伺服器所用負載平衡器的 VIP 位址的 DNS A 記錄。</p>
<p>會解析為前端伺服器所用負載平衡器的 VIP 位址的 webcon.contoso.com 的 DNS A 記錄。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Ee-pool.contoso.com 的且可使用 Enterprise Edition 前端伺服器的前端集區中的負載平衡器虛擬 IP (VIP) 位址解析的 DNS A 記錄。</p>
<p>請注意，是否您使用 DNS 負載平衡此集區上，您的前端集區和內部 web 伺服陣列不能有相同的 FQDN。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

