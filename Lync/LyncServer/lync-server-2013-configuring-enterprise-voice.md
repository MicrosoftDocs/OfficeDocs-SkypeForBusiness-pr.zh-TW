---
title: Lync Server 2013：設定企業語音
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
ms.openlocfilehash: 8a6c09bd44f9fc4b98488c7825f8cab1d3eea7f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中設定企業語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

若要部署 Enterprise Voice，您必須設定下列專案：

  - 建立主幹

  - 定義語音原則

  - 定義語音路由

  - 為使用者啟用企業語音

<div>

## <a name="create-a-trunk"></a>建立主幹

您必須在您的企業語音部署中定義主幹。 針對位置基礎路由，您必須為每個主幹建立主幹設定。 使用 Lync Server 拓撲產生器來定義主幹，並使用 Lync Server Windows PowerShell 命令、Get-cstrunkconfiguration 或 Lync Server 控制台定義對應的主幹設定。 有關如何啟用主幹設定上的位置基礎路由的詳細資訊，請參閱本節中的啟用位置基礎路由至主幹，在 [Lync Server 2013 中啟用位置基礎路由](lync-server-2013-enabling-location-based-routing.md)的主題。 在此範例中，下表說明此案例中使用的主幹。

如需詳細資訊，請參閱 [在 Lync Server 2013 中的拓撲產生器中定義其他主幹](lync-server-2013-define-additional-trunks-in-topology-builder.md)。


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
<th>姓名</th>
<th>位置</th>
<th>中繼伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主幹 1 DEL-GW</p></td>
<td><p>PSTN 閘道</p></td>
<td><p>DEL-GW</p></td>
<td><p>德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主幹 2 HYD-GW</p></td>
<td><p>PSTN 閘道</p></td>
<td><p>HYD-GW</p></td>
<td><p>海德拉巴</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>主幹 3 DEL-PBX</p></td>
<td><p>Pbx</p></td>
<td><p>DEL-PBX</p></td>
<td><p>德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主幹 4 HYD-PBX</p></td>
<td><p>Pbx</p></td>
<td><p>HYD-PBX</p></td>
<td><p>海德拉巴</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>定義語音原則

您必須定義 Enterprise Voice 部署的語音原則。 定義語音原則，以對使用者的子集強制實施位置基礎路由限制（如果只需要使用位置基礎路由的一部分）。 在此範例中，下表說明此案例中使用的語音原則。 表格中只會包含針對位置基礎路由特有的設定，以供說明之用。

如需詳細資訊，請參閱設定 [語音原則和 PSTN 使用方式記錄，以在 Lync Server 2013 中授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。


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
<td><p>PSTN 使用方式</p></td>
<td><p>新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</p></td>
<td><p>Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>錯</p></td>
<td><p>錯</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>定義語音路由

您必須定義 Enterprise Voice 部署的語音路由。 在此範例中，下表說明此案例中使用的語音路由。 表格中只會包含針對位置基礎路由特有的設定，以供說明之用。

如需詳細資訊，請參閱 [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。


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
<td><p>姓名</p></td>
<td><p>新德里路由</p></td>
<td><p>Hyderabad 路由</p></td>
<td><p>PBX Del 路由</p></td>
<td><p>PBX Hyd route</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用方式</p></td>
<td><p>新德里使用</p></td>
<td><p>Hyderabad 使用方式</p></td>
<td><p>PBX Del 使用方式</p></td>
<td><p>PBX Hyd 使用方式</p></td>
</tr>
<tr class="odd">
<td><p>樹幹</p></td>
<td><p>主幹 1 DEL-GW</p></td>
<td><p>主幹 2 HYD-GW</p></td>
<td><p>主幹 3 DEL-PBX</p></td>
<td><p>主幹 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>為使用者啟用企業語音

為使用者啟用企業語音，並將您先前定義的語音原則指派給他們。 在此範例中，下表說明此案例中使用的工作分派。 表格中只會包含針對位置基礎路由特有的設定，以供說明之用。

如需詳細資訊，請參閱 [Enable users For Enterprise Voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。


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
<td><p>關聯的語音原則</p></td>
<td><p>新德里語音原則</p></td>
<td><p>Hyderabad 語音原則</p></td>
</tr>
<tr class="even">
<td><p>範例使用者</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-3</p></td>
<td><p>HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定位置基礎路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

