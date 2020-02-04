---
title: Lync Server 2013：位置報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb42f32313acd3609b21180ddaef90c53c27564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a>Lync Server 2013 中的位置報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

位置報告會提供通話品質指標的相關資訊，依網路位置（也就是網路子網）分組。 如果您的使用者遇到通話問題，此報告可協助您判斷這些問題是否已廣泛分佈，或是主要限制在指定的網路區段中。

<div>

## <a name="accessing-the-location-report"></a>存取位置報告

位置報告是從 [監控報告] 首頁存取。 您可以按一下下列其中一個度量，向下切入 [通話清單] 報告：

  - 通話量

  - 通話百分比太差

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[位置] 報告可讓您篩選諸如通話來源的位置，或是通話是在無線或有線連線中進行。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、日、周或月進行分組。

下表列出可與位置報表搭配使用的篩選。

### <a name="location-report-filters"></a>位置報表篩選

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
<td><p><strong>來電者位置</strong></p></td>
<td><p>發出呼叫之使用者的 IP 子網。 您只可以選取<strong>[全部]</strong>來指示所有子網。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者位置</strong></p></td>
<td><p>接收通話之使用者的 IP 子網。 您只可以選取<strong>[全部]</strong>來指示所有子網。</p></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出撥打電話時，用戶端連線到的網路類型。 選取下列其中一項：</p>
<ol>
<li><p>同時</p></li>
<li><p>有線</p></li>
<li><p>無線</p></li>
</ol></td>
</tr>
<tr class="even">
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

下表列出位置報告中提供的資訊。

### <a name="location-report-metrics"></a>位置報告度量單位

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
<td><p><strong>來電者子網上</strong></p></td>
<td><p>否</p></td>
<td><p>發出呼叫之使用者的 IP 子網。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者子網上</strong></p></td>
<td><p>否</p></td>
<td><p>接收通話之使用者的 IP 子網。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話量</strong></p></td>
<td><p>是</p></td>
<td><p>已發出的通話總次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>是</p></td>
<td><p>分類為不良通話的通話百分比。 較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>往返行程（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。 100毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>下降（MOS）</strong></p></td>
<td><p>是</p></td>
<td><p>通話期間平均觀念得分（MOS）的平均數量下降。 降級值的範圍可從低0.0 到5.0。 0.5 或較低的值代表可接受的下降。 過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。 高品質的結果會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>資料包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖動</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 隱藏比例</strong></p></td>
<td><p>是</p></td>
<td><p>隱藏的音訊樣本與總樣本數的平均比率。 （隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>Healer 延伸比率</strong></p></td>
<td><p>是</p></td>
<td><p>延伸音訊樣本的平均比例與總樣本數的總和。 （已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Healer 壓縮比率</strong></p></td>
<td><p>是</p></td>
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

