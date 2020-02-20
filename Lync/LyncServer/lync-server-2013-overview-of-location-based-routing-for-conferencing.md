---
title: 電話撥入會議的位置型路由的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 863cd213fb28d3adeedc04a5d46e4310ea4cd83b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議位置型路由的概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-19_

位置型路由會議應用程式提供 Lync 會議的 PSTN 通話費防護機制略過。 應用程式監視作用中的會議，並強制執行的位置型路由限制根據參與 Lync 使用者的位置。

位置型路由會議應用程式會決定是否是如果符合下列準則，則會強制執行 Lync 會議位置型的路由：

  - 會議召集人會啟用位置型的路由。 位置型路由限制將會是只套用至由位置型路由已啟用的使用者安排的會議。

  - 至少一位會議參與者是 PSTN 端點。 位置型路由限制將僅適用於包含 PSTN 端點的會議。

  - 用來橋接至 PSTN 會議的 PSTN 閘道的所在位置以及從何處網際網路連接參與者與召集人的網路站台的網路網站。

位置型路由會議應用程式可防止 Lync 使用者和來自不同網路網站的 PSTN 端點，才能在同一場會議參與。 如果會議的召集人啟用位置型的路由，會議應用程式強制執行下列限制：

  - 可加入 Lync 會議的端點取決於已加入會議的端點這項限制會調整以加入的端點離開和新端點加入會議。 如果召集人與參與者加入相同的網路網站，然後將 PSTN 端點的 Lync 會議，允許從相同網路站台、 從不同的網路網站的其他參與者或從不明的網路網站參與者的另一位參與者加入。

  - 如果召集人與參與者加入會議從不同] 或 [未知的網路網站，不允許加入會議，如果 PSTN 通話 ingresses 從啟用位置型路由的 SIP 主幹的 PSTN 端點。

  - 如果召集人與參與者所有加入會議從相同網路網站，且沒有加入相同從 PSTN 會議的參與者，不允許從不同的網路網站的 Lync 端點加入會議。

下表摘要說明這些會議位置型路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>在任何特定時間點會議中的使用者</p></td>
<td><p>允許加入會議的使用者</p></td>
<td><p>不允許加入會議的使用者</p></td>
</tr>
<tr class="even">
<td><p>從單一網路網站的 Lync VoIP 用戶端使用者</p></td>
<td><p>Lync VoIP 用戶端使用者從相同網路網站</p>
<p>Lync VoIP 用戶端使用者從不同的網路網站</p>
<p>Lync VoIP 用戶端使用者的未知的網路站台</p>
<p>同盟的 Lync VoIP 用戶端使用者</p>
<p>使用者加入從 PSTN 端點</p></td>
<td><p>無</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP 用戶端使用者的未知的網路站台</p></td>
<td><p>Lync VoIP 用戶端使用者從任何網站</p>
<p>Lync VoIP 用戶端使用者的未知的站台</p>
<p>同盟的 Lync VoIP 用戶端使用者</p></td>
<td><p>使用者加入透過 PSTN 端點</p></td>
</tr>
<tr class="even">
<td><p>Lync VoIP 用戶端使用者從不同的網路網站</p></td>
<td><p>Lync VoIP 用戶端使用者從任何網路網站</p>
<p>Lync VoIP 用戶端使用者的未知的網路站台</p>
<p>同盟的 Lync VoIP 用戶端使用者</p></td>
<td><p>使用者加入透過 PSTN 端點</p></td>
</tr>
<tr class="odd">
<td><p>從單一的網站和來自 PSTN 端點加入使用者的 Lync VoIP 用戶端使用者</p></td>
<td><p>Lync VoIP 用戶端使用者從相同網路網站</p></td>
<td><p>Lync VoIP 用戶端使用者從不同的網路網站</p>
<p>Lync VoIP 用戶端使用者的未知的網路站台</p>
<p>同盟的 Lync VoIP 用戶端使用者</p></td>
</tr>
</tbody>
</table>


以下是依位置路由會議應用程式的其他特性：

  - 時不允許使用者加入會議，指定位置型路由限制時，會拒絕會議的使用者呼叫而其 Lync 用戶端將報告，在呼叫未完成，或已經結束。

  - 以位置為主的路由 enforcements 會議將不會限制為不論其狀態加入會議，如果將端點加入未啟用位置型路由主幹透過 PSTN 端點加入。

  - 連接至 Mediations 伺服器透過 SIP 主幹，不會不輸出至 PSTN 通話的 PBX 系統會有相同的 enforcements 為 Lync 使用者位於相同網路站台定義 SIP 主幹的位置。 例如，PSTN 端點將能夠加入 PBX 使用者與 Lync 使用者的會議，如果他們都位於相同的網路網站;否則，將不允許 PSTN 端點，如果 PBX 使用者位於不同的網路站台比 Lync 使用者加入會議。

</div>

<span> </span>

</div>

</div>

</div>

