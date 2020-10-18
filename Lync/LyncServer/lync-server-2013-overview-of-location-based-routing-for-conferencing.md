---
title: Lync Server 2013：會議 Location-Based 路由的概述
description: Lync Server 2013：會議 Location-Based 路由的概述。
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
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577369"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中 Location-Based 用於會議之路由的概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-19_

Location-Based 路由會議應用程式可讓 Lync 會議防護 PSTN 收費旁路的機制。 應用程式會監控使用中的會議，並根據 Lync 使用者參與的位置，強制執行 Location-Based 路由限制。

Location-Based 路由會議應用程式會在符合下列準則時，決定是否要在 Lync 會議上強制執行 Location-Based 路由：

  - 已啟用會議召集人的 Location-Based 路由。 Location-Based 路由限制只會套用至已啟用 Location-Based 路由之使用者所組織的會議。

  - 至少有一個會議參與者為 PSTN 端點。 Location-Based 路由限制只適用于包括 PSTN 端點的會議。

  - PSTN 閘道用來將會議加入 PSTN 的網路網站，以及召集人和參與者連線所在的網路網站。

Location-Based 路由會議應用程式可防止 Lync 使用者和 PSTN 端點從不同的網路網站加入相同的會議。 如果為 Location-Based 路由啟用會議召集人，會議應用程式會強制執行下列限制：

  - 可以加入 Lync 會議的端點取決於已加入會議的端點，而且此限制會調整為加入的端點，並且將新的端點加入會議。 如果召集人和參與者從相同的網路網站加入 Lync 會議，則來自相同網路網站的另一位參與者，允許來自不同網路網站或來自未知網路網站之參與者的另一位參與者加入。

  - 如果召集人和參與者從不同或未知的網路網站加入會議，則不允許 PSTN 端點加入會議（如果 PSTN 通話 ingresses 從為 Location-Based 路由啟用的 SIP 主幹）。

  - 如果召集人和參與者全都從相同的網路網站加入會議，且有參與者加入來自 PSTN 的相同會議，則不允許來自不同網路網站的 Lync 端點加入會議。

下表摘要說明這些會議 Location-Based 路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>在會議中，任何指定點的使用者 (s) </p></td>
<td><p>允許加入會議的使用者 (s) </p></td>
<td><p>不允許使用者 (s) 加入會議</p></td>
</tr>
<tr class="even">
<td><p>Lync VoIP 用戶端使用者 (s) 從單一網路網站</p></td>
<td><p>來自相同網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自不同網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>同盟 Lync VoIP 用戶端使用者</p>
<p>從 PSTN 端點加入的使用者</p></td>
<td><p>無</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP 用戶端使用者 (s) 從未知的網路網站</p></td>
<td><p>任何網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網站的 Lync VoIP 用戶端使用者</p>
<p>同盟 Lync VoIP 用戶端使用者</p></td>
<td><p>透過 PSTN 端點加入使用者</p></td>
</tr>
<tr class="even">
<td><p>來自不同網路網站的 Lync VoIP 用戶端使用者</p></td>
<td><p>任何網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>同盟 Lync VoIP 用戶端使用者</p></td>
<td><p>透過 PSTN 端點加入使用者</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP 用戶端使用者 (s) 從單一網路網站，以及從 PSTN 端點加入的使用者</p></td>
<td><p>來自相同網路網站的 Lync VoIP 用戶端使用者</p></td>
<td><p>來自不同網路網站的 Lync VoIP 用戶端使用者</p>
<p>來自未知網路網站的 Lync VoIP 用戶端使用者</p>
<p>同盟 Lync VoIP 用戶端使用者</p></td>
</tr>
</tbody>
</table>


以下是 Location-Based 路由會議應用程式的其他特性：

  - 當使用者因 Location-Based 路由限制而不允許加入會議時，會拒絕使用者呼叫會議，而 Lync 用戶端會報告呼叫未完成或已結束。

  - 在加入具有 Location-Based 路由 enforcements 之會議的 PSTN 端點時，如果端點透過未啟用 Location-Based 路由的主幹加入，則不會限制加入會議的狀態。

  - 透過 SIP 主幹（未向 PSTN 撥出電話）連接至 Mediations Server 的 PBX 系統，將會與位於定義 SIP 主幹的相同網路網站中的 Lync 使用者具有相同的 enforcements。 例如，當 PSTN 端點可以加入具有 PBX 使用者的會議，以及 Lync 使用者位於相同的網站時，它會與其共用;否則，如果 PBX 使用者位於不同的網路網站（Lync 使用者除外），將不允許 PSTN 端點加入會議。

</div>

<span> </span>

</div>

</div>

</div>

