---
title: Lync Server 2013：呼叫診斷摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>在 Lync Server 2013 中呼叫診斷摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

[通話診斷摘要] 報告可全面瞭解對等與會議會話失敗的情況。 報告會顯示這兩種類型的會話的整體失敗率，然後依會話模態類型進一步打破失敗資訊：

  - 立即訊息

  - 應用程式共用

  - 檔案傳輸

  - 音訊

  - 顯示器

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>存取呼叫診斷摘要報告

[呼叫診斷摘要] 報告可從 [監控報告] 首頁存取。 在 [呼叫診斷摘要] 報告中，您可以在 [Lync Server 2013] 中按一下 [對等] 的 [點對點工作階段摘要] 區段下的 [失敗率] 度量，以存取該報告的[對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)。 您也可以按一下下列任何一種會議度量，[在 Lync Server 2013 中存取會議診斷報告](lync-server-2013-conference-diagnostic-report.md)：

  - 總體會話失敗率

  - 焦點失敗率

  - MCU 失敗率

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>充分利用 [呼叫診斷摘要] 報告

[通話診斷摘要] 報告包含的圖形會針對 Microsoft Lync Server 2013 中使用的各種形式，比較失敗率。 這些圖形中的欄實際上是 hotlinks;例如，如果您按一下點對點工作階段的 [立即訊息] 資料行，您會[在 Lync Server 2013 中](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)向下切入對等活動診斷報告的實例，此報告提供有關 [呼叫說明摘要] 報告中所包含的所有立即訊息會話的其他詳細資料。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[呼叫診斷摘要] 報告可讓您篩選出會話中使用的註冊機構池或邊緣伺服器等專案。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、日、周或月進行分組。

下表列出可與 [呼叫診斷摘要] 報告搭配使用的篩選準則。

### <a name="call-diagnostic-summary-report-filters"></a>呼叫診斷摘要報告篩選器

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
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

下表列出點對點工作階段的呼叫診斷摘要報告中所提供的資訊（也就是只涉及兩個參與者的會話）。

### <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

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
<td><p><strong>總會話數</strong></p></td>
<td><p>否</p></td>
<td><p>所執行的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的點對點工作階段百分比。 當您按一下此專案時，報告會顯示對等活動診斷報告，其中會顯示關於失敗的點對點工作階段的詳細資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

下表列出會議會話的通話診斷報告中所提供的資訊（也就是有三個或更多參與者的會議）。

### <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

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
<td><p><strong>會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>召開的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>已執行的會議會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總體會話失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗之會議會話總數的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦點會話</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的焦點會議會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦點失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的專注于會議會話所占的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 會話</strong></p></td>
<td><p>否</p></td>
<td><p>已失敗的會議服務器（先前稱為 Multipoint 控制項單元或 MCU）會議的總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>已失敗的會議服務器（先前稱為 Multipoint 控制項單元或 MCU）會議所占的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

