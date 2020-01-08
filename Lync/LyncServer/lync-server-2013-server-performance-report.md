---
title: Lync Server 2013：伺服器效能報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Lync Server 2013 中的伺服器效能報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

伺服器效能報告會提供 Microsoft Lync Server 2013 伺服器的清單，這些伺服器已經歷最高百分比的不佳通話。 報告會依據伺服器類型來細分伺服器，並報告個別的統計資料，以進行下列類型：

  - 中繼伺服器

  - A/V 會議伺服器

  - A/V 邊緣伺服器

  - 閘道（中繼伺服器）

  - 閘道（中繼伺服器旁路）

  - 影片（包括 A/V 會議伺服器與 A/V 邊緣伺服器的視頻指標）

  - 應用程式共用（包括 A/V 會議伺服器與 A/V 邊緣伺服器的應用程式共用指標）

請務必注意，此報告中顯示的排名是相對排名。 例如，假設您最糟糕的伺服器在其1000的撥入呼叫中有一個不佳的呼叫。 這是一個大於-可接受的百分比。1%。 不過，如果這是您所擁有的最差執行伺服器（也就是如果所有其他伺服器的通話百分比都不是0.1%），則該伺服器仍會出現在 [伺服器效能] 報告中。

<div>

## <a name="accessing-the-server-performance-report"></a>存取伺服器效能報告

伺服器效能報告是從 [監控報告] 首頁存取。 您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：

  - 通話量

  - 通話百分比太差

此外，您可以按一下以下度量，向下切入 [伺服器媒體質量趨勢] 報告：

  - 傾向

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>充分利用伺服器效能報告

伺服器效能報告提供了多種篩選資料的方式;例如，您可以篩選網路類型（從有線連線所撥打的通話，以及從無線連線撥打的通話），以及存取類型（從防火牆外的呼叫撥打到防火牆以外的通話）。 當您查看伺服器效能報告以使用這些篩選器時，這是個不錯的做法。 例如，假設您的中繼伺服器的通話百分比較差3.24%。 如果您只查看無線通話，那台伺服器可能會有接近20% 的通話百分比。 這表示伺服器難以進行無線通話，因為伺服器沒有有線通話的問題，所以這個問題遭到了一部分遮住。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，伺服器效能報告可讓您執行下列動作：依伺服器類型或網路類型（也就是有線或無線）篩選傳回的資料。 您也可以選擇分組資料的方式。 在這種情況下，資料會依小時、日、周或月進行分組。

下表列出您可與 [伺服器效能] 報告搭配使用的篩選。

### <a name="server-performance-report-filters"></a>伺服器效能報告篩選器

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
<td><p><strong>伺服器類型</strong></p></td>
<td><p>指示應報告其效能的伺服器類型。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>中繼伺服器</p></li>
<li><p>A/V 會議伺服器</p></li>
<li><p>A/V 邊緣伺服器</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>前 N 個</strong></p></td>
<td><p>指出每個類別中要顯示的伺服器數量（根據其不佳的通話百分比）。 例如，如果您選取 [ <strong>5</strong> ]，則會顯示五個 poorest 執行中的伺服器。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>500</p></li>
<li><p>第</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>Access 類型</strong></p></td>
<td><p>指出撥打電話時，用戶端是否已登入內部網路或外部網路。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>內部</p></li>
<li><p>外來</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出撥打電話時，用戶端連線到的網路類型。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>點對點</strong></p></td>
<td><p>指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 [伺服器效能] 報告中提供的資訊。

