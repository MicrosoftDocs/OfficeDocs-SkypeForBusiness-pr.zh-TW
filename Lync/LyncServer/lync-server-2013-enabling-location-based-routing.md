---
title: Lync Server 2013：啟用 Location-Based 路由
description: Lync Server 2013：啟用 Location-Based 路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557619"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Location-Based 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-26_

部署 Enterprise Voice 並定義網路地區、網站和子網之後，您可以啟用 Location-Based 路由。 必須為下列 Enterprise Voice 元素啟用 Location-Based 路由：

  - 網路網站

  - 主幹設定

  - 語音原則

  - 路由設定

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>啟用 Location-Based 路由傳送至網路網站

部署企業語音及設定網路網站之後，即可設定 Location-Based 路由。 首先，您會建立一個語音路由原則，以將網路網站與適當的 PSTN 使用方式產生關聯。 將 PSTN 使用方式指派給語音路由原則時，請務必使用與使用 PSTN 閘道（位於不需要 Location-Based 路由限制）之區域之語音路由相關聯的 PSTN 使用方式。使用 [Lync Server Windows PowerShell] 命令、New-CsVoiceRoutingPolicy 或 Lync Server 控制台建立語音路由原則。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

如需詳細資訊，請參閱 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。

在此範例中，下清單格和 Windows PowerShell 命令會說明兩個語音路由策略及其在此案例中定義的關聯 PSTN 使用方式。 只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>語音路由原則1</th>
<th>語音路由原則2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>語音原則識別碼</p></td>
<td><p>新德里語音路由原則</p></td>
<td><p>Hyderabad 語音路由原則</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用方式</p></td>
<td><p>新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</p></td>
<td><p>Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</p></td>
</tr>
</tbody>
</table>

  

接下來，針對適用的網站設定 Location-Based 路由，並將您的語音路由策略關聯。 使用 Lync Server Windows PowerShell 命令 New-CsNetworkSite，啟用 Location-Based 路由，並將語音路由原則關聯至必須強制執行路由限制的網路網站。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

在此範例中，下表說明使用 Lync Server Windows PowerShell 在此案例中定義的兩個不同網路網站（新德里和 Hyderabad 的 Location-Based 路由）。 只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>網站名稱 </p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>語音路由原則</p></td>
<td><p>新德里語音路由原則</p></td>
<td><p>Hyderabad 語音路由原則</p></td>
</tr>
<tr class="even">
<td><p>子網路</p></td>
<td><p>Subnet 1 (新德里) </p></td>
<td><p>Subnet 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>啟用 Location-Based 路由傳送至主幹

您必須為每個主幹或每個網路網站建立主幹設定，才能啟用 Location-Based 路由的主幹設定。 使用 Lync Server Windows PowerShell 命令 Get-cstrunkconfiguration 來建立主幹設定。 如果有多個主幹與指定的系統相關聯 (例如閘道或 PBX) ，必須修改每一個主幹設定，以啟用 Location-Based 路由限制。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

如需詳細資訊，請參閱 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在此範例中，下列 Windows PowerShell 命令會說明如何為此案例中定義的部署中的每個主幹建立一個主幹設定。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

在每個主幹設定主幹設定之後，您可以使用 [Lync Server Windows PowerShell] 命令 Set-CsTrunkConfiguration，啟用 Location-Based 路由傳送至必須強制執行路由限制的主幹。 啟用 Location-Based 路由傳送至將通話路由傳送至 PSTN 閘道的主幹，並將閘道所在的網路網站關聯。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

如需詳細資訊，請參閱 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在此範例中，會為每個與 Hyderabad 中的 PSTN 閘道相關聯的主幹啟用 Location-Based 路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

請勿啟用不將通話路由傳送至 PSTN 之主幹的 Location-Based 路由;不過，您仍然必須將主幹與系統所在的網路網站產生關聯，因為在到達透過此主幹連線之端點的 PSTN 通話時，需要強制執行 Location-Based 路由限制。 在此範例中，未針對與 Hyderabad 中 PBX 系統相關聯的每個主幹啟用 Location-Based 路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
連接至不將通話路由傳送至 PSTN 的系統端點 (亦即，PBX) 會具有與啟用 Location-Based 路由之使用者的 Lync 端點類似的限制。 這表示，不論使用者的位置為何，這些使用者都可以在 Lync 使用者上撥打和接聽電話。 他們也可以在未將通話路由傳送至 PSTN 網路的其他系統上撥打和撥出來電 (亦即，不論系統關聯的網站為何，連接至不同 PBX 的端點) 都會有所不同。 所有撥出電話、撥出電話、涉及 PSTN 端點的來電轉接及來電轉接都會受到 Location-Based 路由 enforcements 的制約。 這類呼叫只能使用定義為此類系統之本機的 PSTN 閘道。

下表說明兩個不同網路網站中四個主幹的主幹設定：兩個連接至 PSTN 閘道的兩個，以及兩個連接至 PBX 系統的主幹設定。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway：主幹 1 DEL-GW</p></td>
<td><p>是</p></td>
<td><p>Site 1 (新德里) </p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：主幹 2 HYD-GW</p></td>
<td><p>是</p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway：主幹 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 1 (新德里) </p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：主幹 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>啟用 Location-Based 路由至語音原則

若要強制 Location-Based 路由傳送至特定的使用者，請設定使用者的語音原則，以防止 PSTN 免付費旁路。 使用 [Lync Server Windows PowerShell] 命令 New-CsVoicePolicy，以建立新的語音原則或 Set-CsVoicePolicy （如果使用現有的原則），以透過防止 PSTN 免語音旁路來啟用 Location-Based 路由。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

如需詳細資訊，請參閱 [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。

在此範例中，下清單格和 Windows PowerShell 命令可讓您在此案例中所定義的新德里和 Hyderabad 語音原則中預防 PSTN 長途電話旁路。 只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


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
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>啟用路由設定中的 Location-Based 路由

最後，全域啟用 Location-Based 路由傳送至您的路由設定。 使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，啟用 Location-Based 路由。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

如需詳細資訊，請參閱 [CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。

<div>


> [!NOTE]  
> 雖然 Location-Based 路由必須透過全域設定來啟用，但只會針對此檔中所指定的網站、使用者和主幹，強制執行所套用的規則集。



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定 Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

