---
title: Lync Server 2013：Standard Edition Server 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 中 Standard Edition Server 的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

本節說明部署標準版伺服器所需的網域名稱系統（DNS）記錄。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>標準版伺服器的 DNS 記錄

下表指定 Lync Server 2013 標準版伺服器部署的 DNS 需求。


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
<td><p>含 name ucupdates-r2 的內部 A 記錄。&lt;可解析&gt;為標準版伺服器託管裝置更新 Web 服務之 IP 位址的 SIP 網域。 在已開啟 UC 裝置，但使用者從未登入裝置的情況下，A 記錄可讓裝置探索託管裝置更新 Web 服務的伺服器，並取得更新。 否則，在使用者第一次登入時，裝置會透過頻帶內的設定來取得伺服器資訊。 如需詳細資訊，請參閱 Operations 檔中的<a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的裝置更新 Web 服務</a>。</p></td>
</tr>
<tr class="even">
<td><p>支援 HTTP 流量的反向 proxy</p></td>
<td><p>外部 A 記錄，可將外部 web farm FQDN 解析成反向 proxy 的外部 IP 位址。 用戶端和 UC 裝置使用此記錄連線到反向 proxy。 如需詳細資訊，請參閱在規劃檔中<a href="lync-server-2013-determine-dns-requirements.md">判斷 Lync Server 2013 的 DNS 需求</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中自動用戶端登入的 DNS 需求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 中的裝置更新 Web 服務](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

