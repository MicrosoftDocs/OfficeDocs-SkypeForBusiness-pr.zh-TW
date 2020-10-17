---
title: Lync Server 2013： Location-Based 路由和顧問式來電轉接
description: Lync Server 2013： Location-Based 路由和顧問式來電轉接。
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567669"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>在 Lync Server 2013 中 Location-Based 路由和顧問式來電轉接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-31_

除了強制 Location-Based 路由傳送至 Lync 會議之外，Location-Based 路由會議應用程式也會強制進行向 PSTN 端點出口的諮詢來電轉接 Location-Based 路由限制。 「諮詢通話轉移」是兩方間所建立的呼叫，其中一個團體會將來電轉接給新的使用者。 例如，PSTN 端點會呼叫使用者 A (Lync 方程式) 。 使用者 A 判斷 PSTN 使用者應轉寄給使用者 B (Lync 使用者) 。 使用者 A 通話為 PSTN 使用者保留，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。 使用者 A 將來電轉接至使用者 B。

**諮詢通話轉接通話流程**

![會議圖表的位置基礎路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "會議圖表的位置基礎路由")

當啟用 Location-Based 路由的使用者啟動對 PSTN 端點的諮詢來電轉接時 (如前面的圖所示) 所示，這會建立兩個使用中的呼叫、PSTN 使用者和 Lync 使用者 A 之間的呼叫，以及 Lync 使用者 A 和 Lync 使用者 B 之間的另一個呼叫。下列行為是由 Location-Based 路由會議應用程式強制執行的：

  - 如果您有權將 pstn 通話路由的 SIP 主幹路由，以將 PSTN 呼叫重新路由至網路網站（Lync 使用者 B (亦即轉接目標) 位於此位置），則會允許通話轉接;否則，將會封鎖「諮詢來電轉接」。 這種授權是根據傳送方的位置，而不是以將使用中通話路由傳送至 PSTN 端點的 SIP 主幹所在的相同網路網站執行。

  - 若 SIP 主幹路由輸入 PSTN 來電未獲授權，無法將來電路由傳送至已傳送方 (Lync 使用者 B) 或已轉接的當事方位於未知的網路網站，則諮詢呼叫會轉接至 PSTN 端點 (亦即會封鎖來電轉接目標) 。

下表說明 Location-Based 路由會議應用程式如何套用 Location-Based 路由限制以進行諮詢來電轉接。 雖然 PBX 端點不會直接與網路產生關聯，但 PBX 的 SIP 主幹可被指派為網路網站。 因此，PBX 端點可以與網路網站間接關聯。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>通話轉移方的網路網站</p></td>
<td><p>來電轉接目標的網路網站</p></td>
<td><p>行為</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>相同網路網站中的 Lync 使用者 (亦即網站 1) </p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>不同網路網站中的 Lync 使用者 (亦即 site 2) </p></td>
<td><p>不允許顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>未知網路網站中的 Lync 使用者</p></td>
<td><p>不允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>同盟 Lync 使用者</p></td>
<td><p>不允許顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>同一個網站中的 PBX 端點 (亦即，site 1) </p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>不同網站中的 PBX 端點 (亦即 site 2) </p></td>
<td><p>不允許顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>同一個網站中的 PBX 端點 (亦即，site 1) </p></td>
<td><p>PSTN 端點</p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>不同網站中的 PBX 端點 (亦即 site 2) </p></td>
<td><p>PSTN 端點</p></td>
<td><p>不允許顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>相同網路網站中的 Lync 使用者 (亦即網站 1) </p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>不同網路網站中的 Lync 使用者 (亦即 site 2) </p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="even">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>未知網路網站中的 Lync 使用者</p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
<tr class="odd">
<td><p>任何網站中的 PBX 端點</p></td>
<td><p>同盟 Lync 使用者</p></td>
<td><p>允許顧問式轉接</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

