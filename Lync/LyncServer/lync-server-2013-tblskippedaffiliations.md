---
title: Lync Server 2013：tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblSkippedAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblSkippedAffiliations 包含無法讀取的隸屬關係（通常是由於 Active Directory 網域服務存取錯誤）。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int，not null</p></td>
<td><p>Principal ID。</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>標識隸屬關係的字串。</p>
<p>格式為： guid： {0} uri： {1} &gt; id：{2}</p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int，not null</p></td>
<td><p>更新此列之主體的 ID。 因為 Active Directory 同步處理是這些專案的唯一來源，所以它永遠是1（系統使用者）。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄（s）</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

