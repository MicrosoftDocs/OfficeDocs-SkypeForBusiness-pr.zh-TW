---
title: Lync Server 2013：設定 Edge server 的埠範圍
description: Lync Server 2013：設定 Edge server 的埠範圍。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c085a5dbc32bbf56842984eae2ef8896ab895c65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548249"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Edge server 的埠範圍

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-07-24_

有了 Edge 伺服器，您不需要針對音訊、視訊與應用程式共用設定個別連接埠範圍；同樣地，用於 Edge 伺服器的連接埠範圍也無須符合與您會議伺服器、應用程式伺服器以及中繼伺服器搭配使用的連接埠範圍。 在繼續進行我們的範例之前，請務必強調此選項存在時，我們建議您不要變更埠範圍，因為當您移出50000埠範圍時，可能會對某些案例產生負面影響。

例如，假設您已設定會議、應用程式以及中繼伺服器以使用這些連接埠範圍：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>封包類型</th>
<th>起始連接埠</th>
<th>已保留連接埠數目</th>
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
<td><p>影片</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>總數</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


如您所見，音訊、影片和應用程式共用的埠範圍會從埠40803開始，並包含24732埠的總數。 您可依喜好設定某個 Edge Server，透過執行類似下列 Lync Server Management Shell 命令以使用這些全部的連接埠值：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，使用下列命令以在組織中同時設定所有 Edge 伺服器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

您可以使用下列 Lync Server 管理命令介面命令來驗證 Edge server 的目前埠設定：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同樣地，我們確實提供這些選項，我們強烈建議您保留其為埠設定的內容。

</div>

<span> </span>

</div>

</div>

</div>

