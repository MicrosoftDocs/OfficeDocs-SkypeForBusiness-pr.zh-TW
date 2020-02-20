---
title: Lync Server 2013： 設定容錯移轉路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b012b1bbab693e9a95a64d1fb3150723523cb53d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>在 Lync Server 2013 中設定容錯移轉路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。

### <a name="table-1-user-policy"></a>表 1. 使用者原則

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
<td><p>Local</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Redmond 本地原則</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Dallas 通話原則</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>表 2. 路由

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
<th>路由名稱</th>
<th>號碼模式</th>
<th>電話使用方式</th>
<th>主幹</th>
<th>閘道</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Redmond 本地路由</p></td>
<td><p>^\+1(425|206|253)(\d{7})$</p></td>
<td><p>Local</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>紅色 GW1</p>
<p>紅色 GW2</p></td>
</tr>
<tr class="even">
<td><p>Dallas 本地路由</p></td>
<td><p>^\+1(972|214|469)(\d{7})$</p></td>
<td><p>Local</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas GW1</p></td>
</tr>
<tr class="odd">
<td><p>全域路由</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>紅色 GW1</p>
<p>紅色 GW2</p>
<p>Dallas GW1</p></td>
</tr>
<tr class="even">
<td><p>Dallas 使用者路由</p></td>
<td><p>^\+?(\d*)$</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>Dallas GW1</p></td>
</tr>
</tbody>
</table>


表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。

</div>

<span> </span>

</div>

</div>

</div>

