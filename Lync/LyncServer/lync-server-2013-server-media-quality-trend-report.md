---
title: Lync Server 2013： 伺服器媒體品質趨勢報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c7a9f1fbadb69f00982f52dfae264d6a4ce60d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>在 Lync Server 2013 伺服器媒體品質趨勢報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-12_

伺服器媒體品質趨勢報告可讓您以圖形方式比較最多 5 個伺服器上的經驗品質計量，例如通話數量、 收訊不良通話百分比、 封包遺失及抖動。 這樣做為識別執行效能不佳的伺服器、 識別伺服器，都未得到充分利用，或識別所要使用過度的伺服器此類事情更容易。

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>存取伺服器媒體品質趨勢報告

伺服器媒體品質趨勢報告可從下列報告的其中一個：

  - [Lync Server 2013 中的 server Performance Report](lync-server-2013-server-performance-report.md) (按一下趨勢計量）

  - [Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)(按一下 [A / V edge server] 計量。 如果來電者或受話者位於伺服器，您可能也會達到伺服器品質媒體趨勢報告的端點名稱，即可。）

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>伺服器媒體品質趨勢報告的最佳用法

當您按一下趨勢計量[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)的特定伺服器上時，將會開啟伺服器媒體品質趨勢報告。 不過，您會看到該報表; 中的空白執行個體在伺服器效能報告選取的伺服器不會顯示在螢幕上。 相反地，您必須從 [伺服器] 下拉式清單中選取該伺服器。 請注意，[伺服器] 下拉式清單中包含的所有選取的選項。 如果您有超過 5 伺服器; 此選項將無法運作伺服器媒體品質趨勢報告可以只會顯示一次最多 5 部伺服器的資料。

在 [伺服器媒體品質趨勢報告顯示的圖形，資料點標記為呼叫磁碟區，且收訊不良通話百分比不良率;按一下圖上的點將開啟[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)顯示的來電總數 （或不良通話數） 指定的時間期間內的執行個體。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以使用伺服器媒體品質趨勢報告篩選器。

### <a name="server-media-quality-trend-report-filters"></a>伺服器媒體品質趨勢報告篩選器

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
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 8 月 7 日及 2012 年 9 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>伺服器類型</strong></p></td>
<td><p>伺服器參與通話類型。 允許的值為：</p>
<ul>
<li><p>中繼伺服器</p></li>
<li><p>A/V Conferencing Server</p></li>
<li><p>A/V Edge Server</p></li>
<li><p>閘道 （中繼伺服器）</p></li>
<li><p>閘道 （中繼伺服器旁路）</p></li>
<li><p>AS 會議伺服器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>伺服器</strong></p></td>
<td><p>參與工作階段; 的伺服器名稱為您的伺服器類型篩選條件的值為基礎，會自動填入此下拉式清單。 編譯報表時，您可以選取最多 5 個不同的伺服器。</p></td>
</tr>
<tr class="even">
<td><p><strong>存取類型</strong></p></td>
<td><p>會指出是否參與者登入內部網路或外部網路。 允許的值為：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>內部</p></li>
<li><p>External</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>會指出參與者已連線至網路的類型。 允許的值為：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>會指出外部參與者是否已使用工作階段期間的虛擬私人網路 (VPN) 連線。 允許的值為：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出伺服器媒體品質趨勢報告提供的資訊。

### <a name="server-media-quality-trend-report-metrics"></a>伺服器媒體品質趨勢報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>[通話數</strong></p></td>
<td><p>否</p></td>
<td><p>通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>降低 (MOS)</strong></p></td>
<td><p>否</p></td>
<td><p>平均量 MOS （mean 選項分數） 降低在通話期間發生的詳細資訊。 降低值可介於 0.0 的低到高的 5.0;為 0.5 或更低的值代表可接受的效能下降。 在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。 Lync Server 使用一組演算法來預測如何使用者會有分級通話。</p>
<p>高的效能下降值會造成壅塞;缺少的頻寬;無線壅塞干擾，或已多載的媒體伺服器或端點。 高降低的情形會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>否</p></td>
<td><p>歸類為不良的通話總數。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返時間 （毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>平均時間 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳送到一個端點，再重新量。 200 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>即時傳輸通訊協定 (RTP) 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動 (ms)</strong></p></td>
<td><p>否</p></td>
<td><p>偵測到之間 RTP 封包抵達的平均抖動值。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>否</p></td>
<td><p>之隱藏樣本總數總計的音訊樣本的平均比率。 （隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復延伸的比率</strong></p></td>
<td><p>否</p></td>
<td><p>範例總數總計的延伸音訊樣本的平均比率。 （延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復壓縮的比率</strong></p></td>
<td><p>否</p></td>
<td><p>範例總數的壓縮音訊樣本的平均比率。 （壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

