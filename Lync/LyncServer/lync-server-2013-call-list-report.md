---
title: Lync Server 2013：通話清單報告
description: Lync Server 2013：通話清單報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561689"
---
# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013 中的通話清單報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

通話清單報告提供經驗品質 (QoE 在組織中撥打和接收的個別通話) 度量。 請注意，實際報告的衡量值將取決於您存取通話清單報告的方式。 例如，如果您 [在 Lync Server 2013 的設備報告中](lync-server-2013-device-report.md)開啟報表，您會看到下列的計量值，也就是在裝置報表上報告的計量：

  - 來電者的麥克風

  - 來電者的喇叭

  - 被呼叫者的麥克風

  - 被呼叫者的喇叭

  - 語音切換時間的比例

不過，如果您在 [Lync Server 2013 的位置報告中](lync-server-2013-location-report.md)開啟通話清單報告，您就不會看到任何這類度量。相反地，您會看到如下的計量：

  - 來回行程 (毫秒) 

  - MOS) 降級 (

  - 封包遺失

  - 抖動 (毫秒) 

這些是在位置報告上報告的統計資料。 不過，從通話清單報告您可以隨時按一下 [詳細資料] 度量，以提供任何呼叫的完整 QoE 資訊。

<div>

## <a name="accessing-the-call-list-report"></a>存取通話清單報告

您可以從下列任何報告中存取通話清單報告：

  - [Lync Server 2013 (中的位置報告](lync-server-2013-location-report.md)，方法是按一下 [通話量] 或 [不良通話百分比] 度量) 

  - [Lync Server 2013 (中的裝置報表](lync-server-2013-device-report.md)，方法是按一下 [通話量] 或 [通話百分比] 度量值) 

  - [Lync Server 2013 (中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)，請按一下 [通話量] 或 [不良通話百分比] 度量) 

  - [Lync server 2013 (中的伺服器效能報告](lync-server-2013-server-performance-report.md)，按一下 [通話量] 或 [通話百分比] 度量值) 

在 [通話清單報告] 中，按一下 [詳細資料] 度量，即可存取 [Lync Server 2013 中的 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md) 。

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>充分利用通話清單報告

如果您無法記下某些「通話清單報告」度量 (例如，) 實際測量的比例語音切換時間，請將滑鼠停留在公制標籤上;然後會出現工具提示，提供度量的簡短描述。

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選通話清單報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出通話清單報告中每次通話所提供的資訊。

### <a name="call-list-report-metrics"></a>通話清單報告計量

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
<td><p><strong>詳細資料</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示通話的其他資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>是</p></td>
<td><p>發起通話之人員的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>方</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>通話的開始日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>通話的結束日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>起始通話之人員端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫者的端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>來回行程 (毫秒) </strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。 在100毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MOS) 降級 (</strong></p></td>
<td><p>是</p></td>
<td><p>通話期間 (MOS) 效能的平均平均觀點量。 降級值的範圍從低0.0 到高5.0。 值0.5 或更少代表可接受的降級。 在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。 高降級導致音訊失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>封包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 封包遺失的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復隱藏比率</strong></p></td>
<td><p>是</p></td>
<td><p>隱藏音訊樣本的平均比率與樣本總數總數。  (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修復延伸比率</strong></p></td>
<td><p>是</p></td>
<td><p>延伸音訊樣本的平均比例與樣本總數總數。  (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</p></td>
</tr>
<tr class="even">
<td><p><strong>修復壓縮比例</strong></p></td>
<td><p>是</p></td>
<td><p>壓縮音訊樣本的平均比率與樣本總數。  (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連線能力</strong></p></td>
<td><p>是</p></td>
<td><p>無線通訊連結的類型。 這通常是下列其中一項：</p>
<ul>
<li><p>繼 電器</p></li>
<li><p>直接</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

