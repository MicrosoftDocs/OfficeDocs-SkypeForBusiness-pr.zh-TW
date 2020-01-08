---
title: Lync Server 2013：適用于會議的位置路由概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895a89ee59edaf973ae5194658c4cdf12564542e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中針對會議位置路由的概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-19_

以位置為基礎的路由會議應用程式為 Lync 會議提供防範 PSTN 免付費旁路的機制。 應用程式會監視作用中的會議，並根據參與的 Lync 使用者的位置強制執行以位置為基礎的路由限制。

如果符合下列條件，則以位置為基礎的路由會議應用程式會決定是否要在 Lync 會議上強制執行基於位置的路由：

  - 會議召集人已啟用位置路由。 以位置為基礎的路由限制將只會套用至啟用位置式路由的使用者所組織的會議。

  - 至少有一個會議參與者是 PSTN 端點。 以位置為基礎的路由限制只適用于包含 PSTN 端點的會議。

  - PSTN 閘道用來將會議橋接至 PSTN 的網路網站，以及召集人與參與者的連線位置所在的網路網站。

[以位置為基礎的路由會議] 應用程式可防止 Lync 使用者和 PSTN 端點從不同的網路網站加入相同的會議。 如果啟用會議召集人進行位置式路由，會議應用程式會強制執行下列限制：

  - 可以加入 Lync 會議的端點，取決於已加入會議的端點，而且這個限制會依加入的端點而調整，而新的端點則會加入會議。 如果召集人和參與者是從相同的網路網站加入 Lync 會議，則 PSTN 端點（來自相同網路網站的另一個參與者），另一個參與者從不同的網路網站或來自未知網路網站的參與者，都可以起來.

  - 如果召集人和參與者是從不同或未知的網路網站加入會議，但如果 PSTN 呼叫 ingresses 來自 SIP 主幹系，且已啟用位置路由，則不允許 PSTN 端點加入會議。

  - 如果召集人與參與者全都從同一個網路網站加入會議，且有參與者從 PSTN 加入相同的會議，則不允許來自不同網路網站的 Lync 端點加入會議。

下表摘要列出了這些會議位置的路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>在任何指定點的會議中的使用者</p></td>
<td><p>允許使用者加入會議</p></td>
<td><p>不允許使用者加入會議</p></td>
</tr>
<tr class="even">
<td><p>從單一網路網站 Lync VoIP 用戶端使用者</p></td>
<td><p>從同一個網路網站 Lync VoIP 用戶端使用者</p>
<p>來自不同網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>聯盟 Lync VoIP 用戶端使用者</p>
<p>從 PSTN 端點加入的使用者</p></td>
<td><p>無</p></td>
</tr>
<tr class="odd">
<td><p>來自未知網路網站的 Lync VoIP 用戶端使用者</p></td>
<td><p>來自任何網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網站的 Lync VoIP 用戶端使用者</p>
<p>聯盟 Lync VoIP 用戶端使用者</p></td>
<td><p>透過 PSTN 端點加入的使用者</p></td>
</tr>
<tr class="even">
<td><p>來自不同網路網站的 Lync VoIP 用戶端使用者</p></td>
<td><p>來自任何網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>聯盟 Lync VoIP 用戶端使用者</p></td>
<td><p>透過 PSTN 端點加入的使用者</p></td>
</tr>
<tr class="odd">
<td><p>從單一網路網站與從 PSTN 端點加入的使用者進行 Lync VoIP 用戶端使用者</p></td>
<td><p>從同一個網路網站 Lync VoIP 用戶端使用者</p></td>
<td><p>來自不同網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>聯盟 Lync VoIP 用戶端使用者</p></td>
</tr>
</tbody>
</table>


下列是 [以位置為基礎的路由會議] 應用程式的其他特性：

  - 如果使用者不允許加入會議指定的位置路由限制，則使用者呼叫會議將會遭到拒絕，而他的 Lync 用戶端會報告通話未完成或已結束。

  - 使用以位置為基礎的路由 enforcements 加入會議的 PSTN 端點不會限制加入會議，無論端點是透過不是以位置式路由的幹線來連接。

  - 透過不是出局呼叫的 SIP 幹線連線至 Mediations 伺服器的 PBX 系統，將會擁有與在已定義 SIP 幹線之相同網路網站中的 Lync 使用者相同的 enforcements。 例如，PSTN 端點將能夠加入與 PBX 使用者和 Lync 使用者位於相同網路網站中的會議;否則，如果 PBX 使用者與 Lync 使用者不在不同的網路網站，則不允許 PSTN 端點加入會議。

</div>

<span> </span>

</div>

</div>

</div>

