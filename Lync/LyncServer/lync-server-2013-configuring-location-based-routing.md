---
title: Lync Server 2013：設定 Location-Based 路由
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
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517411"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Location-Based 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

Lync Server 2013 CU1，Location-Based 路由是 Enterprise Voice 的功能。 Location-Based 路由是通話管理功能，可控制 Lync Server 2013 CU1 路由傳送通話的方式。 它會根據 Lync 來電者的位置，強制限制通話是否可路由傳送至 PBX 或 PSTN 目的地。 Location-Based 路由根據來電者的網路位置，對 PSTN 通話套用呼叫授權規則。 來電者的位置取決於與來電者相連之網路子網相關聯的網路網站。 設定 Location-Based 路由需要先部署企業語音，然後設定網路地區、網站和子網。 這會設定啟用 Location-Based 路由的基礎。

在部署 Location-Based 路由之前，您必須先部署 Enterprise Voice，並設定網路地區、網站，並將網路子網與網路網站產生關聯。 完成後，您可以設定 Location-Based 路由。 如需如何設定網路地區、網站及子網的步驟，請參閱 [在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

本節會逐步引導您使用下列範例做為 Location-Based 路由的設定，如圖所示。

![Enterprise Voice 位置-基礎路由範例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 位置-基礎路由範例")

  
下表代表本範例中定義的使用者。


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
<td><p>新德里公司辦公室</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 公司辦公室</p></td>
<td><p>HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>未知的 (，例如旅館) </p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>Pbx</p></td>
<td><p>新德里公司辦公室</p></td>
<td><p>DEL-PBX-1、DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>Pbx</p></td>
<td><p>Hyderabad 公司辦公室</p></td>
<td><p>HYD-PBX-1、HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>Pstn</p></td>
<td><p>Unknown</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

下表代表此範例環境中所述的系統。


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
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1，轉送伺服器</p></td>
<td><p>任何</p></td>
<td><p>毫秒-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 閘道1</p></td>
<td><p>德里</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 閘道2</p></td>
<td><p>海德拉巴</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>德里</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>海德拉巴</p></td>
<td><p>RED PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定企業語音](lync-server-2013-configuring-enterprise-voice.md)

  - [在 Lync Server 2013 中部署網路地區、網站和子網](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [在 Lync Server 2013 中啟用 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

