---
title: Lync Server 2013： Location-Based 路由的部署程式
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
ms.openlocfilehash: f9d2dfa15dce07fa66678932d8d765ec7308ba75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526920"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中 Location-Based 路由的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

本主題提供設定 Location-Based 路由的處理常式的概述。 您必須先部署 Lync Server Enterprise Edition 或 Standard Edition with Enterprise Voice，才能設定 Location-Based 路由。 當您部署企業語音時，已安裝並啟用 Location-Based 路由所需的元件。

### <a name="location-based-routing-deployment-process"></a>Location-Based 路由部署程式

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
<td><p>部署企業語音</p></td>
</tr>
<tr class="even">
<td><p>驗證您的企業語音部署</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>設定網路地區、網站及子網</p></td>
<td><ul>
<li><p>建立網路地區</p></li>
<li><p>建立網路網站</p></li>
<li><p>將子網與網路網站產生關聯</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>關於網路區域、網站和子網路<br />
建立或修改網路地區<br />
建立或修改網站<br />
建立子網與網路網站的關聯</p></td>
</tr>
<tr class="even">
<td><p>設定 Location-Based 路由</p></td>
<td><ul>
<li><p>建立語音路由原則</p></li>
<li><p>針對每個主幹定義個別主幹設定</p></li>
<li><p>修改語音原則</p></li>
<li><p>啟用 Location-Based 路由設定</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>部署範例

下列部署是用來進一步說明 Location-Based 路由所啟用的機制。

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>傳入 PSTN 通話

系統管理員可以讓已定義的主幹將通話路由傳送至「Site 1 Gateway」，以進行 Location-Based 路由傳送，並使 "Site 1 Gateway" 與 Site 1 產生關聯。 啟用後，透過 "Site 1 Gateway" 路由傳送的通話只會路由傳送至位於網站1的使用者。 透過「Site 1 Gateway」主幹路由傳送至不同網站中使用者的所有通話（例如 Site 2）都會遭到封鎖，以避免 PSTN 通話旁路。

透過 "Site 1 Gateway" 進行的所有傳入 PSTN 通話，只允許路由傳送至位於網站1的端點。 例如，當 "Lync user 1" 前往 site 2 時，所有經由 "Site 1 Gateway" 的內送 PSTN 通話，將不會路由至位於 site 2 中的「Lync user 1」端點。 如果 "Lync user 1" 前往無法判斷使用者位置的未知網路網站，則會套用相同的路由規則。

下表概述此內容中的「Lync user 1」的使用者經驗。


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
<th>Lync 使用者1位於網路 site 1 的端點</th>
<th>位於網路 site 2 的 Lync 使用者1端點</th>
<th>位於未知網路網站的 Lync 使用者1端點</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1的撥入 PSTN 來電</p></td>
<td><p>呼叫會路由傳送至此位置的端點</p></td>
<td><p>通話不會路由到此位置的端點</p></td>
<td><p>通話不會路由到此位置的端點</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>呼出 PSTN 通話

語音路由是以直接指派給使用者的語音原則，以及指派給網路網站的語音路由原則所參考。 這兩個原則都包含路由參考，可用來將通話路由傳送成不同的方式。 例如，管理員可以為位於網路 site 1 中的所有使用者定義一個語音路由原則，以便透過「Site 1 Gateway」路由傳送所有撥出電話，而部分使用者的語音原則則透過「Site 2 閘道」定義所有撥出電話的路由。 當這些使用者位於網路網站1時，其輸出通話將透過「網站1閘道」路由傳送。

當使用者位於為 Location-Based 路由設定之網路網站時，網路網站的語音路由原則路由會覆寫使用者的語音原則路由。 此規則對於暫時移至不同網站的使用者尤其有用。 在此特定案例中，使用者將永遠使用本機到其位置的閘道;如果 "Lync user 3" 位於 "Site 2"，他的所有撥出電話都會透過「Site 2 閘道」路由傳送，但如果是前往 site 1，他在 site 1 進行的所有撥出呼叫都會透過 "Site 1 Gateway" 進行路由傳送。

下表說明 Lync 使用者1的使用者經驗，可從下列網路網站撥出電話。


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
<th>網路網站1</th>
<th>網路網站2</th>
<th>未啟用 Location-Based 路由的未知網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥出電話的授權</p></td>
<td><p>Lync 使用者1語音原則</p></td>
<td><p>Lync 使用者1語音原則</p></td>
<td><p>Lync 使用者1語音原則</p></td>
</tr>
<tr class="even">
<td><p>路由撥出通話</p></td>
<td><p>網站1語音路由原則</p></td>
<td><p>網站2語音路由原則</p></td>
<td><p>使用者的語音原則，且僅限未啟用 Location-Based 路由的系統</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>通話轉接及轉寄

當轉接來電或轉寄來電時，通話的路由會受到 Location-Based 路由的影響。

下表描述 Lync 使用者1將 PSTN 通話轉接或轉寄給另一個 Lync 使用者的功能。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者起始來電轉接或轉寄</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網站中的 Lync 使用者未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1</p></td>
<td><p>允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
</tr>
</tbody>
</table>

  
下表說明 Location-Based 路由會如何根據正在轉接的 Lync 使用者位置（ (Lync 使用者2、Lync 使用者4等) 至 PSTN 端點），如何影響通話的路由


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>轉接或轉寄通話的終點</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網站中的 Lync 使用者未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>呼叫轉寄或轉接透過 site 1 語音路由原則及透過 Site 1 閘道的方式路由傳送</p></td>
<td><p>呼叫轉寄或轉接透過 site 2 語音路由原則，以及透過 Site 2 閘道的出局進行路由</p></td>
<td><p>呼叫轉寄或轉接透過 Lync 使用者語音原則傳送，並透過未啟用位置基礎路由 (的閘道來傳送（如果有的話）) </p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同時震鈴

在範例拓撲中設定位置基礎路由之後，會強制執行下列互動。

下表說明 Location-Based 路由是否允許不同的 Lync 使用者同時震鈴 (（例如，Lync 使用者2、Lync 使用者4等) ）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>傳入 PSTN 通話目標</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網站中的 Lync 使用者未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1</p></td>
<td><p>允許同時振鈴</p></td>
<td><p>不允許同時振鈴</p></td>
<td><p>不允許同時振鈴</p></td>
</tr>
</tbody>
</table>

  
下表說明 Location-Based 路由是否允許從不同的 Lync 使用者同時撥打 PSTN 端點 (例如，Lync 使用者2、Lync 使用者4等) 。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時環目標</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網站中的 Lync 使用者未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync user 1 行動電話 (PSTN 端點) </p></td>
<td><p>透過網路 site 1 的語音路由原則及透過 site 1 閘道的出局進行路由傳送的通話</p></td>
<td><p>透過網路 site 2 的語音路由原則及透過 site 2 閘道的傳出的通話</p></td>
<td><p>透過來電者語音原則路由傳送，並透過未啟用 Location-Based 路由的 PSTN 閘道進行出局</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

