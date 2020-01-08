---
title: Lync Server 2013：會議活動報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的會議活動報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

會議活動報告可讓您輕鬆回答下列問題：每天舉行多少筆會議，以及何時舉行這些會議？ 這類資訊不僅是本身所有用的，也適用于疑難排解工具。 例如，假設使用者抱怨，在一天中間網路看起來很慢。 您可以快速流覽會議活動報告，可能會建議一種可能的原因：目前為止，有更多的會議是在 10:00 AM 和 2:00 PM 之間排程，然後在其他時間進行排程。

如果慢速網路造成問題，您可以鼓勵使用者在一天較低的 trafficked 時間期間重新排程其中一些會議。

<div>

## <a name="accessing-the-conference-activity-report"></a>存取會議活動報告

在[Lync Server 2013 的 [會議摘要] 報告中](lync-server-2013-conference-summary-report.md)，按一下下列其中一個度量，即可存取會議活動報告：

  - 會議總數

  - 參與者總數

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>充分利用會議活動報告

根據預設，會議活動報告會會顯示指定時段內的會議總數（例如，每日會議總數，或一天中每小時會議的總數）。 不過，您也可以選擇顯示該時段的參與者總數或參與者分鐘數的總數。 若要這樣做，請按一下 [顯示/隱藏參數] 按鈕以顯示篩選選項，然後從 [報告依據] 下拉式清單中選取下列其中一項：

  - 參與者計數

  - 參與者通話分鐘數

  - 會議計數

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出您可與會議活動報告搭配使用的篩選。

### <a name="conference-activity-report-filters"></a>會議活動報表篩選

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
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期/時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列任何一項：</p>
<ul>
<li><p>每小時（最多可顯示25小時）</p></li>
<li><p>每天（最多可以顯示31天）</p></li>
<li><p>每週（最多可以顯示12周）</p></li>
<li><p>每月（最多可以顯示12個月）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告依據</strong></p></td>
<td><p>指出要在報表中使用的值。 您可以選取下列其中一項：</p>
<ul>
<li><p>參與者計數</p></li>
<li><p>參與者通話分鐘數</p></li>
<li><p>會議計數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>依泳池進行的會議度量單位

下表列出每個池之會議活動報告中的資訊。

### <a name="metrics-for-conferences-by-pool"></a>依泳池進行的會議度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>否</p></td>
<td><p>在會議中使用的註冊機構池或邊緣伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>舉行會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>參與者總數、總參與者分鐘數或會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>依伺服器類型的會議標準

下表列出每個伺服器類型之會議活動報告中的資訊。

### <a name="metrics-for-conferences-by-server-type"></a>依伺服器類型的會議標準

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>會議服務器類型</strong></p></td>
<td><p>否</p></td>
<td><p>在會議中使用的伺服器類型，通常是下列其中一項：</p>
<ul>
<li><p>網路會議服務器</p></li>
<li><p>IM 會議伺服器</p></li>
<li><p>電話會議伺服器</p></li>
<li><p>防病毒會議服務器</p></li>
<li><p>應用程式共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>舉行會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>參與者總數、總參與者分鐘數或會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

