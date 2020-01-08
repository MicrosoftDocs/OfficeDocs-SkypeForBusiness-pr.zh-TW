---
title: Lync Server 2013：設定容錯移轉路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>在 Lync Server 2013 中設定容錯移轉路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

下列範例顯示管理員如何定義容錯移轉路線，以便在達拉斯 GW1 關閉或無法使用的情況下使用。 下表說明所需的配置變更。

### <a name="table-1-user-policy"></a>資料表1。 使用者原則

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者原則</th>
<th>電話使用方式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設通話原則</p></td>
<td><p>局部</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>雷德蒙當地原則</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>達拉斯通話原則</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>表格2。 到達

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>路線名稱</th>
<th>數位模式</th>
<th>電話使用方式</th>
<th>去</th>
<th>關</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>雷德蒙的本機路線</p></td>
<td><p>^\+1（425 | 206 | 253）（\d{7}） $</p></td>
<td><p>局部</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>紅-GW1</p>
<p>紅-GW2</p></td>
</tr>
<tr class="even">
<td><p>達拉斯本機路線</p></td>
<td><p>^\+1（972 | 214 | 469）（\d{7}） $</p></td>
<td><p>局部</p></td>
<td><p>Trunk3</p></td>
<td><p>達拉斯-GW1</p></td>
</tr>
<tr class="odd">
<td><p>通用路線</p></td>
<td><p>^\+?（\d *） $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>紅-GW1</p>
<p>紅-GW2</p>
<p>達拉斯-GW1</p></td>
</tr>
<tr class="even">
<td><p>達拉斯使用者路由</p></td>
<td><p>^\+?（\d *） $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>達拉斯-GW1</p></td>
</tr>
</tbody>
</table>


在表格1中，在達拉斯通話原則中，在 DallasUsers 電話使用量之後，就會新增 GlobalPSTNHopoff 的電話使用方式。 這可讓使用達拉斯通話原則進行呼叫，以使用針對 GlobalPSTNHopoff 電話使用設定的路線（如果無法使用 DallasUsers 電話使用方式的路線）。

</div>

<span> </span>

</div>

</div>

</div>

