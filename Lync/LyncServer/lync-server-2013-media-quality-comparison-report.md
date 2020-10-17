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
ms.openlocfilehash: 05b157be6cc94f0b01dbefadfd89041118b944e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500660"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體質量比較報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

媒體質量比較報告可讓您比較不同音訊通話類型的通話品質值 (例如，透過無線網路撥打的通話，以及透過有線連線進行的通話) 。

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>存取媒體質量比較報告

媒體質量比較報告可從監控報告的首頁進行存取。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以搭配媒體質量比較報告使用的篩選器。

### <a name="media-quality-comparison-report-filters"></a>媒體質量比較報表篩選

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
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>調用</strong></p></td>
<td><p>要用來做為主要比較專案的呼叫類型。 允許的值為：</p>
<ul>
<li><p>一切</p></li>
<li><p>外部</p></li>
<li><p>內部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
<li><p>外部和有線</p></li>
<li><p>外部和無線</p></li>
<li><p>外部和 VPN</p></li>
<li><p>外部和非 VPN</p></li>
<li><p>內部和有線</p></li>
<li><p>內部和無線</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>與通話比較</strong></p></td>
<td><p>要用來做為次要比較專案的呼叫類型。 允許的值為：</p>
<ul>
<li><p>一切</p></li>
<li><p>外部</p></li>
<li><p>內部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
<li><p>外部和有線</p></li>
<li><p>外部和無線</p></li>
<li><p>外部和 VPN</p></li>
<li><p>外部和非 VPN</p></li>
<li><p>內部和有線</p></li>
<li><p>內部和無線</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出媒體質量比較報告中提供的資訊。

### <a name="media-quality-comparison-report-metrics"></a>媒體質量比較報告度量

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
<td><p><strong>通話數量</strong></p></td>
<td><p>否</p></td>
<td><p>通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>MOS) 降級 (</strong></p></td>
<td><p>否</p></td>
<td><p>平均 MOS 金額 (平均平均觀點) 通話期間的效能。 降級值的範圍從低0.0 到高 5.0;值0.5 或更少代表可接受的降級。 從過去開始，平均觀點是透過讓使用者以1到5的比例來評分呼叫的品質來計算。 Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</p>
<p>嚴重降級值可能是由於擁塞所造成;缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。 高降級導致音訊失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的呼叫總數。 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>來回行程 (毫秒) </strong></p></td>
<td><p>否</p></td>
<td><p>Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。 在200毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>否</p></td>
<td><p> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動 (毫秒) </strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>否</p></td>
<td><p>隱藏音訊樣本的平均比率與樣本總數總數。  (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復延伸比率</strong></p></td>
<td><p>否</p></td>
<td><p>延伸音訊樣本的平均比例與樣本總數總數。  (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復壓縮比例</strong></p></td>
<td><p>否</p></td>
<td><p>壓縮音訊樣本的平均比率與樣本總數。  (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

