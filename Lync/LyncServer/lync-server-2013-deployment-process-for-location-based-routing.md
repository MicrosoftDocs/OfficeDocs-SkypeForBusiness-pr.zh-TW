---
title: Lync Server 2013： 部署程序的位置型的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的位置型路由的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

本主題提供參與設定位置型的路由程序的概觀。 設定位置型路由之前，您必須部署 Lync Server Enterprise Edition 或 Standard Edition 與 Enterprise Voice。 已安裝並當您部署企業語音時，啟用位置型路由所需的元件。

### <a name="location-based-routing-deployment-process"></a>位置型路由的部署程序

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>所需群組和角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署企業語音</p></td>
<td><ul>
<li><p>設定主幹</p></li>
<li><p>建立語音原則</p></li>
<li><p>定義語音路由</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>部署 Enterprise Voice</p></td>
</tr>
<tr class="even">
<td><p>確認 Enterprise Voice 部署</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>設定網路地區、 網站及子網路</p></td>
<td><ul>
<li><p>建立網路地區</p></li>
<li><p>建立網路網站</p></li>
<li><p>夥伴子網路與網路網站</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>關於網路區域、網站和子網路<br />
建立或修改網路地區<br />
建立或修改網站<br />
將子網路與網站產生關聯</p></td>
</tr>
<tr class="even">
<td><p>設定位置型的路由</p></td>
<td><ul>
<li><p>建立語音路由原則</p></li>
<li><p>定義每個主幹的個別的主幹組態</p></li>
<li><p>修改語音原則</p></li>
<li><p>啟用位置型路由設定</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>範例部署

下列部署用來進一步說明啟用位置型路由的機制。

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>傳入 PSTN 通話

系統管理員可以啟用定義將通話路由傳送至 「 網站 1 閘道 」 以位置為主的路由主幹和閘道建立關聯 」 網站 1 」 的網站 1。 啟用之後，會透過 「 網站 1 閘道 」 路由傳送的呼叫會只是路由傳送至位於網站 1 中的使用者。 例如，將可防止 PSTN 通話費封鎖站台 2 透過目的地中不同的站台，使用者的 「 網站 1 閘道 」 主幹路由傳送的所有呼叫略都過。

只允許透過 「 網站 1 閘道 」 的所有內送 PSTN 通話路由傳送到位於網站 1 的端點。 例如，當 「 Lync 使用者 1 」 移動至站台 2，透過 「 網站 1 閘道 」 的所有內送 PSTN 通話將不會路由至 「 Lync 使用者 1 」 端點位於站台 2。 如果 「 Lync 使用者 1 」 移動至其中無法判斷使用者的位置未知的網路網站，則會套用相同的路由規則。

下表概述 「 Lync 使用者 1 」 在此內容中的使用者經驗。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Lync 使用者 1 端點位於網路網站 1</th>
<th>Lync 使用者 1 端點位於網路網站 2</th>
<th>Lync 使用者 1 端點位於不明的網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者 1 的內送的 PSTN 通話</p></td>
<td><p>來電會路由傳送至在此位置的端點</p></td>
<td><p>在此位置的端點無法路由傳送通話</p></td>
<td><p>在此位置的端點無法路由傳送通話</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>撥出 PSTN 電話

語音路由會直接指派給使用者的語音原則和指派給網路網站的語音路由原則內的參照。 這兩個原則包含可用來以不同方式路由傳送來電的路由的參照。 例如，系統管理員可以定義語音路由原則的所有使用者位於網路網站 1 來路由傳送透過 「 網站 1 閘道 」 的所有撥出通話，雖然某些使用者的語音原則定義透過 「 網站 2 閘道 」 的所有撥出電話路由。 雖然這些使用者位於網路網站 1，其輸出通話都會透過 「 網站 1 閘道 」 路由傳送。