### <a name="server-performance-report-metrics-audio-call-summary"></a>伺服器效能報告度量值：語音通話摘要

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>伺服器</strong></p></td>
<td><p>否</p></td>
<td><p>伺服器的名稱/IP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話量</strong></p></td>
<td><p>否</p></td>
<td><p>撥打的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的通話總數。 較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返行程（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。 100毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>下降（MOS）</strong></p></td>
<td><p>是</p></td>
<td><p>通話期間平均觀念得分（MOS）的平均數量下降。 降級值的範圍可從低0.0 到5.0。 0.5 或較低的值代表可接受的下降。 過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。 在 Lync Server 中，監視伺服器會使用一組演算法來預測使用者對通話進行評分的方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。 高品質的結果會造成失真或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>資料包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 隱藏比例</strong></p></td>
<td><p>是</p></td>
<td><p>隱藏的音訊樣本與總樣本數的平均比率。 （隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 延伸比率</strong></p></td>
<td><p>是</p></td>
<td><p>延伸音訊樣本的平均比例與總樣本數的總和。 （已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 壓縮比率</strong></p></td>
<td><p>是</p></td>
<td><p>壓縮之音訊樣本的平均比率為樣本總數。 （壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>伺服器效能報告度量值：影片通話摘要

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
<td><p><strong>呼叫類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。 通話類型包括：</p>
<ul>
<li><p>UC 對等通話</p></li>
<li><p>UC 會議會話</p></li>
<li><p>PSTN 會議會話</p></li>
<li><p>PSTN 電話：媒體旁路</p></li>
<li><p>PSTN 通話（非旁路）： UC 腿</p></li>
<li><p>PSTN 通話（非旁路）：閘道腿</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話量</strong></p></td>
<td><p>否</p></td>
<td><p>每個通話類型的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的通話總數。 較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話音量（無線通話）</strong></p></td>
<td><p>否</p></td>
<td><p>已使用無線連線的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話量（VPN 通話）</strong></p></td>
<td><p>否</p></td>
<td><p>已使用 VPN 連線的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話音量（外部通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線的呼叫數量（也就是內部網路以外的連線）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均比對率（Kbits/s）</strong></p></td>
<td><p>否</p></td>
<td><p>平均視頻位元速率（以千位數/秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>低位比率%</strong></p></td>
<td><p>否</p></td>
<td><p>位元速率低的通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出資料包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>輸出資料包的即時傳輸通訊協定（RTP）資料包遺失。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>凍結的畫面%</strong></p></td>
<td><p>否</p></td>
<td><p>「凍結」畫面的百分比。 在凍結的畫面中，當通話的音訊部分繼續時，影片會停止向前進行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出平均畫面播放速率</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間輸出傳輸的平均畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸入平均畫面播放速率</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間內送傳輸的平均畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸入低畫面播放速率%</strong></p></td>
<td><p>否</p></td>
<td><p>傳入影片的位元速率低的通話百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>用戶端健康情況%</strong></p></td>
<td></td>
<td><p>表示通話期間用戶端裝置的相對健康情況。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>伺服器效能報告規格：應用程式共用通話摘要

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
<td><p><strong>呼叫類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。 通話類型包括：</p>
<ul>
<li><p>UC 對等通話</p></li>
<li><p>UC 會議會話</p></li>
<li><p>PSTN 會議會話</p></li>
<li><p>PSTN 電話：媒體旁路</p></li>
<li><p>PSTN 通話（非旁路）： UC 腿</p></li>
<li><p>PSTN 通話（非旁路）：閘道腿</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話量</strong></p></td>
<td><p>否</p></td>
<td><p>每個通話類型的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的通話總數。 較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話音量（無線通話）</strong></p></td>
<td><p>否</p></td>
<td><p>已使用無線連線的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話量（VPN 通話）</strong></p></td>
<td><p>否</p></td>
<td><p>已使用 VPN 連線的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話音量（外部通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線的呼叫數量（也就是內部網路以外的連線）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均相對單向</strong></p></td>
<td><p>否</p></td>
<td><p>兩個媒體端點之間的平均相對單向延遲。 這是一個單跳躍延遲測量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 .RDP 磚處理延遲時間</strong></p></td>
<td><p>否</p></td>
<td><p>在查看會話期間，AS 會議服務器中的 [作為會議中的平均 RDP 磚處理延遲]。 此統計不會涵蓋網路延遲。 高平均值會在觀賞體驗中反映較長的延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>總 spoiled 磚%</strong></p></td>
<td><p>否</p></td>
<td><p>Spoiled RDP 磚的總百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

