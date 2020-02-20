---
title: Lync Server 2013： 媒體品質摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa7c620cff3247e4d744f60c24e0f5aa6293da3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體品質摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-06-29_

媒體品質摘要報告或許是您分析您的組織中的通話品質的最佳選擇： 這份報告提供詳細的經驗品質 (QoE) 通話衡量標準，向下切分為下列類別：

  - UC 對等通話 （例如 Microsoft Lync 2013 呼叫 Microsoft Lync 2013)

  - UC 會議工作階段

  - PSTN 會議工作階段

  - PSTN 通話： 媒體旁路

  - PSTN 通話 （非旁路）： UC Leg

  - PSTN 通話 （非旁路）： 閘道 Leg

  - 其他通話類型

當您第一次開啟報表時，您會看到每個類別的摘要資訊。 不需要離開報表，您可以展開每個類別，查看子類別，例如從 Office Communicator 2007 R2 至 Lync 2013 進行的通話。 接著，您可以再向下鑽研至若要查看每個內的子類別所進行的通話詳細這些子類別。

在 [Microsoft Lync Server 2013 媒體品質摘要報告進一步會向下資料分成三種通話類型： 音訊通話、 視訊通話及應用程式共用通話。 每個通話類型都有其專屬報告區段中，而且它自己的自訂設定的通話衡量標準。

Media Quality Summary Report 也可讓您套用篩選器，可讓您比較有線的撥打與無線通話、 內部撥打與外部通話，以及和非 VPN 通話比較 VPN 通話的通話品質。

<div>

## <a name="accessing-the-media-quality-summary-report"></a>存取媒體品質摘要報告

從監視報告首頁存取媒體品質摘要報告。 您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：

  - [通話數

  - 通話不良百分比

此外，您可以按一下任何下列的音訊通話衡量標準來存取媒體品質計量散佈報告：

  - 往返時間 （毫秒）

  - 降低 (MOS)

  - 封包遺失

  - 抖動 (ms)

  - 修復隱藏比率

  - 修復延伸的比率

  - 修復壓縮的比率

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，媒體品質摘要報告可讓您存取類型 （也就是與外部存取的時間間隔存取） 等事項或是有線/無線網路連線篩選傳回的資料。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配媒體品質摘要報告的篩選器。

### <a name="media-quality-summary-report-filters"></a>媒體品質摘要報告篩選器

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
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>內部</p></li>
<li><p>External</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
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

下表列出媒體品質摘要報告提供的資訊。

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>媒體品質摘要報告衡量標準： 音訊通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。 通話類型包括：</p>
<ul>
<li><p>UC 對等通話</p></li>
<li><p>UC 會議工作階段</p></li>
<li><p>PSTN 會議工作階段</p></li>
<li><p>PSTN 通話： 媒體旁路</p></li>
<li><p>PSTN 通話 （非旁路）： UC Leg</p></li>
<li><p>PSTN 通話 （非旁路）： 閘道 Leg</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話數</strong></p></td>
<td><p>否</p></td>
<td><p>每一種通話類型通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>否</p></td>
<td><p>歸類為不良的通話總數。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （無線通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話數 （VPN 通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （外部通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 （亦即內部網路外部連接） 的通話數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>往返時間 （毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。 100 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>降低 (MOS)</strong></p></td>
<td><p>否</p></td>
<td><p>平均量平均意見分數 (MOS) 降低在通話期間發生。 為 [高] 的 5.0，降低值可介於 0.0 的低。 為 0.5 或更低的值代表可接受的效能下降。 在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</p>
<p>高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。 高降低的情形會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>RTP 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
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


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>媒體品質摘要報告衡量標準： 視訊通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。 通話類型包括：</p>
<ul>
<li><p>UC 對等通話</p></li>
<li><p>UC 會議工作階段</p></li>
<li><p>PSTN 會議工作階段</p></li>
<li><p>PSTN 通話： 媒體旁路</p></li>
<li><p>PSTN 通話 （非旁路）： UC Leg</p></li>
<li><p>PSTN 通話 （非旁路）： 閘道 Leg</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話數</strong></p></td>
<td><p>否</p></td>
<td><p>每一種通話類型通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>否</p></td>
<td><p>歸類為不良的通話總數。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （無線通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話數 （VPN 通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （外部通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 （亦即內部網路外部連接） 的通話數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均位元速率 （Kb/秒）</strong></p></td>
<td><p>否</p></td>
<td><p>平均視訊位元速率 （每秒的 kb）。</p></td>
</tr>
<tr class="even">
<td><p><strong>低位元速率 %]</strong></p></td>
<td><p>否</p></td>
<td><p>其中的位元速率較低的通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出封包遺漏</strong></p></td>
<td><p>否</p></td>
<td><p>輸出封包的即時傳輸通訊協定 (RTP) 封包遺失。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>[凍結的畫面 %]</strong></p></td>
<td><p>否</p></td>
<td><p>「 凍結 」 畫面的百分比。 在 [凍結的畫面，影片會停止前進時通話的音訊部分會繼續執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出平均播放速率]</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間輸出傳輸的平均播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸入的平均播放速率]</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間輸入傳輸的平均播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸入低播放速率 %]</strong></p></td>
<td><p>否</p></td>
<td><p>其中傳入的視訊的位元速率較低的通話百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>用戶端健康情況 %]</strong></p></td>
<td></td>
<td><p>通話期間會指出用戶端裝置的相關健康情況。</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>媒體品質摘要報告衡量標準： 應用程式共用通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。 通話類型包括：</p>
<ul>
<li><p>UC 對等通話</p></li>
<li><p>UC 會議工作階段</p></li>
<li><p>PSTN 會議工作階段</p></li>
<li><p>PSTN 通話： 媒體旁路</p></li>
<li><p>PSTN 通話 （非旁路）： UC Leg</p></li>
<li><p>PSTN 通話 （非旁路）： 閘道 Leg</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話數</strong></p></td>
<td><p>否</p></td>
<td><p>每一種通話類型通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>否</p></td>
<td><p>歸類為不良的通話總數。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （無線通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話數 （VPN 通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話數 （外部通話）</strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 （亦即內部網路外部連接） 的通話數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動 (ms)</strong></p></td>
<td><p>否</p></td>
<td><p>偵測到之間 RTP 封包抵達的平均抖動值。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均相對的其中一種方式</strong></p></td>
<td><p>否</p></td>
<td><p>平均相對單向之間的延遲兩個媒體端點。 此為單一躍點延遲措施。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 RDP 並排顯示處理延遲</strong></p></td>
<td><p>否</p></td>
<td><p>平均 RDP 並排檢視工作階段的持續時間內 AS 會議伺服器的處理延遲。 高平均反映觀賞體驗，請在較長延遲，並包含網路延遲。 負載過重的會議伺服器可能會發生較高的平均延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>總毀損之並排顯示 %</strong></p></td>
<td><p>否</p></td>
<td><p>毀損之 RDP 並排顯示的總百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

