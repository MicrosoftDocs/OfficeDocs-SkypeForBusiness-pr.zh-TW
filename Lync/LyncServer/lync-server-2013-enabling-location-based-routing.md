---
title: Lync Server 2013：啟用以位置為基礎的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 啟用以位置為基礎的路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-26_

部署企業語音並定義網路區域、網站和子網之後，您就可以啟用以位置為基礎的路由。 必須針對下列 Enterprise Voice 元素啟用位置路由：

  - 網路網站

  - 幹線設定

  - 語音原則

  - 路由設定

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>啟用從位置路由至網路網站

部署企業語音及設定網路網站之後，您就可以開始設定以位置為基礎的路由。 首先，您要建立語音路由策略，以將網路網站與適當的 PSTN 用途進行關聯。 將 PSTN 用途指派給語音路由策略時，請務必只使用與您在其位置使用 PSTN 閘道的語音路由所關聯的 PSTN 使用，或者是位於不需要以位置為基礎的路由限制的區域中的 PSTN 閘道。使用 Lync Server Windows PowerShell 命令、新 CsVoiceRoutingPolicy 或 Lync Server [控制台] 來建立語音路由策略。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

如需詳細資訊，請參閱[新 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。

在這個範例中，下清單格和 Windows PowerShell 命令說明在這個案例中定義的兩個語音路由策略及其關聯 PSTN 用法。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

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
<th>語音路由策略2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>語音原則識別碼</p></td>
<td><p>新德里語音路由原則</p></td>
<td><p>Hyderabad 語音路由策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用量、PBX Del 用法、PBX Hyd 使用量</p></td>
<td><p>Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</p></td>
</tr>
</tbody>
</table>

  

接下來，針對適用的網路網站設定以位置為基礎的路由，並將您的語音路由策略與它們建立關聯。 使用 Lync Server Windows PowerShell 命令（CsNetworkSite）啟用以位置為基礎的路由，並將語音路由策略與您必須強制執行路由限制的網路網站產生關聯。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

在這個範例中，下表說明在這個案例中使用 Lync Server Windows PowerShell 定義的兩個不同網路網站、新德里及 Hyderabad 的位置路由。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

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
<th>Site 1 （新德里）</th>
<th>Site 2 （Hyderabad）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>網站名稱</p></td>
<td><p>Site 1 （新德里）</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>滿足</p></td>
<td><p>滿足</p></td>
</tr>
<tr class="odd">
<td><p>語音路由策略</p></td>
<td><p>新德里語音路由原則</p></td>
<td><p>Hyderabad 語音路由策略</p></td>
</tr>
<tr class="even">
<td><p>網</p></td>
<td><p>Subnet 1 （新德里）</p></td>
<td><p>Subnet 2 （Hyderabad）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>啟用以位置為基礎的路由至 Trunks

在針對位置路由啟用中繼設定之前，您必須為每個幹線或每個網路網站建立幹線設定。 使用 Lync Server Windows PowerShell 命令（New-cstrunkconfiguration）建立幹線設定。 如果有多個 trunks 與指定的系統（亦即閘道或 PBX）相關聯，則必須修改每個中繼設定，才能啟用以位置為基礎的路由限制。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

如需詳細資訊，請參閱[新 new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在這個範例中，下列 Windows PowerShell 命令說明如何針對此案例中定義的部署中的每個主幹建立一個幹線設定。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

針對每個幹線設定中繼設定之後，您就可以使用 Lync Server Windows PowerShell 命令（New-cstrunkconfiguration），以啟用要強制執行路由限制的 trunks 的位置路由。 啟用以位置為基礎的路由，以便將呼叫路由到 pstn 閘道，並將呼叫路由至 PSTN，並建立閘道所在網路網站的關聯。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

如需詳細資訊，請參閱[新 new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在這個範例中，對於與新德里及 Hyderabad 中 PSTN 閘道相關聯的每個幹線，都會啟用以位置為基礎的路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

請勿針對不將呼叫路由至 PSTN 的 trunks 啟用位置式路由;不過，您仍然必須將主幹與系統所處的網路網站進行關聯，以以位置為基礎的路由限制需要針對透過這種幹線連接端點的 PSTN 呼叫強制執行。 在這個範例中，對於與新德里與 Hyderabad 中的 PBX 系統相關聯的每個幹線，都不會啟用位置路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
連接至不將呼叫路由至 PSTN （亦即 PBX）之系統的端點，將會有類似的限制，也就是啟用位置式路由的使用者 Lync 端點。 這表示無論使用者的位置為何，這些使用者都能在 Lync 使用者上撥打和接聽來電。 他們也可以在不將呼叫路由至 PSTN 網路的其他系統（亦即連接至不同 PBX 的端點）上，將接收呼叫與其他系統進行撥打，而不論與系統關聯的網路網站為何。 所有的撥入通話、撥出通話、來電轉接及涉及 PSTN 端點的來電轉接，都會受到位置式路由 enforcements。 此類通話只能使用定義為此類系統的本機的 PSTN 閘道。

下表說明兩個不同網路網站中四個 trunks 的主幹設定：兩個已連接至 PSTN 閘道，以及兩個連線至 PBX 系統的兩個。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway：幹線 1 DEL-GW</p></td>
<td><p>滿足</p></td>
<td><p>Site 1 （新德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：主幹 2 HYD-GW</p></td>
<td><p>滿足</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway：幹線 3 DEL-PBX</p></td>
<td><p>虛假</p></td>
<td><p>Site 1 （新德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：幹線 4 HYD-PBX</p></td>
<td><p>虛假</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>啟用以位置為基礎的路由到語音原則

若要強制將位置路由傳送給特定的使用者，請將這些使用者的語音原則設定為避免 PSTN 免付費旁路。 使用 Lync Server Windows PowerShell 命令（CsVoicePolicy）建立新的語音原則，或設定 CsVoicePolicy （如果使用現有的原則），以透過避免 PSTN 免付費旁路來啟用以位置為基礎的路由。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

如需詳細資訊，請參閱[新 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。

在這個範例中，下清單格和 Windows PowerShell 命令說明如何防止在此案例中定義的 Hyderabad 語音原則中避開 PSTN 免付費旁路。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

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
<td><p>PSTN 用法</p></td>
<td><p>新德里使用量、PBX Del 用法、PBX Hyd 使用量</p></td>
<td><p>Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>滿足</p></td>
<td><p>滿足</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>在路由設定中啟用以位置為基礎的路由

最後，全域啟用路由設定的位置路由。 使用 Lync Server Windows PowerShell 命令（CsRoutingConfiguration）來啟用以位置為基礎的路由。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

如需詳細資訊，請參閱[設定 CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。

<div>


> [!NOTE]  
> 雖然必須透過全域設定啟用位置路由，否則將只會針對此檔中已設定其配置的網站、使用者和 trunks，強制執行要套用的一組規則。



</div>

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

