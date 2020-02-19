---
title: 'Lync Server 2013: QoE 檢視詳細資料'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a>Lync Server 2013 中的 QoE 檢視詳細資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。 此為建議的檢視，可用來建立自訂報告，而非直接存取資料庫資料表；那是因為檢視較可能維持與日後版本的回溯相容性。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>檢視名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 AudioStreamDetail 檢視</a></p></td>
<td><p>儲存資料庫中每個音訊資料流的資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 檢視</a></p></td>
<td><p>儲存資料庫中每個媒體行的資訊。 一個音訊工作階段通常包含一個音訊媒體行。 一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 檢視</a></p></td>
<td><p>儲存網路設定的資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Lync Server 2013 中的工作階段檢視</a></p></td>
<td><p>儲存在資料庫中擁有記錄之工作階段的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 檢視</a></p></td>
<td><p>儲存使用者代理程式的資訊，這些使用者代理程式與在資料庫中擁有記錄的工作階段相關。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 檢視</a></p></td>
<td><p>儲存在資料庫中每個視訊資料流的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

