---
title: Lync Server 2013： 通話清單報告
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
ms.openlocfilehash: 53b462644e2334f428b8cd9a46c0ca07472f6ee2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013 中的通話清單報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

Call List Report 提供個別通話進行與接收您組織中的經驗品質 (QoE) 計量。 請注意，實際的計量報告取決於您如何存取通話清單報告。 例如，如果您從[裝置報告在 Lync Server 2013 中](lync-server-2013-device-report.md)開啟報告，您會看到下列項目，也會在 「 裝置報告報告的評量等量值：

  - 發話者的麥克風

  - 發話者的喇叭

  - 受話者的麥克風

  - 受話者的喇叭

  - 語音交換時間的比率

不過，如果您從[Lync Server 2013 中的 Location Report](lync-server-2013-location-report.md)開啟通話清單報告，您不會看到任何這些度量資訊;相反地，您會看到如下的計量：

  - 往返時間 （毫秒）

  - 降低 (MOS)

  - 封包遺失

  - 抖動 (ms)

這些是上 Location Report 報告的評量。 然而，從 Call List Report 您可以隨時按一下提供任何通話的完整 QoE 資訊的詳細資料] 計量。

<div>

## <a name="accessing-the-call-list-report"></a>存取通話清單報告

可以從任何下列報告存取通話清單報告：

  - [Lync Server 2013 中的 Location Report](lync-server-2013-location-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）

  - [Lync Server 2013 中的 Device Report](lync-server-2013-device-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）

  - [Lync Server 2013 中的 Media Quality Summary Report](lync-server-2013-media-quality-summary-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）

  - [Lync Server 2013 中的 Server Performance Report](lync-server-2013-server-performance-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）

Call List Report 中您可以從存取[Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)詳細資料] 計量，即可。

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>通話清單報告的最佳用法

如果您忘記了哪些部分 （例如比率語音交換時間） 的通話清單報告計量實際測量，將滑鼠停留到計量標籤，工具提示會再出現提供該計量的簡短描述。

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選 Call List Report。

</div>

<div>

## <a name="metrics"></a>計量

下表列出每個呼叫 Call List Report 提供的資訊。

### <a name="call-list-report-metrics"></a>通話清單報告計量

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
<td><p><strong>詳細資料</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告就會顯示其他資訊通話。</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>是</p></td>
<td><p>啟動通話者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>受話者</strong></p></td>
<td><p>是</p></td>
<td><p>被呼叫者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間通話的開始。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間通話的結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>啟動通話者的端點所用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>被呼叫者端點所用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返時間 （毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。 100 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>降低 (MOS)</strong></p></td>
<td><p>是</p></td>
<td><p>平均量平均意見分數 (MOS) 降低在通話期間發生。 為 [高] 的 5.0，降低值可介於 0.0 的低。 為 0.5 或更低的值代表可接受的效能下降。 在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。 在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</p>
<p>高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。 高降低的情形會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>封包遺失</strong></p></td>
<td><p>是</p></td>
<td><p>RTP 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖動</strong></p></td>
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
<tr class="odd">
<td><p><strong>連線能力</strong></p></td>
<td><p>是</p></td>
<td><p>無線通訊連結的類型。 一般而言，這會是下列其中一項：</p>
<ul>
<li><p>轉送</p></li>
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

