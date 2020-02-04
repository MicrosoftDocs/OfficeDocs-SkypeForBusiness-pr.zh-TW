---
title: Lync Server 2013：撥出電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>在 Lync Server 2013 中撥出電話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

針對位置路由的使用者的出站呼叫路由會受到使用者端點的網路位置的影響。 下表說明根據呼叫者終點的位置，以位置為基礎的路由會如何影響傳出通話的路由。

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>來電者撥入到 PSTN 的電話

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>使用者端點位於已啟用位置路由的網路網站中</th>
<th>使用者端點位於未知的網路網站中，或未啟用以位置為基礎的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥出通話的授權</p></td>
<td><p>根據使用者的語音原則，進行撥號授權</p></td>
<td><p>根據使用者的語音原則，進行撥號授權</p></td>
</tr>
<tr class="even">
<td><p>傳送撥出通話</p></td>
<td><p>根據網路網站的語音路由策略來傳送通話</p></td>
<td><p>通話是依據使用者的語音原則傳送，只能透過 trunks （如果有的話）啟用。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的位置基礎路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

