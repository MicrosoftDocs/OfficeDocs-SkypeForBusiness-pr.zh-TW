---
title: Lync Server 2013：媒體質量摘要報告
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
ms.openlocfilehash: 4080460083074f7ad74618034ab2e7910de5e53d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516180"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的媒體質量摘要報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-29_

媒體質量摘要報告也許是在您的組織中分析通話品質的首選：此報告可提供詳細的經驗品質 (QoE 會分解為下列類別) 的呼叫計量。

  - UC 對等通話 (例如 Microsoft Lync 2013 至 Microsoft Lync 2013 通話) 

  - UC 會議會話

  - PSTN 會議會話

  - PSTN 通話：媒體旁路

  - PSTN 通話 (Non-Bypass) ： UC 腿

  - PSTN 通話 (Non-Bypass) ：閘道腿

  - 其他通話類型

當您第一次開啟報表時，您會看到每個類別的摘要資訊。 在未離開報告的情況下，您可以展開每個類別，以查看子類別，例如從 Office Communicator 2007 R2 進行的呼叫至 Lync 2013。 接著，您可以在這些子類別中深入查看，以查看該子類別中所進行之每個通話的詳細資料。

在 Microsoft Lync Server 2013 中，媒體質量摘要報告會進一步將資料分解為三種通話類型：音訊通話、影片通話和應用程式共用通話。 每個通話類型在報告中都有其自己的區段，以及其自己的自訂呼叫計量集。

媒體質量摘要報告也可讓您套用篩選器，讓您能夠比較有線通話的通話品質與無線通話、內部通話與外部通話，以及 VPN 呼叫與非 VPN 通話。

<div>

## <a name="accessing-the-media-quality-summary-report"></a>存取媒體質量摘要報告

媒體質量摘要報告可從監控報告的首頁進行存取。 您可以按一下下列其中一個計量，以深入瞭解 [Lync Server 2013 中的通話清單報告](lync-server-2013-call-list-report.md) ：

  - 通話數量

  - 通話百分比不佳

此外，您可以按一下下列任何音訊撥號計量，以存取媒體質量計量散佈報告：

  - 來回行程 (毫秒) 

  - MOS) 降級 (

  - 封包遺失

  - 抖動 (毫秒) 

  - 修復隱藏比率

  - 修復延伸比率

  - 修復壓縮比例

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，媒體質量摘要報告可讓您篩選傳回的資料，例如存取類型 (例如，「間隔存取」與「外部存取」) 或有線/無線網路連線。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配媒體質量摘要報告使用的篩選器。

### <a name="media-quality-summary-report-filters"></a>媒體質量摘要報告篩選器

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
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>內部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出媒體質量摘要報告中提供的資訊。

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>媒體質量摘要報告計量：音訊通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。 通話類型包括：</p>
<ul>
<li><p>UC Peer-to-Peer 通話</p></li>
<li><p>UC 會議會話</p></li>
<li><p>PSTN 會議會話</p></li>
<li><p>PSTN 通話：媒體旁路</p></li>
<li><p>PSTN 通話 (Non-Bypass) ： UC 腿</p></li>
<li><p>PSTN 通話 (Non-Bypass) ：閘道腿</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話數量</strong></p></td>
<td><p>否</p></td>
<td><p>每個通話類型的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的呼叫總數。 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="even">
<td><p><strong> (無線通話的電話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong> (VPN 呼叫的通話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話量 (外部呼叫) </strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來回行程 (毫秒) </strong></p></td>
<td><p>否</p></td>
<td><p>即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。 在100毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>MOS) 降級 (</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間 (MOS) 效能的平均平均觀點量。 降級值的範圍從低0.0 到高5.0。 值0.5 或更少代表可接受的降級。 在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。 高降級導致音訊失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>RTP 封包遺失的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 封包遺失通常會導致音訊失真或遺失。</p></td>
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


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>媒體質量摘要報告計量：影片通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。 通話類型包括：</p>
<ul>
<li><p>UC Peer-to-Peer 通話</p></li>
<li><p>UC 會議會話</p></li>
<li><p>PSTN 會議會話</p></li>
<li><p>PSTN 通話：媒體旁路</p></li>
<li><p>PSTN 通話 (Non-Bypass) ： UC 腿</p></li>
<li><p>PSTN 通話 (Non-Bypass) ：閘道腿</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話數量</strong></p></td>
<td><p>否</p></td>
<td><p>每個通話類型的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的呼叫總數。 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="even">
<td><p><strong> (無線通話的電話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong> (VPN 呼叫的通話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話量 (外部呼叫) </strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均位元速率 (Kb/s) </strong></p></td>
<td><p>否</p></td>
<td><p>平均影片位元速率 (以每秒千位數) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>低位率%</strong></p></td>
<td><p>否</p></td>
<td><p>位元速率低的通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出封包遺失</strong></p></td>
<td><p>否</p></td>
<td><p>Real-Time 傳輸通訊協定 (RTP) 輸出封包遺失。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>凍結的圖文框%</strong></p></td>
<td><p>否</p></td>
<td><p>「凍結」框架的百分比。 在凍結的框架中，當繼續通話的音訊部分時，影片會停止向前。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出平均畫面播放速率</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間輸出傳輸的平均畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸入平均畫面播放速率</strong></p></td>
<td><p>否</p></td>
<td><p>通話期間傳入傳輸的平均畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸入低框架速率%</strong></p></td>
<td><p>否</p></td>
<td><p>傳入影片的位元速率很低之通話的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>用戶端狀況%</strong></p></td>
<td></td>
<td><p>會指出通話期間用戶端裝置的相對健康情況。</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>媒體質量摘要報告計量：應用程式共用通話摘要

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
<td><p><strong>通話類型/端點類型</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。 通話類型包括：</p>
<ul>
<li><p>UC Peer-to-Peer 通話</p></li>
<li><p>UC 會議會話</p></li>
<li><p>PSTN 會議會話</p></li>
<li><p>PSTN 通話：媒體旁路</p></li>
<li><p>PSTN 通話 (Non-Bypass) ： UC 腿</p></li>
<li><p>PSTN 通話 (Non-Bypass) ：閘道腿</p></li>
<li><p>其他通話類型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話數量</strong></p></td>
<td><p>否</p></td>
<td><p>每個通話類型的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>否</p></td>
<td><p>分類為不良的呼叫總數。 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="even">
<td><p><strong> (無線通話的電話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用無線連線的呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong> (VPN 呼叫的通話量) </strong></p></td>
<td><p>否</p></td>
<td><p>使用 VPN 連線的呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話量 (外部呼叫) </strong></p></td>
<td><p>否</p></td>
<td><p>使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動 (毫秒) </strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均相對單向方式</strong></p></td>
<td><p>否</p></td>
<td><p>兩個媒體端點之間的平均相對單向延遲。 此為單一躍點延遲措施。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 .RDP 磚處理延遲</strong></p></td>
<td><p>否</p></td>
<td><p>在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲。 高平均反映的觀賞體驗中的延遲較長，包含網路延遲。 負載過重的會議伺服器可能會發生較高的平均延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>Spoiled 磚的總數%</strong></p></td>
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

