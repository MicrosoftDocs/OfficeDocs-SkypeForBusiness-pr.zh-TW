---
title: Lync Server 2013： 位置型路由及諮詢轉接
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
ms.openlocfilehash: 2dff8b723889be65f26e2c04d7f6a594515bfd09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>位置型路由及 Lync Server 2013 中的諮詢轉接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-31_

除了強制執行位置型路由到 Lync 會議，位置型路由會議應用程式強制執行諮詢轉接，輸出至 PSTN 端點上的位置型路由限制。 諮詢的來電轉接是兩方的其中一方將通話轉接給新的使用者建立通話。 例如，PSTN 端點撥話給使用者 （Lync 受話者）。 使用者的決定 PSTN 使用者應該轉寄給使用者 B （Lync 使用者）。 按下以講話 PSTN 使用者同意 PSTN 使用者保留狀態，並呼叫使用者 B 使用者的呼叫使用者的位置。 使用者的轉接通話上-保留給使用者 b。

**諮詢的呼叫轉接通話流程**

![依位置路由會議圖表](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "依位置路由會議圖表")

當使用者啟用位置型路由啟始諮詢來電轉接的 PSTN 端點 （如如上圖所示） 時，這會建立兩個作用中呼叫、 一次呼叫之間 PSTN 使用者與 Lync 使用者的以及其他之間 Lync 使用者的與 Lync 使用者 b。下列行為是由位置型路由會議應用程式強制執行：

  - 如果呼叫的 SIP 主幹路由 PSTN 重新路由傳送至網站 Lync 使用者 B （亦即轉接的目標） 位於、，然後將允許來電轉接; PSTN 通話授權否則請諮詢的來電轉接會被封鎖。 這項授權會根據傳送的方的位置路由至 PSTN 端點作用中的呼叫的 SIP 主幹與位於相同網路站台正在執行。

  - 如果 SIP 主幹路由內送的 PSTN 通話無法將通話路由傳送至網站： 轉移的方 （Lync 使用者 B） 位於或轉接的廠商位於不明的網路網站的權限，然後諮詢通話轉接至 PSTN端點 （亦即來電轉接的目標） 會被封鎖。

下表說明如何以位置為主的路由限制會套用諮詢轉接位置型路由會議應用程式。 雖然 PBX 端點不是直接與網路網站相關聯，PBX 連接至 SIP 主幹可被指派的網路網站。 因此，PBX 端點可以間接網路與網站產生關聯。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>轉接的通話方的網路網站</p></td>
<td><p>來電轉接的目標的網路網站</p></td>
<td><p>行為</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>Lync 使用者在相同的網路網站 （亦即網站 1）</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>Lync 使用者在不同的網路網站 (亦即 site 2)</p></td>
<td><p>將不允許諮詢轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>不明的網路網站中的 Lync 使用者</p></td>
<td><p>將不允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>同盟的 Lync 使用者</p></td>
<td><p>將不允許諮詢轉接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 端點</p></td>
<td><p>在相同的網站 （亦即網站 1） 的 PBX 端點</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>在不同的站台 (亦即 site 2) 的 PBX 端點</p></td>
<td><p>將不允許諮詢轉接</p></td>
</tr>
<tr class="even">
<td><p>在相同的網站 （亦即網站 1） 的 PBX 端點</p></td>
<td><p>PSTN 端點</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>在不同的網站 (亦即 site 2) 的 PBX 端點</p></td>
<td><p>PSTN 端點</p></td>
<td><p>將不允許諮詢轉接</p></td>
</tr>
<tr class="even">
<td><p>站台中的 PBX 端點</p></td>
<td><p>Lync 使用者在相同的網路網站 （亦即網站 1）</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>站台中的 PBX 端點</p></td>
<td><p>Lync 使用者在不同的網路網站 (亦即 site 2)</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="even">
<td><p>站台中的 PBX 端點</p></td>
<td><p>不明的網路網站中的 Lync 使用者</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
<tr class="odd">
<td><p>站台中的 PBX 端點</p></td>
<td><p>同盟的 Lync 使用者</p></td>
<td><p>將允許諮詢轉接</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

