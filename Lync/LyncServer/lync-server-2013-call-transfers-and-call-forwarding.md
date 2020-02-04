---
title: Lync Server 2013：通話轉接和來電轉接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512deaf8af03f112e35443c25e46685c42a2f2e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 中的通話轉接和來電轉接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

在涉及 PSTN 端點時，以位置為基礎的路由會分析 calle 端點的位置，以及將來電轉接或轉接到哪個端點（亦即傳輸/轉寄目標）。 位置路由根據兩個端點的位置，決定要轉移還是轉寄通話。

下表說明 Lync 使用者在使用 PSTN 端點的通話中的情況，而 Lync 使用者將來電轉接到另一個 Lync 使用者。 根據 transferee 端點的網路網站位置而定，以位置為基礎的路由會影響來電轉接或轉寄的傳送。

### <a name="initiating-call-transfer-or-forward"></a>啟動來電轉接或轉寄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者啟動來電轉接/轉寄</th>
<th>在使用者啟動來電轉接或轉寄時，目標端點位於相同的網路網站</th>
<th>在使用者啟動來電轉接或轉寄時，目標端點位於不同的網路網站</th>
<th>目標端點位於 [未知網路] 網站或 [網路網站] 未啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>允許呼叫轉寄或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
</tr>
</tbody>
</table>

  

例如：與 PSTN 端點通話中的 Lync 使用者會將來電轉接到相同網路網站中的另一個 Lync 使用者。 在這種情況下，允許來電轉接。

下表說明 Lync 使用者在與另一個 Lync 使用者的通話中的情況，且其中一個使用者將來電轉接到 PSTN 端點。 視通話的傳送物件位置而定，表格會詳細說明以位置為基礎的路由對通話的影響。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>來電轉接或轉接至 PSTN 端點

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>來電轉接/轉寄端點目標</th>
<th>同一網路網站中的 Lync 使用者</th>
<th>不同網路網站中的 Lync 使用者</th>
<th>無法在 [未知網路] 網站或 [網路] 網站中的一或兩個 Lync 使用者啟用位置路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>已轉移使用者的網站語音路由策略允許呼叫轉寄或轉接</p></td>
<td><p>已轉移使用者的網站語音路由策略允許呼叫轉寄或轉接</p></td>
<td><p>轉移的使用者語音原則只允許來電轉接或轉接，只透過 trunks，不支援以位置為基礎的路由</p></td>
</tr>
</tbody>
</table>

  
例如：與同一網路網站中的另一個 Lync 使用者通話中的 Lync 使用者，會將來電轉接到 PSTN 端點，並允許來電轉接。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的位置基礎路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

