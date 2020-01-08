---
title: Lync Server 2013：為邊緣伺服器設定埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中設定邊緣伺服器的埠範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-07-24_

有了 Edge 伺服器，您就不需要為音訊、影片和應用程式共用設定個別的埠範圍;同樣地，邊緣伺服器所用的埠範圍不一定要與您的會議、應用程式及中繼伺服器所使用的埠範圍相符。 在繼續進行我們的範例之前，請務必先將這個選項提供給您，但我們建議您不要變更埠範圍，因為如果您移出50000埠範圍，就可能會對某些案例造成負面影響。

例如，假設您已將會議、應用程式和中繼伺服器設定為使用這些埠範圍：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>資料包類型</th>
<th>起始埠</th>
<th>保留的埠數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>顯示器</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>本壘</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


如您所見，音訊、影片和應用程式共用的埠範圍是從埠40803開始，並包含總共24732個埠。 如果您想要的話，您可以將指定的邊緣伺服器設定成在 Lync Server 管理命令介面中執行如下的命令，以使用這些整體埠值：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，使用下列命令同時設定貴組織中的所有邊緣伺服器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

您可以使用此 Lync Server Management Shell 命令來驗證 Edge 伺服器的目前埠設定：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同樣地，雖然我們確實提供這些選項，但我們強烈建議您將它們留給埠配置。

</div>

<span> </span>

</div>

</div>

</div>

