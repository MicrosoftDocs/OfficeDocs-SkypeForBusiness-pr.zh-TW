---
title: Lync Server 2013：以位置為基礎的路由與諮詢式來電轉接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013 中的位置路由與諮詢式來電轉接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-31_

除了強制將位置路由到 Lync 會議之外，以位置為基礎的路由會議應用程式會在諮詢通話中強制執行以位置為基礎的路由限制，將出局傳送到 PSTN 端點。 「諮詢式來電轉接」是雙方在其中一方傳送呼叫給新使用者的兩方之間所建立的通話。 例如，PSTN 端點會呼叫使用者 A （Lync 被呼叫者）。 使用者 A 決定應將 PSTN 使用者轉寄到使用者 B （Lync 使用者）。 使用者 A 將呼叫與 PSTN 使用者保留通話，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。 使用者 A 將來電轉接到使用者 B。

**諮詢式通話轉移通話流程**

![會議圖表的以位置為基礎的路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "會議圖表的以位置為基礎的路由")

當啟用位置路由的使用者啟動 PSTN 端點的諮詢式來電轉接時（如上圖所示），這會產生兩個作用中的通話、PSTN 使用者與 Lync 使用者 A 之間的呼叫，以及 Lync 使用者 A 和 Lync 使用者 B 之間的另一個通話。下列行為是由以位置為基礎的路由會議應用程式強制執行：

  - 如果 SIP 中繼路由 PSTN 呼叫已獲授權，可將 PSTN 呼叫重新路由至 Lync 使用者 B （亦即傳輸目標）所在的網路網站，則允許來電轉接;否則，將會封鎖諮詢式來電轉接。 這項授權是依據已傳送的參與方的位置，而不是將作用中的呼叫路由至 PSTN 端點的 SIP 主幹來執行。

  - 如果 SIP 中繼路由未獲授權將呼叫路由至傳送方（Lync 使用者 B）所在的網路網站，或轉移的參與方位於未知的網路網站中，請諮詢來電轉接到 PSTN將會封鎖端點（亦即來電轉接目標）。

下表說明諮詢式來電轉接的位置式路由會議應用程式如何套用以位置為基礎的路由限制。 雖然 PBX 端點並不與網路網站直接關聯，但 PBX 的 SIP 幹線已連接至可指派網路網站。 因此，PBX 端點可以與網路網站間接關聯。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>來電轉接方的網路網站</p></td>
<td><p>來電轉接目標的網路網站</p></td>
<td><p>行為</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>同一網路網站中的 Lync 使用者（亦即 site 1）</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>不同網路網站中的 Lync 使用者（亦即 site 2）</p></td>
<td><p>不允許使用顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>未知網路網站中的 Lync 使用者</p></td>
<td><p>不允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>聯盟 Lync 使用者</p></td>
<td><p>不允許使用顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>同一網站中的 PBX 端點（亦即 site 1）</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>不同網站中的 PBX 端點（亦即 site 2）</p></td>
<td><p>不允許使用顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>同一網站中的 PBX 端點（亦即 site 1）</p></td>
<td><p>PSTN 端點</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>不同網站中的 PBX 端點（亦即 site 2）</p></td>
<td><p>PSTN 端點</p></td>
<td><p>不允許使用顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>同一網路網站中的 Lync 使用者（亦即 site 1）</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>不同網路網站中的 Lync 使用者（亦即 site 2）</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>未知網路網站中的 Lync 使用者</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>聯盟 Lync 使用者</p></td>
<td><p>允許使用顧問式轉接</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