當使用者位於設定位置型路由的網路網站時，網站的語音路由原則路由會覆寫使用者的語音原則路由。 此規則會特別有用的暫時將移至不同的站台的使用者。 在本例中特定使用者將一律使用是在本機至其位置; 閘道如果 「 Lync 使用者 3 」 是位在 「 網站 2 」，將透過 「 網站 2 閘道 」，路由傳送所有他撥出電話但如果他旅行網站 1，將會放置而他是在網站 1 他撥出電話路由透過 「 網站 1 閘道 」。

下表說明 Lync 使用者 1 將撥出電話設定為從下列網站的使用者經驗。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>網路網站 1</th>
<th>網路網站 2</th>
<th>不明的網路站台或未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥出電話的授權</p></td>
<td><p>Lync 使用者 1 的語音原則</p></td>
<td><p>Lync 使用者 1 的語音原則</p></td>
<td><p>Lync 使用者 1 的語音原則</p></td>
</tr>
<tr class="even">
<td><p>撥出電話路由</p></td>
<td><p>網站 1 語音路由原則</p></td>
<td><p>站台 2 語音路由原則</p></td>
<td><p>使用者的語音原則和僅提供給未啟用位置型路由的系統</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>來電轉接和轉寄郵件

當呼叫會轉接或轉寄時，路由傳送來電會受到位置型的路由。

下表說明 Lync 使用者 1 傳送或轉寄至另一位 Lync 使用者 PSTN 通話。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者初始化來電轉接或轉寄</th>
<th>Lync 使用者 2</th>
<th>Lync 使用者 4</th>
<th>未啟用位置型路由的網路網站中的 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者 1</p></td>
<td><p>轉接通話] 或 [允許傳輸</p></td>
<td><p>轉接通話] 或 [不允許轉接</p></td>
<td><p>轉接通話] 或 [不允許轉接</p></td>
</tr>
</tbody>
</table>

  
下表說明如何位置型路由會影響通話路由傳送的方式取決於所傳送之 Lync 使用者的位置 （Lync 使用者 2、 Lync 使用者 4 等等） 至 PSTN 端點


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫是轉接或轉接至其中的端點</th>
<th>Lync 使用者 2</th>
<th>Lync 使用者 4</th>
<th>未啟用位置型路由的網路網站中的 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>轉接通話] 或 [傳輸路由傳送到網站 1 語音路由原則及輸出透過網站 1 閘道</p></td>
<td><p>轉接通話] 或 [傳輸路由透過站台 2 語音路由原則和透過網站 2 閘道的輸出</p></td>
<td><p>轉接通話] 或 [傳輸路由傳送到輸出透過未啟用位置型路由 （如果有的話） 閘道與 Lync 使用者的語音原則</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同時響鈴

一旦位置型路由設定中的範例拓撲，則會強制執行下列互動。

下表說明是否依位置路由允許同時響鈴的不同 Lync 使用者 （亦即 Lync 使用者 2、 Lync 使用者 4 等）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>內送 PSTN 通話目標</th>
<th>Lync 使用者 2</th>
<th>Lync 使用者 4</th>
<th>未啟用位置型路由的網路網站中的 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者 1</p></td>
<td><p>允許同時響鈴</p></td>
<td><p>不允許同時響鈴</p></td>
<td><p>不允許同時響鈴</p></td>
</tr>
</tbody>
</table>

  
下表說明是否依位置路由允許同時響鈴的 PSTN 端點來自不同 Lync 使用者 （亦即 Lync 使用者 2、 Lync 使用者 4 等）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時響鈴目標</th>
<th>Lync 使用者 2</th>
<th>Lync 使用者 4</th>
<th>未啟用位置型路由的網路網站中的 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者 1 行動電話 （PSTN 端點）</p></td>
<td><p>透過網路網站 1 的語音路由原則和透過網站 1 閘道的輸出路由傳送來電</p></td>
<td><p>透過網路網站 2 的語音路由原則及輸出透過站台 2 閘道路由傳送來電</p></td>
<td><p>電話路由傳送到來電者的語音原則，並將 egress 透過 PSTN 閘道未啟用位置型的路由</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中依位置路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

