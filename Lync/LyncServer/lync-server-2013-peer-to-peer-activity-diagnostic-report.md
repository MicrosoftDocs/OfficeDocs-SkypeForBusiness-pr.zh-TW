---
title: Lync Server 2013：對等活動診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc98f1c81f79605da2de2b06397d8a23d8086861
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的對等活動診斷報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

對等活動診斷報告可提供對等通訊會話成功與失敗的資訊。 請注意，Microsoft Lync Server 2013 會區分不同類型的失敗：

  - **預期失敗**。 預期的失敗通常是最有技術意義的失敗。 例如，假設您撥打電話給某人，但他/她不在辦公室，而且無法接聽電話。 因為通話沒有回應，所以從技術角度來看，該通話是失敗的。 另一方面，這是預期的失敗：如果您不能接聽電話，Microsoft Lync Server 2013 不會預期您接聽電話。 同樣地，如果您嘗試將即時消息傳送給離線的使用者，或只登入不支援立即訊息的電話，就會發生預期的失敗。

  - 未**預期的失敗**。 不正確的錯誤就是名稱所暗示的錯誤：根據情況而定的錯誤，您不會發生這種情況。 例如，假設您撥打電話給某人，而該人員可接聽來電;不過，當 Lync Server 2013 嘗試將來電傳送到語音信箱時，通話失敗的原因是連線到 Exchange 整合通訊已遺失。 這是一個意外的錯誤：您預計通話永遠會傳送給語音信箱。 一般來說，非預期的失敗就是真正的失敗：它們是可能無法透過使用者教育或類似的措施修正的問題。

請注意，成功、預期的失敗及意外的失敗指標可能不會新增到 [總會話] 度量。 例如，在前面的圖例中，我們有下列值：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>成功</th>
<th>預期失敗</th>
<th>意外的失敗</th>
<th>總會話數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>位</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


如果您新增 2024 + 469 + 16，您總共會得到2509個會話，而 [總會話] 資料行則會顯示2521會話總數。 "遺失" 的12個會話是系統無法分類成成功或失敗的會話。 當協力廠商產品引入 Lync Server 不熟悉的新診斷程式代碼時，有時候會發生這種情況。 當發生這種情況時，使用該產品進行的通話，並報告該診斷程式代碼，不一定會成為成功、預期的失敗或意外的失敗。

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>存取對等活動診斷報告

從 [監控報告] 首頁存取對等診斷報告。 您可以按一下下列其中一個度量，[以存取 Lync Server 2013 中的失敗發佈報告](lync-server-2013-failure-distribution-report.md)：

  - 意外的失敗量

  - 預期失敗的音量

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>充分運用對等活動診斷報告

有幾種方式可以篩選對等的活動診斷報告，但根據預設，這些篩選選項會在視圖中隱藏。 若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [顯示/隱藏參數] 按鈕。 一旦您這麼做，就可以使用篩選選項。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，對等活動診斷報告可讓您篩選諸如會話形式（例如立即訊息、檔案傳輸或應用程式共用）等內容。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、日、周或月進行分組。

下表列出您可以搭配對等活動診斷報告使用的篩選。

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>對等活動診斷報表篩選

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
<td><p><strong>模態</strong></p></td>
<td><p>指出發生的溝通活動類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>立即訊息</p></li>
<li><p>檔案傳輸</p></li>
<li><p>應用程式共用</p></li>
<li><p>音訊</p></li>
<li><p>顯示器</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>度量單位（依模態）

下表列出針對每個模態的對等活動診斷報告中所提供的資訊。

### <a name="metrics-per-modality"></a>度量單位（依模態）

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
<td><p><strong>成功的音量</strong></p></td>
<td><p>否</p></td>
<td><p>成功的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>成功百分比</strong></p></td>
<td><p>否</p></td>
<td><p>已完成且重要問題的點對點工作階段百分比。 將成功率除以總會話數來計算。</p></td>
</tr>
<tr class="odd">
<td><p><strong>預期失敗的音量</strong></p></td>
<td><p>否</p></td>
<td><p>&quot;預期失敗&quot;發生的會話總數。</p>
<p>預期的失敗是預期發生的失敗。 例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>預期失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>遇到預期錯誤的點對點工作階段百分比。 將預期的失敗量除以總會話數來計算。</p></td>
</tr>
<tr class="odd">
<td><p><strong>意外的失敗量</strong></p></td>
<td><p>否</p></td>
<td><p>發生&quot;意外失敗&quot;的會話總數。</p>
<p>發生意外的失敗，就是看起來像是其他健康的系統。 例如，如果來電者停留在 [保留] 上，就不應該終止通話。 如果發生這種情況，就會將它標記為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>意外的失敗百分比</strong></p></td>
<td><p>否</p></td>
<td><p>遇到意外錯誤的點對點工作階段百分比。 將非預期的失敗量除以總會話數來計算。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總會話數</strong></p></td>
<td><p>否</p></td>
<td><p>會話總數，包括成功的會話、失敗的會話（預期的失敗與意外的失敗），以及未分類的會話。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

