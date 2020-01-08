---
title: Lync Server 2013： ConferenceJoinTimeThresholds 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。 [會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：

  - 少於2秒。

  - 介於2秒和5秒之間。

  - 介於5秒和10秒之間。

  - 10秒以上。

ConferenceJoinTimeThresholds 資料表包含2秒、5秒和10秒的分類值。

此表格是在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>分類的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>分類的上限。 允許的值為：</p>
<ol>
<li><p>pplx-2</p></li>
<li><p>500</p></li>
<li><p>第</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

