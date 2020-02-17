---
title: Lync Server 2013： 伺服器效能報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e60757721a9244a55e7ce341be6834934108858a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Lync Server 2013 中的伺服器效能報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

伺服器效能報告提供經歷最高-收訊不良通話百分比的 Microsoft Lync Server 2013 伺服器的清單。 報表會分解伺服器的伺服器類型，報告下列類型的不同統計資料：

  - 中繼伺服器

  - A/V Conferencing Server

  - A/V Edge Server

  - 閘道 （中繼伺服器）

  - 閘道 （中繼伺服器旁路）

  - 視訊 (包括視訊計量 a / V 會議伺服器和 A / V Edge server)

  - 應用程式共用 (包括應用程式共用計量 a / V 會議伺服器和 A / V Edge server)

請務必注意，在此報告中顯示成相對排名排名。 例如，假設您最壞打算執行的伺服器有其 1000 撥電話之間的一個收訊不良通話。 這是更多比接受百分比。 1%。 不過，如果這是最壞打算執行伺服器必須 (亦即，如果所有其他伺服器有即使低於收訊不良通話百分比。 1%)，然後該伺服器仍會出現在 [伺服器效能報告。

<div>

## <a name="accessing-the-server-performance-report"></a>存取伺服器效能報告

伺服器效能報告是從監視報告首頁存取。 您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：

  - [通話數

  - 通話不良百分比

此外，您可以按一下向下切入伺服器媒體品質趨勢報告下列計量：

  - Trend

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>伺服器效能報告的最佳用法

伺服器效能報告提供了數種方式來篩選資料;例如，您可以篩選網路類型 （從有線連線與從無線連線的呼叫進行的通話） 和存取類型 （內部防火牆與撥打從防火牆外部進行的通話）。 它是不錯的選項檢視伺服器效能報告進行時使用這些篩選器。 例如，假設您有中繼伺服器已 3.24%收訊不良通話百分比。 如果您查看察覺無線通話，該相同的伺服器可能達到 20%收訊不良通話百分比。 這表示，在伺服器已困難無線通話，因為伺服器已不會察覺有線來電的問題部分遮蔽問題。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，伺服器效能報告可讓您進行當作篩選傳回的資料的伺服器類型或網路型別 （也就是有線或無線） 等項目。 您也可以選擇資料的分組方式。 在此情況下，是由小時、 日、 週或月群組資料。

下表列出您可以搭配伺服器效能報告的篩選器。

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
<td><p><strong>伺服器類型</strong></p></td>
<td><p>會指出應該報告其效能的伺服器類型。 請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>中繼伺服器</p></li>
<li><p>A/V Conferencing Server</p></li>
<li><p>A/V Edge Server</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>榜尾數量</strong></p></td>
<td><p>若要顯示在每個類別會指出伺服器 （根據其通話不良百分比） 的數目。 例如，如果您選取<strong>5</strong>然後五個執行效能最差的伺服器會顯示。 請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>5 </p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>內部</p></li>
<li><p>External</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<ol>
<li><p>[全部]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出伺服器效能報告中提供的資訊。

### <a name="server-performance-report-metrics-audio-call-summary"></a>伺服器效能報告計量： 音訊通話摘要

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
<td><p>伺服器名稱] / [IP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話數</strong></p></td>
<td><p>否</p></td>
<td><p>撥打的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>否</p></td>
<td><p>歸類為不良的通話總數。 通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返時間 （毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。 100 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>降低 (MOS)</strong></p></td>
<td><p>是</p></td>
<td><p>平均量平均意見分數 (MOS) 降低在通話期間發生。 為 [高] 的 5.0，降低值可介於 0.0 的低。 為 0.5 或更低的值代表可接受的效能下降。 在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。 在 Lync Server 中，監控伺服器會使用一組演算法來預測如何使用者會有分級通話。</p>
<p>高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。 高降低的情形會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>封包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定 (RTP) 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動 (ms)</strong></p></td>
<td><p>是</p></td>
<td><p>偵測到之間 RTP 封包抵達的平均抖動值。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>是</p></td>
<td><p>之隱藏樣本總數總計的音訊樣本的平均比率。 （隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復延伸的比率</strong></p></td>
<td><p>是</p></td>
<td><p>範例總數總計的延伸音訊樣本的平均比率。 （延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復壓縮的比率</strong></p></td>
<td><p>是</p></td>
<td><p>範例總數的壓縮音訊樣本的平均比率。 （壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>伺服器效能報告計量： 視訊通話摘要

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
<td><p>輸出封包的即時傳輸通訊協定 (RTP) 封包遺失。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
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


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>伺服器效能報告計量： 應用程式共用通話摘要

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
<td><p>平均 RDP 並排檢視工作階段的持續時間內 AS 會議伺服器的處理延遲。 此計量並未涵蓋網路延遲。 高平均會反映檢視經驗中較長的延遲。 負載過重的會議伺服器可能會發生較高的平均延遲。</p></td>
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

