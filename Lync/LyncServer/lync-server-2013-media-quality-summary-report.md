---
title: Lync Server 2013：媒體質量摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c967c6d6b120c73cb933281d4edb17be1868900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 [媒體質量摘要] 報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-29_

媒體質量摘要報告可能是您在組織中分析通話品質的最佳做法：此報告提供詳細的體驗品質（QoE）通話度量單位，分為下列類別：

  - UC 對等呼叫（例如 Microsoft Lync 2013 至 Microsoft Lync 2013 通話）

  - UC 會議會話

  - PSTN 會議會話

  - PSTN 電話：媒體旁路

  - PSTN 通話（非旁路）： UC 腿

  - PSTN 通話（非旁路）：閘道腿

  - 其他通話類型

當您第一次開啟報表時，您會看到每個類別的摘要資訊。 您可以在不離開報表的情況下展開每個類別，以查看子類別，例如從 Office Communicator 2007 R2 撥打到 Lync 2013 的情況。 接著，您可以向下切入這些子類別，以查看在該子類別中所做的每個通話的詳細資料。

在 Microsoft Lync Server 2013 中，媒體質量摘要報告會進一步將資料分解為三種通話類型：語音通話、視頻通話和應用程式共用通話。 每個通話類型在報表中都有自己的區段，以及自己的自訂通話測量指標集合。

[媒體質量摘要] 報告也可讓您套用篩選，讓您可以比較有線通話的通話品質與無線通話、內部通話與外部通話，以及 VPN 通話與非 VPN 通話。

<div>

## <a name="accessing-the-media-quality-summary-report"></a>存取媒體質量摘要報告

[媒體質量摘要] 報告是從 [監控報告] 首頁存取。 您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：

  - 通話量

  - 通話百分比太差

此外，您可以按一下下列任何一種音訊通話指標，以存取媒體質量度量分佈報告：

  - 往返行程（毫秒）

  - 下降（MOS）

  - 資料包遺失

  - 抖動（毫秒）

  - Healer 隱藏比例

  - Healer 延伸比率

  - Healer 壓縮比率

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，媒體質量摘要報告可讓您篩選傳回的資料，例如存取類型（也就是間隔存取與外部存取）或有線/無線網路連線等。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、日、周或月進行分組。

下表列出您可搭配媒體質量摘要報告使用的篩選。

### <a name="media-quality-summary-report-filters"></a>媒體質量摘要報表篩選

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
<td><p><strong>Access 類型</strong></p></td>
<td><p>指出撥打電話時，用戶端是否已登入內部網路或外部網路。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>內部</p></li>
<li><p>外來</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出撥打電話時，用戶端連線到的網路類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>點對點</strong></p></td>
<td><p>指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>點對點</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 [媒體質量摘要] 報告中提供的資訊。

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>媒體質量摘要報表度量單位：語音通話摘要

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
<td><p><strong>往返行程（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。 100毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>下降（MOS）</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間平均觀念得分（MOS）的平均數量下降。 降級值的範圍可從低0.0 到5.0。 0.5 或較低的值代表可接受的下降。 過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。 高品質的結果會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>資料包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>RTP 資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
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


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>媒體質量摘要報表度量單位：影片通話摘要

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
<td><p>輸出資料包的即時傳輸通訊協定（RTP）資料包遺失。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
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


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>媒體質量摘要報告規格：應用程式共用通話摘要

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
<td><p>在查看會話期間，AS 會議服務器中的 [作為會議中的平均 RDP 磚處理延遲]。 高平均值會在觀賞體驗中反映較長的延遲時間，並包含網路延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。</p></td>
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

