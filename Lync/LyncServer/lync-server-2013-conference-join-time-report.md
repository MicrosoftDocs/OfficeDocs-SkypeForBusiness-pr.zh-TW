---
title: Lync Server 2013：會議加入時間報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Lync Server 2013 中的會議加入時間報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-23_

[會議加入時間摘要] 可讓您判斷使用者加入會議所需的時間。 報告會顯示平均的連線時間（以毫秒為單位），同時也會提供一種細目，讓您知道有多少使用者可以在2秒或更短的時間內加入會議，還有多少使用者需要2到5秒的時間加入會議等。

<div>

## <a name="accessing-the-conference-join-time-report"></a>存取會議加入時間報告

[會議加入時間] 報告可從 [監控報告] 首頁存取。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出可與會議加入時間報表搭配使用的篩選。

### <a name="conference-join-time-report-filters"></a>會議加入時間報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
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
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會議會話</strong></p></td>
<td><p>會話類型。 允許的值為：</p>
<ul>
<li><p>同時</p></li>
<li><p>焦點會話（焦點是線上會議的中心原則和狀態管理員，並協調會議的所有方面</p></li>
<li><p>應用程式共用</p></li>
<li><p>A/V 會議</p></li>
</ul>
<p>如果您選取 [全部]，會議加入時間總將會顯示在報表頂端。 請注意，這些總和只適用于使用 Microsoft Exchange 或 Microsoft Outlook 排程的會議。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出會議加入時間報表中提供的資訊。

### <a name="conference-join-time-report-metrics"></a>會議加入時間報表度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>為止</strong></p>
<p>這個指標的實際標題會根據所選的間隔而有所不同。</p></td>
<td><p>否</p></td>
<td><p>會議發生的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>總會話數</strong></p></td>
<td><p>否</p></td>
<td><p>會話總數，包括成功的會話、失敗的會話（預期的失敗與意外的失敗），以及未分類的會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Average （毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>參與者加入會議所需的平均時間（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>會話&lt; 2 秒，大量</strong></p></td>
<td><p>否</p></td>
<td><p>可在不超過2秒內加入會議的參與者人數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會話&lt; 2 秒、百分比</strong></p></td>
<td><p>否</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>會話2-5 秒、成交量</strong></p></td>
<td><p>否</p></td>
<td><p>在2秒到5秒之間加入會議所需的參與者人數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會話2-5 秒、百分比</strong></p></td>
<td><p>否</p></td>
<td><p>在2秒到5秒之間加入會議所需的呼叫參與者總數的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>會話5-10 秒、成交量</strong></p></td>
<td><p>否</p></td>
<td><p>在5秒到10秒之間加入會議所需的參與者人數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會話5-10 秒、百分比</strong></p></td>
<td><p>否</p></td>
<td><p>在5秒和10秒之間加入會議所需的呼叫參與者總數的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>會話&gt; 10 秒、成交量</strong></p></td>
<td><p>否</p></td>
<td><p>需要10秒以上的參與者加入會議的人數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會話&gt; 10 秒、百分比</strong></p></td>
<td><p>否</p></td>
<td><p>需要10秒以上的時間來加入會議的呼叫參與者總數的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

