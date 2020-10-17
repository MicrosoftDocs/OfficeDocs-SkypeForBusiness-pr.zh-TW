---
title: Lync Server 2013： Peer-to-Peer 活動摘要報告
description: Lync Server 2013： Peer-to-Peer 活動摘要報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557299"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 Peer-to-Peer 活動摘要報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

Peer-to-Peer 活動摘要報告可提供對等通訊會話的整體觀點。 點對點工作階段通常只會包含兩位使用者，不需要使用 Lync Server 會議服務。 相比之下，會議通常包含兩個以上的使用者，且需要使用 Microsoft Lync Server 2013 會議服務。 會議活動會在會議摘要報告上報告。

Peer-to-Peer 活動摘要報告可協助您回答如下問題：

  - 我的使用者在一般的一天會傳送多少對等立即訊息？

  - 是否有任何使用者真的利用 Lync Server 應用程式共用和檔案傳輸功能？

  - 使用者抱怨，網路在一天中的特定時間似乎很慢。 對等音訊和影片在這些時段內專門占多少分鐘？

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>存取 Peer-to-Peer 活動摘要報告

您可以從監控報告的首頁存取 Peer-to-Peer 活動摘要報告。 您可以按一下下列其中一個計量， [以在 Lync Server 2013 中開啟 PEER-TO-PEER IM 報告](lync-server-2013-peer-to-peer-im-report.md) ：

  - 對等 IM 工作階段總數

  - 對等 IM 訊息總數

同樣的，您也可以按一下下列其中一項度量，開啟 Peer-to-Peer 的語音和影片報告：

  - 對等音訊會話總數

  - 對等音訊會話分鐘總數

  - 對等音訊會話總數

  - 對等音訊會話分鐘總數

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Peer-to-Peer 活動摘要報告的最佳用法

在 Peer-to-Peer 活動摘要報告的底部，您會找到計量（如對等 IM 會話總數和對等 IM 訊息總數）的總和。 這會提供報表內文中所發現詳細資訊的摘要。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。 例如，Peer-to-Peer 活動摘要報表可讓您選擇資料的分組方式。 在此情況下，活動會依小時、天、周或月進行分組。

下表列出您可以搭配 Peer-to-Peer 活動摘要報告使用的篩選器。

### <a name="peer-to-peer-activity-summary-report-filters"></a>活動摘要報表篩選 Peer-to-Peer

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。 例如，如果您選取 [開始日期 7/17/12012] 和 [結束2/28/2012 日期] 的 [每日間隔]，將會顯示 8/7/12012 12:00 AM 到 9/7/12012 12:00 AM (的資料，也就是有31天的資料) 總計。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 Peer-to-Peer 活動摘要報告中提供的資訊。

### <a name="peer-to-peer-activity-summary-report-metrics"></a>活動摘要報表度量 Peer-to-Peer

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>每小時</strong></p>
<p><strong>每日</strong></p>
<p><strong>每週</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指出在篩選工具列上所選取的時間間隔。 在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/17/12012]，就會看到該日期的使用者註冊活動的每小時細目。</p></td>
</tr>
<tr class="even">
<td><p><strong>點對點工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>進行中的點對點工作階段總數（不論會話類型為何）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等 IM 工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等立即訊息 (IM) 會話的總數。 當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等 IM 訊息總數</strong></p></td>
<td><p>否</p></td>
<td><p>在點對點工作階段中傳送的立即訊息總數。 當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等音訊會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊通話總數。 當您按一下此欄位時，報表會顯示所選時段的 Peer-to-Peer 語音及影片報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等音訊會話分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊會話所用的總時間量。 當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均對等音訊會話分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊會話所用的平均時間量。 由音訊會話總數除以音訊會話總數所計算。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等音訊會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻通話總數。 請注意，影片也會算作音訊會話：每個影片都會計算為一個影片會話和一個音訊會話。 當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等視頻會話分鐘總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻會話所用的總時間。 當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均對等視頻會話分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻會話所用的平均時間量。 透過影片總數除以影片總數來計算。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等檔案傳輸會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>包含檔案傳輸的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等應用程式共用會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>包含應用程式共用的點對點工作階段總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

