---
title: Lync Server 2013：標準版伺服器的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 中標準版伺服器的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

本節說明部署標準版伺服器所需的網域名稱系統（DNS）記錄。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>標準版伺服器的 DNS 記錄

下表指定 Lync Server 2013 標準版伺服器部署的 DNS 需求。

### <a name="dns-requirements-for-a-standard-edition-server"></a>標準版伺服器的 DNS 需求

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
<td><p>標準版伺服器</p></td>
<td><p>將伺服器的完整功能變數名稱（FQDN）解析成其 IP 位址的內部 A 記錄。</p></td>
</tr>
<tr class="even">
<td><p>自動用戶端登入</p></td>
<td><p>針對每個支援的 SIP 網域，_sipinternaltls _tcp 的 SRV 記錄。&lt;經由&gt;埠5061的網域，會對應到標準版 server 的 FQDN，該伺服器會將登入的用戶端要求驗證並重新導向。 如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自動用戶端登入 DNS 需求</a>。</p></td>
</tr>
<tr class="odd">
<td><p>透過整合通訊（UC）裝置進行的裝置更新 Web 服務探索</p></td>
<td><p>含 name ucupdates-r2 的內部 A 記錄。&lt;可解析&gt;為標準版伺服器託管裝置更新 Web 服務之 IP 位址的 SIP 網域。 在已開啟 UC 裝置，但使用者從未登入裝置的情況下，A 記錄可讓裝置探索託管裝置更新 Web 服務的伺服器，並取得更新。 否則，在使用者第一次登入時，裝置會透過頻帶內的設定來取得伺服器資訊。</p></td>
</tr>
<tr class="even">
<td><p>支援 HTTP 流量的反向 proxy</p></td>
<td><p>外部 A 記錄，可將外部 web farm FQDN 解析成反向 proxy 的外部 IP 位址。 用戶端和 UC 裝置使用此記錄連線到反向 proxy。 如需詳細資訊，請參閱在規劃檔中<a href="lync-server-2013-determine-dns-requirements.md">判斷 Lync Server 2013 的 DNS 需求</a>。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

