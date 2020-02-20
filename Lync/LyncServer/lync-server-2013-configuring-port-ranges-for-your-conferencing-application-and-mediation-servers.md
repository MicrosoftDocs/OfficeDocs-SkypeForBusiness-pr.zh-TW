---
title: Lync Server 2013： 設定會議、 應用程式及中繼伺服器的連接埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb91667406fe2c4ed292f9b0b6b85e69c2e4e256
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Lync Server 2013 中設定的連接埠範圍，會議、 應用程式及中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-04-30_

為了實作服務品質 (QoS) ，您應該為在會議、應用程式和中繼伺服器上共用的音訊、視訊和應用程式共用，設定完全相同的連接埠範圍；此外，這些連接埠範圍不得以任何方式重疊。舉個簡單的例子，假設您針對會議伺服器上的視訊使用連接埠 10000 到 10999。這表示您也必須為應用程式和中繼伺服器上的視訊保留連接埠 10000 到 10999。如果沒有，服務品質 (QoS) 將無法如預期般運作。

同樣地，假設您為視訊保留連接埠 10000 到 10999，但接著為音訊保留連接埠 10500 到 11999。這樣會造成服務品質的問題，因為連接埠範圍重疊。使用服務品質 (QoS) 時，每一種模式都必須有一組唯一的連接埠：如果您對視訊使用連接埠 10000 到 10999，則必須使用不同的範圍 (例如，對音訊使用 11000 到 11999)。

根據預設，音訊和視訊的連接埠範圍中不會重疊 Microsoft Lync Server 2013;不過，連接埠範圍指派給應用程式共用與這兩個音訊和視訊的連接埠範圍重疊。 （，接著，表示沒有任何這些範圍特有）。您可以執行從 Lync Server 2013 管理命令介面中的下列三個命令，會議、 應用程式及中繼伺服器驗證的現有的連接埠範圍：

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 如同您在上述命令中所見，每一種連接埠類型 (音訊、視訊和應用程式共用) 都會被指派兩個不同的屬性值：連接埠起點和連接埠計數。連接埠起點指出用於該形式的第一個連接埠；例如，如果音訊連接埠起點等於 50000，表示用於音訊流量的第一個連接埠是連接埠 50000。如果音訊連接埠計數是 2 (這不是有效值，在這裡是作為說明之用) 表示只為音訊配置 2 個連接埠。如果第一個連接埠是連接埠 50000，且總共有兩個連接埠，表示第二個連接埠一定是連接埠 50001 (連接埠範圍必須是連續的)。因此，音訊的連接埠範圍將會是連接埠 50000 到 50001 (含)。<BR>另請注意，應用程式伺服器和中繼伺服器只支援音訊的服務品質；您不需要在應用程式伺服器或中繼伺服器中變更視訊或應用程式共用連接埠。



</div>

如果您執行上述的三個命令，您會看到 Lync Server 2013 的預設連接埠值的設定如下：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性	</th>
<th>會議伺服器</th>
<th>應用程式伺服器</th>
<th>中繼伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


如前所述，當 QoS 設定 Lync Server 連接埠，則您應該確保： 1) 音訊連接埠設定都是相同其他會議、 應用程式及中繼伺服器;和，2） 的連接埠範圍不會重疊。 如果您仔細查看上述表格中，您會看到的連接埠範圍皆相同，不同的三種伺服器類型。 例如，起始音訊連接埠設為每個伺服器類型] 上的連接埠 49152 和音訊每部伺服器中已保留連接埠總數也是相同： 8348。 不過，連接埠範圍重疊： 音訊連接埠從 49152，開始，但是這樣執行動作的連接埠設定放在一旁應用程式共用。 若要讓服務品質的最佳使用方式，應用程式共用應該會重新設定為使用唯一的連接埠範圍。 例如，您可以設定應用程式共用連接埠 40803 處開始，並使用 8348 連接埠。 (為什麼 8348 連接埠嗎？ 如果您將這些值相加-40803 + 8348-表示的應用程式共用將使用連接埠 40803 透過連接埠 49150。 因為音訊連接埠開始時沒有 49152 之前，您將不再有任何重疊的連接埠範圍。）

在為應用程式共用選取新的連接埠範圍之後，可以使用 Set-CsConferencingServer Cmdlet 進行變更。您不需要在應用程式伺服器或中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。如果您決定要重新指派用於音效流量的連接埠，只要在這些伺服器上變更連接埠值即可。

若要修改單一會議伺服器上共用的應用程式的連接埠值會執行 Lync Server 管理命令介面從如下的命令：

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

如果您要在所有的會議伺服器上進行這些變更，可以改為執行下列命令：

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

在變更連接埠設定之後，您應該要先停止，然後再重新啟動每一項受到變更影響的服務。

您的會議伺服器、應用程式伺服器和中繼伺服器並不是一定要共用完全相同的連接埠範圍；唯一必要的需求是您要在所有的伺服器上預留唯一的連接埠範圍。不過，如果您在所有伺服器上使用同一組連接埠，通常會讓管理工作更為輕鬆。

</div>

<span> </span>

</div>

</div>

</div>

