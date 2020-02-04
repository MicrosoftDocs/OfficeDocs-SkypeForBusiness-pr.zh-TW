---
title: Lync Server 2013：通話清單報告
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
ms.openlocfilehash: ce2954f848d448676aea2931cda4dffa8ddc0c5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013 中的通話清單報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[通話清單] 報告提供在貴組織中撥打及接聽的個別通話的經驗品質（QoE）度量單位。 請注意，報告的實際度量單位會視您存取通話清單報告的方式而定。 例如，如果您從[Lync Server 2013 的裝置報表](lync-server-2013-device-report.md)開啟報表，您會看到如下所示的度量標準，也就是在裝置報表上報告的度量值：

  - 來電者麥克風

  - 來電者的喇叭

  - 被呼叫者的麥克風

  - 被呼叫者的喇叭

  - 語音切換時間的比率

不過，如果您在[Lync Server 2013](lync-server-2013-location-report.md)的 [位置] 報告中開啟 [通話清單] 報告，就不會看到任何這些指標;相反地，您會看到如下所示的統計資料：

  - 往返行程（毫秒）

  - 下降（MOS）

  - 資料包遺失

  - 抖動（毫秒）

這些是在位置報告上報告的度量單位。 不過，您隨時可以在通話清單報告中按一下詳細資料，以提供任何通話的完整 QoE 資訊。

<div>

## <a name="accessing-the-call-list-report"></a>存取通話清單報告

您可以從下列任何一種報告存取通話清單報告：

  - [Lync Server 2013 中的位置報告](lync-server-2013-location-report.md)（按一下通話量或較差的通話百分比指標）

  - [Lync Server 2013 中的裝置報告](lync-server-2013-device-report.md)（按一下通話量或較差的通話百分比指標）

  - [Lync Server 2013 中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)（按一下通話量或較差的通話百分比指標）

  - [Lync server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)（按一下通話量或較差的通話百分比指標）

在通話清單報告中，您可以按一下詳細資料度量，[以存取 Lync Server 2013 中的 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>充分利用通話清單報告

如果您不記得一些通話清單報告的度量單位（例如語音切換時間）實際測量，請將滑鼠停留在公制標籤上;接著會出現工具提示，提供規格的簡短描述。

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法篩選通話清單報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出 [通話清單] 報告中針對每個通話提供的資訊。

### <a name="call-list-report-metrics"></a>通話清單報告度量單位

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
<td><p><strong>詳細資料</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示通話的其他資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫</strong></p></td>
<td><p>是</p></td>
<td><p>啟動通話之人的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>方</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>通話開始的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>通話結束的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>本機號碼使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>啟動通話之人的端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫者的端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返行程（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。 100毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>下降（MOS）</strong></p></td>
<td><p>是</p></td>
<td><p>通話期間平均觀念得分（MOS）的平均數量下降。 降級值的範圍可從低0.0 到5.0。 0.5 或較低的值代表可接受的下降。 過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。 在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</p>
<p>高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。 高品質的結果會造成失真或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>資料包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動</strong></p></td>
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
<tr class="odd">
<td><p><strong>連通</strong></p></td>
<td><p>是</p></td>
<td><p>[無線通訊] 連結的類型。 通常，這是下列其中一項：</p>
<ul>
<li><p>轉送</p></li>
<li><p>播放</p></li>
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

