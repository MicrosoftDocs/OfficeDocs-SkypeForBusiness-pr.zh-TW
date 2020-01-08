---
title: Lync Server 2013：對等 IM 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013 中的對等 IM 報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

對等 IM 報告提供對等立即訊息（IM）會話的趨勢資訊，依池和驗證類型細分。 報告可以顯示在指定時段內所保留的會話總數（例如，按天或按小時計算），也可以顯示在該期間內傳送的立即訊息總數。

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>存取對等 IM 報告

您只能[在 Lync Server 2013 開啟對等 [活動摘要] 報告](lync-server-2013-peer-to-peer-activity-summary-report.md)，然後按一下下列其中一個度量，以存取對等 IM 報告：

  - 對等 IM 會話總數

  - 對等 IM 訊息總計

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>充分運用對等 IM 報告

根據預設，對等 IM 報表會顯示每小時郵件數（或一天，視您的設定而定）。 不過，您也可以選擇透過每小時的會話來查看一天。 若要這樣做，請按一下 [報表] 視窗右上角的 [**隱藏/顯示參數**]，然後按一下 [**報表依據**] 清單中的 [**會話計數**]。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。 下表列出可與對等 IM 報表搭配使用的篩選。

### <a name="peer-to-peer-im-report-filters"></a>對等 IM 報表篩選

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
<td><p>時間範圍的開始日期和時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，請輸入一周或一月內任何位置的日期（您不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期和時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列其中一項：</p>
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
<td><p>指出要在報表中使用的值。 選取下列其中一項：</p>
<ul>
<li><p>會話計數</p></li>
<li><p>郵件計數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>依池進行對等 IM 會話的度量單位

下表列出對等 IM 報表中提供的資訊。

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>依池進行對等 IM 會話的度量單位

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
<td><p>註冊機構池或邊緣伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>會話發生的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>依驗證類型的對等 IM 會話的度量單位

下表列出點對點工作階段中參與者所使用的每一種驗證類型的對等 IM 報告所提供的資訊。

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>依驗證類型的對等 IM 會話的度量單位

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
<td><p><strong>驗證類型</strong></p></td>
<td><p>否</p></td>
<td><p>會話參與者所使用的驗證類型。 值通常是下列其中一項：</p>
<ul>
<li><p>級</p></li>
<li><p>建立</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>會話發生的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

