---
title: Lync Server 2013：規劃撥出語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5315b18e83b84980ff6d61e5385626e104a5e1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>在 Lync Server 2013 中規劃撥出語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

[輸出呼叫路由] 適用于發往公用交換電話網絡（PSTN）閘道、幹線或私人分支 exchange （PBX）的呼叫。 當使用者撥打電話時，伺服器會根據需要將電話號碼標準化為. 164 格式，並嘗試將它與 SIP URI 相符。 如果伺服器無法進行相符，就會根據所提供的撥號字串來套用輸出呼叫路由邏輯。 您可以透過設定下表所述的伺服器設定，來定義該邏輯。

### <a name="lync-server-outbound-call-routing-settings"></a>Lync Server 輸出呼叫路由設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>面向</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥號對應表</p></td>
<td><p>撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。</p></td>
</tr>
<tr class="even">
<td><p>正常化規則</p></td>
<td><p>正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。 根據撥號位置，以及進行通話的人員或連絡人物件，可能會以不同方式來轉譯和翻譯相同的撥號字串。 與特定位置相關聯的一組正常化規則會構成撥號方案。</p></td>
</tr>
<tr class="odd">
<td><p>語音原則</p></td>
<td><p>語音原則會將一或多個 PSTN 使用記錄與一位使用者或一組使用者相關聯。 語音原則也提供您可以啟用或停用的通話功能清單。</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用記錄</p></td>
<td><p>PSTN 使用記錄會指定呼叫類別（例如內部、當地或長途），這些使用者可以由不同的使用者或使用者群組在組織中進行。</p></td>
</tr>
<tr class="odd">
<td><p>通話路線</p></td>
<td><p>通話路由會將目的地電話號碼與特定的 trunks 和 PSTN 使用狀況記錄建立關聯。 PSTN 閘道被視為幹線。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本節內容

本節提供設定下列出站呼叫路由伺服器設定的指導方針：

  - <span></span>  
    [Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Lync Server 2013 中的語音原則](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 SIP 中繼](lync-server-2013-sip-trunking.md)  
[Lync Server 2013 中的直接 SIP 連線](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

