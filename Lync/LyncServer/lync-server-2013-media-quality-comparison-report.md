---
title: Lync Server 2013：媒體質量比較報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體質量比較報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

媒體質量比較報告可讓您比較不同類型音訊通話的通話品質值（例如，透過無線網路撥打，以及透過有線連線進行通話）。

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>存取媒體質量比較報告

您可從 [監控報告] 首頁存取媒體質量比較報告。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出您可搭配媒體質量比較報告使用的篩選。

### <a name="media-quality-comparison-report-filters"></a>媒體質量比較報表篩選

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
<td><p><strong>撥</strong></p></td>
<td><p>要用來做為主要比較專案的呼叫類型。 允許的值為：</p>
<ul>
<li><p>同時</p></li>
<li><p>外來</p></li>
<li><p>內部</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
<li><p>外部和有線</p></li>
<li><p>外部和無線</p></li>
<li><p>外部與 VPN</p></li>
<li><p>外部與非 VPN</p></li>
<li><p>內部和有線</p></li>
<li><p>內部和無線</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>與通話比較</strong></p></td>
<td><p>要用來做為次要比較專案的呼叫類型。 允許的值為：</p>
<ul>
<li><p>同時</p></li>
<li><p>外來</p></li>
<li><p>內部</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
<li><p>外部和有線</p></li>
<li><p>外部和無線</p></li>
<li><p>外部與 VPN</p></li>
<li><p>外部與非 VPN</p></li>
<li><p>內部和有線</p></li>
<li><p>內部和無線</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列其中一項：</p>
<ul>
<li><p>每小時（最多可顯示25小時）</p></li>
<li><p>每天（最多可以顯示31天）</p></li>
<li><p>每週（最多可以顯示12周）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出媒體質量比較報告中提供的資訊。

### <a name="media-quality-comparison-report-metrics"></a>媒體質量比較報告度量單位

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
<td><p><strong>通話量</strong></p></td>
<td><p>否</p></td>
<td><p>通話總次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>下降（MOS）</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間的平均 MOS （平均意見分數）會下降。 降級值的範圍可從低0.0 到 5.0;0.5 或較低的值代表可接受的下降。 在過去，平均值觀點的計算方式是讓使用者以1到5的比例來評分通話品質。 Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</p>
<p>擁塞可能會造成高降級值。缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。 高品質的結果會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的呼叫總數。 較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返行程（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。 200毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>資料包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 隱藏比例</strong></p></td>
<td><p>否</p></td>
<td><p>隱藏的音訊樣本與總樣本數的平均比率。 （隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 延伸比率</strong></p></td>
<td><p>否</p></td>
<td><p>延伸音訊樣本的平均比例與總樣本數的總和。 （已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 壓縮比率</strong></p></td>
<td><p>否</p></td>
<td><p>壓縮之音訊樣本的平均比率為樣本總數。 （壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

