---
title: Lync Server 2013：同時響鈴
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013 中的同時響鈴

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

當呼叫方啟用同時撥打時，以位置為基礎的路由會分析呼叫方的位置，以及呼叫方的端點，判斷是否應該路由通話。

下表說明設定同時撥打的使用者，以及同時撥打的目標，是相同網路網站、不同網路網站或未知網路網站中的使用者。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>打入的 PSTN 通話</th>
<th>與被呼叫方位於相同的網路網站中</th>
<th>位於不同于被人的網路網站</th>
<th>位於未知的網路網站中，或未啟用以位置為基礎的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>允許同時撥打</p></td>
<td><p>不允許同時撥打</p></td>
<td><p>不允許同時撥打</p></td>
</tr>
</tbody>
</table>

  
下表說明 Lync 使用者（亦即 Lync 呼叫者）在同一個網路網站、不同網路網站或來自未知網路網站的呼叫。 被呼叫方有一個 PSTN 端點（亦即手機）設定為同時振鈴目標。 在這個案例中，以位置為基礎的路由會判斷是否應該將呼叫路由到被呼叫者的同時環目標（亦即手機）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時撥打目標</th>
<th>與被呼叫方位於相同的網路網站中</th>
<th>位於不同于被人的網路網站</th>
<th>位於未知的網路網站中，或未啟用以位置為基礎的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>透過來電者的網站語音路由策略允許同時撥打</p></td>
<td><p>透過來電者的網站語音路由策略允許同時撥打</p></td>
<td><p>透過呼叫者的語音原則允許同時撥打，以進行位置式路由的 trunks</p></td>
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

