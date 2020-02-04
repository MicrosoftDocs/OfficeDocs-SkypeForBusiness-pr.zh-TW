---
title: Lync Server 2013：針對您的會議、應用程式和中繼伺服器配置埠範圍
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
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>在 Lync Server 2013 中針對您的會議、應用程式和中繼伺服器設定埠範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-30_

為了實現服務品質，您應該在會議、應用程式和中繼伺服器上設定相同的埠範圍，以進行音訊、影片和應用程式共用;此外，這些埠範圍不一定會以任何方式重迭。 若要使用簡單的範例，假設您在會議服務器上使用埠10000到10999進行影片。 這表示您也必須在您的應用程式和轉送伺服器上為影片保留埠10000到10999。 否則，QoS 將無法如期運作。

同樣地，假設您將埠10000到10999，以進行影片，但接著將埠10500到11999以進行音訊。 這可能會造成服務品質的問題，因為埠範圍會重迭。 有了 QoS，每個模態都必須有一組獨特的埠：如果您使用埠10000到10999進行影片，則必須使用不同的範圍（例如，從11000到11999的音訊）。

根據預設，音訊及視訊連接埠範圍不會在 Microsoft Lync Server 2013 中重迭;不過，指派給應用程式共用的埠範圍會與音訊與視訊連接埠範圍重迭。 （進而表示這些範圍都不是唯一的）。您可以在 Lync Server 2013 管理命令介面中執行下列三個命令，以驗證您的會議、應用程式和轉送作業伺服器的現有埠範圍：

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> 您可以在前面的命令中看到，每個埠類型（音訊、影片和應用程式共用）都指派了兩個個別的屬性值：埠開始和埠數。 埠開始指示該模態使用的第一個埠;例如，如果音訊埠開始等於50000，表示音訊流量使用的第一個埠是埠50000。 如果音訊埠數是2（這是不正確值，但在這裡是用來做為說明），則表示只會為音訊分配兩個埠。 如果第一個埠是埠50000，而且總共有兩個埠，則表示第二個埠必須是埠50001（埠範圍必須是連續的）。 因此，音訊的埠範圍是埠50000到50001（含）。<BR>請注意，應用程式伺服器和中繼伺服器只支援音訊的 QoS;您不需要變更應用程式伺服器或轉送伺服器中的影片或應用程式共用埠。



</div>

如果您執行前面三個命令，您會看到 Lync Server 2013 的預設埠值已設定為如下所示：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Property</th>
<th>會議服務器</th>
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


如前所述，為 QoS 設定 Lync Server 埠時，您應該確保：1）音訊埠設定在您的所有會議、應用程式和轉送伺服器上都相同;和，2）埠範圍不會重迭。 如果您仔細觀察前面的表格，您會看到埠範圍在三種伺服器類型上都是相同的。 例如，在每個伺服器類型上，啟動音訊埠都設定為 port 49152，而且在每個伺服器上為音訊所保留的埠總數也相同：8348。 不過，埠的範圍會重迭：音訊埠是從埠49152開始，但會將埠設定為應用程式共用。 為了讓您能夠最佳地使用服務品質，應該將應用程式共用重新配置為使用唯一的埠範圍。 例如，您可以將應用程式共用設定為從埠40803開始，並使用8348埠。 （為什麼要8348埠？ 如果將這些值加在一起，即 40803 + 8348，即表示應用程式共用將使用埠40803穿過埠49150。 因為音訊埠無法在埠49152開始，因此您將不會再有任何重迭的埠範圍。

在您為應用程式共用選取新的埠範圍之後，您可以使用 CsConferencingServer Cmdlet 進行變更。 您不需要在應用程式伺服器或您的中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。 如果您決定要重新指派音訊流量所用的埠，您只需在這些伺服器上變更埠值。

若要在單一會議服務器上修改應用程式共用的埠值，請在 Lync Server 管理命令介面中執行如下所示的命令：

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

如果您想要在所有的會議服務器上進行這些變更，您可以改為執行此命令：

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

在變更埠設定之後，您應該停止並重新啟動每個變更所影響的服務。

您的會議服務器、應用程式伺服器及中繼伺服器共用完全相同的埠範圍，並不是強制性的。唯一的真正需求是您在所有伺服器上都留出唯一的埠範圍。 不過，如果您在所有伺服器上都使用相同的埠組，系統管理通常會更容易。

</div>

<span> </span>

</div>

</div>

</div>

