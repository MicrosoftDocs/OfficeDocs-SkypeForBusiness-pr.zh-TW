---
title: Lync Server 2013：位置基礎路由的部署程序
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
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的位置基礎路由的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

本主題提供設定以位置為基礎的路由所涉及之程式的概覽。 您必須先使用企業語音部署 Lync Server Enterprise Edition 或標準版，才能設定以位置為基礎的路由。 部署企業語音時，已安裝並啟用位置路由所需的元件。

### <a name="location-based-routing-deployment-process"></a>以位置為基礎的路由部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>必要的群組和角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署企業語音</p></td>
<td><ul>
<li><p>設定 Trunks</p></li>
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
<td><p>設定網路區域、網站和子網</p></td>
<td><ul>
<li><p>建立網路區域</p></li>
<li><p>建立網路網站</p></li>
<li><p>將子網與網路網站建立關聯</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>關於網路區域、網站和子網<br />
建立或修改網路區域<br />
建立或修改網路網站<br />
將子網與網路網站建立關聯</p></td>
</tr>
<tr class="even">
<td><p>設定以位置為基礎的路由</p></td>
<td><ul>
<li><p>建立語音路由策略</p></li>
<li><p>針對每個幹線定義不同的幹線設定</p></li>
<li><p>修改語音原則</p></li>
<li><p>啟用以位置為基礎的路由設定</p></li>
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

下列部署是用來進一步說明根據位置式路由啟用的機制。

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>打入的 PSTN 電話

系統管理員可以讓已定義的幹線將呼叫路由至「Site 1 閘道」以進行位置路由，並將「網站1閘道」與網站1產生關聯。 一旦啟用，透過 "Site 1 閘道" 路由的通話將只會路由至位於網站1的使用者。 透過「網站1閘道」幹線傳送給不同網站中的使用者的所有通話，例如 Site 2 將遭到封鎖，以避免 PSTN 免付費旁路。

透過「網站1閘道」進行的所有撥出 PSTN 呼叫只允許路由至位於網站1中的端點。 例如，當「Lync 使用者1」移至 site 2 時，所有透過「Site 1 閘道」傳入的 PSTN 呼叫，都不會路由至位於網站2中的 [Lync 使用者 1] 端點。 如果「Lync 使用者1」移至無法判斷使用者位置的未知網路網站，就會套用相同的傳送規則。

下表概述了在這個內容中，「Lync 使用者1」的使用者經驗。


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
<th>Lync 使用者1位於網路 site 2 中的端點</th>
<th>Lync user 1 端點位於未知網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1的入站 PSTN 呼叫</p></td>
<td><p>通話路由到此位置的端點</p></td>
<td><p>通話未路由到此位置中的端點</p></td>
<td><p>通話未路由到此位置中的端點</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>出局 PSTN 通話

在直接指派給使用者的語音原則中，以及指派給網路網站的語音路由策略，都會參照語音路由。 這兩個原則都包含對路由的參照，可以用來以不同方式路由通話。 例如，管理員可以為位於 network site 1 中的所有使用者定義語音路由策略，以便透過「Site 1 閘道」路由所有出站通話，而部分使用者的語音原則則是透過「Site 2 閘道」定義所有出站通話的路線。 當這些使用者位於網路網站1時，其輸出呼叫將會透過「網站1閘道」路由。

當使用者位於設定為位置路由的網路網站時，網路網站的語音路由策略路由會覆寫使用者的語音原則路由。 此規則對於暫時移至不同網站的使用者特別有用。 在這個特定情況下，使用者將永遠使用本機的閘道來進行位置。如果 "Lync 使用者 3" 位於「Site 2」，則所有的撥出通話都將透過「Site 2 閘道」路由，但如果他移至 site 1，則會透過「Site 1 閘道」路由傳送給網站1的所有撥出通話。

下表說明 Lync 使用者1從下列網路網站撥出電話的使用者經驗。


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
<th>未知的網路網站，或未啟用以位置為基礎的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥出通話的授權</p></td>
<td><p>Lync 使用者1語音原則</p></td>
<td><p>Lync 使用者1語音原則</p></td>
<td><p>Lync 使用者1語音原則</p></td>
</tr>
<tr class="even">
<td><p>傳送撥出通話</p></td>
<td><p>網站1語音路由策略</p></td>
<td><p>Site 2 語音路由策略</p></td>
<td><p>使用者的語音原則，且僅適用于不支援位置路由的系統</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>來電轉接與轉寄

轉接或轉接來電時，通話的路由會受到以位置為基礎的路由影響。

下表說明 Lync 使用者1將 PSTN 來電轉接或轉寄給另一個 Lync 使用者的情況。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者啟動來電轉接或轉寄</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網路網站中的 Lync 使用者未啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1</p></td>
<td><p>允許呼叫轉寄或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
</tr>
</tbody>
</table>

  
下表說明如何根據傳送給 PSTN 端點的 Lync 使用者的位置（Lync 使用者2、Lync 使用者4等），來視位置路由影響呼叫路由的方式。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>轉接至或轉寄通話的終點</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網路網站中的 Lync 使用者未啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>呼叫轉寄或轉接透過 site 1 語音路由原則與外出，透過 Site 1 閘道進行路由</p></td>
<td><p>呼叫轉寄或轉移是透過 site 2 語音路由原則與外出，透過 Site 2 閘道進行路由</p></td>
<td><p>呼叫轉寄或轉接是透過 Lync 使用者語音原則傳送，而外出則是透過未啟用位置路由的閘道（如果有的話）來傳送。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同時響鈴

在範例拓撲中設定位置式路由之後，就會強制執行下列互動。

下表說明根據位置路由是否允許不同的 Lync 使用者同時撥打（亦即 Lync 使用者2、Lync 使用者4等）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>打入的 PSTN 通話目標</th>
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網路網站中的 Lync 使用者未啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1</p></td>
<td><p>允許同時撥打</p></td>
<td><p>不允許同時撥打</p></td>
<td><p>不允許同時撥打</p></td>
</tr>
</tbody>
</table>

  
下表說明根據位置路由是否允許從不同的 Lync 使用者同時撥打 PSTN 端點（亦即 Lync 使用者2、Lync 使用者4等）。


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
<th>Lync 使用者2</th>
<th>Lync 使用者4</th>
<th>網路網站中的 Lync 使用者未啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者1行動電話（PSTN 端點）</p></td>
<td><p>呼叫是透過網路 site 1 的語音路由原則與外出，透過 site 1 閘道傳送</p></td>
<td><p>呼叫是透過網路網站2的語音路由原則與外出，透過 site 2 閘道傳送</p></td>
<td><p>通話是透過呼叫者語音原則路由的，而且會透過不支援位置路由的 PSTN 閘道進行出口</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃位置基礎路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

