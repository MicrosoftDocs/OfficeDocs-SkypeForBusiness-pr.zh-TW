---
title: Lync Server 2013： 設定位置型的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e8877c4691decfe0c2e65fd820e97432e095aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>設定 Lync Server 2013 中的位置型路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-12_

Lync Server 2013 CU1、 位置型的路由是企業語音功能。 位置型路由會控制如何來電會路由傳送的 Lync Server 2013 CU1 通話管理功能。 它會強制執行是否來電可被路由傳送至 PBX 或 PSTN 目的地取決於 Lync 發話者的位置的限制。 位置型路由將通話授權規則套用至發話者的網路位置為基礎的 PSTN 通話。 發話者的位置取決於來電者連接的網路網站的網路子網路相關聯。 若要設定位置型的路由需要先部署 Enterprise Voice，然後再設定網路地區、 網站及子網路。 這會啟用位置型路由 foundation 設定。

之前部署位置型的路由，您必須先部署 Enterprise Voice、 網路地區、 網站，並設定網路子網路關聯至您的網路網站。 完成之後，您可以設定位置型的路由。 如需如何設定網路地區、 網站及子步驟，請參閱[部署進階 Enterprise Voice 功能在 Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

本節會引導您完成位置型的路由，請使用下列範例為圖例的組態。

![Enterprise Voice 位置型的路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 位置型的路由範例")

  
下表代表此範例中所定義的使用者。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>端點類型</th>
<th>位置</th>
<th>使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>德里的公司辦公室</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 公司辦公室</p></td>
<td><p>HYD-LYNC-1、 HYD-LYNC-2、 HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>未知 （亦即旅館）</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>德里的公司辦公室</p></td>
<td><p>DEL-PBX-1、 DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 公司辦公室</p></td>
<td><p>HYD-PBX-1、 HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Unknown</p></td>
<td><p>PSTN-1、 PSTN-2、 PSTN-3</p></td>
</tr>
</tbody>
</table>

  

下表代表此範例環境中所示的系統。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>系統</th>
<th>位置</th>
<th>姓名</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 集區</p></td>
<td><p>任何</p></td>
<td><p>LS PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1，中繼伺服器</p></td>
<td><p>任何</p></td>
<td><p>MS PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 閘道 1</p></td>
<td><p>德里</p></td>
<td><p>DEL GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 閘道 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>德里</p></td>
<td><p>DEL PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>紅色 PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定企業語音](lync-server-2013-configuring-enterprise-voice.md)

  - [部署網路地區、 網站及 Lync Server 2013 中的子網路](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [啟用 Lync Server 2013 中依位置路由](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署 Lync Server 2013 中的進階的 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

