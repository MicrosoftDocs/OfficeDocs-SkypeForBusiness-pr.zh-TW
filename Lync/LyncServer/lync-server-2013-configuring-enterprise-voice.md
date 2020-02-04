---
title: Lync Server 2013：配置企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中設定企業語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

若要部署企業語音，您需要設定下列專案：

  - 建立主幹

  - 定義語音原則

  - 定義語音路線

  - 允許使用者使用企業語音

<div>

## <a name="create-a-trunk"></a>建立主幹

您必須在企業語音部署中定義 trunks。 對於以位置為基礎的路由，您必須針對每個幹線建立幹線設定。 使用 Lync Server 拓撲建立器來定義您的 trunks，並使用 Lync Server Windows PowerShell 命令、新的 New-cstrunkconfiguration，或 Lync Server 控制台來定義相對應的幹線設定。 在[Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)中啟用位置路由的詳細資訊，請參閱在 Lync 設定上啟用位置路由的方式（在 Trunks 中啟用位置路由）一節。 在這個範例中，下表說明這個案例中使用的 trunks。

如需詳細資訊，請參閱[在 Lync Server 2013 的拓撲建立器中定義其他 trunks](lync-server-2013-define-additional-trunks-in-topology-builder.md)。


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
<th>主幹名稱</th>
<th>系統類型</th>
<th>名稱</th>
<th>位置</th>
<th>中繼伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>幹線 1 DEL-GW</p></td>
<td><p>PSTN 閘道</p></td>
<td><p>DEL-GW</p></td>
<td><p>新德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主幹 2 HYD-GW</p></td>
<td><p>PSTN 閘道</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>幹線 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>新德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主幹 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>定義語音原則

您必須為企業語音部署定義語音原則。 如果您只需要使用位置的路由，請定義語音原則，以將位置基礎路由限制強制到使用者的子集。 在這個範例中，下表說明此案例中使用的語音原則。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

如需詳細資訊，請參閱設定[語音原則和 PSTN 使用記錄，以在 Lync Server 2013 中授權呼叫功能與許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>語音原則1</th>
<th>語音原則2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>語音原則識別碼</p></td>
<td><p>新德里語音原則</p></td>
<td><p>Hyderabad 語音原則</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用量、PBX Del 用法、PBX Hyd 使用量</p></td>
<td><p>Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>虛假</p></td>
<td><p>虛假</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>定義語音路由

您必須為企業語音部署定義語音路由。 在這個範例中，下表說明此案例中使用的語音路線。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

如需詳細資訊，請參閱[在 Lync Server 2013 中設定出站通話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。


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
<th></th>
<th>語音路由1</th>
<th>語音路由2</th>
<th>語音路由3</th>
<th>語音路由4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>新德里路線</p></td>
<td><p>Hyderabad 路線</p></td>
<td><p>PBX Del 路由</p></td>
<td><p>PBX Hyd 路由</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用量</p></td>
<td><p>Hyderabad 使用量</p></td>
<td><p>PBX Del 用法</p></td>
<td><p>PBX Hyd 使用量</p></td>
</tr>
<tr class="odd">
<td><p>去</p></td>
<td><p>幹線 1 DEL-GW</p></td>
<td><p>主幹 2 HYD-GW</p></td>
<td><p>幹線 3 DEL-PBX</p></td>
<td><p>主幹 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>允許使用者使用企業語音

允許使用者使用企業語音，並將您先前定義的語音原則指派給他們。 在這個範例中，下表說明這個案例中所使用的作業。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

如需詳細資訊，請參閱[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位於新德里的使用者</th>
<th>位於 Hyderabad 的使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>相關的語音原則</p></td>
<td><p>新德里語音原則</p></td>
<td><p>Hyderabad 語音原則</p></td>
</tr>
<tr class="even">
<td><p>範例使用者</p></td>
<td><p>DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定位置基礎路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

