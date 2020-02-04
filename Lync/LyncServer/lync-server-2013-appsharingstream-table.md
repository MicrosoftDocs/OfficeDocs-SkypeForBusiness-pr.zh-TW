---
title: Lync Server 2013： AppSharingStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AppSharingStream 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-21_

AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質度量單位。 此表格是在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話開始的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>使用順序識別碼來區分在相同日期和同一時間啟動的會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要、外部</p></td>
<td><p>代表通話中使用的影片線條類型。 允許的值為：</p>
<ul>
<li><p>0-音訊</p></li>
<li><p>1–影片</p></li>
<li><p>2-全景影片</p></li>
<li><p>3-應用程式/桌面共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>應用程式共用資料流程的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在 RTP 資料包抵達之間檢測到最大抖動。 （抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>環路</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。 200毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>即時傳輸通訊協定資料包要傳送到另一個端點的最大值（以毫秒為單位），然後返回。 200毫秒或較低的往返行程時間會視為可接受的品質。</p>
<p>國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>即時傳輸通訊協定（RTP）資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>即時傳輸通訊協定（RTP）資料包遺失率的最大值。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>已傳送的資料包數目。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會話結束時可使用的估計單向頻寬。 以每秒位數報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>應用程式共用負載的描述。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延隔時間的平均量。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延隔時間的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>單向突發發生次數總計。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總計單向突發密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總計單向突發持續時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總的單向間距發生情況。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總單向間距密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總共一個單向間距時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar （256）</p></td>
<td></td>
<td><p>應用程式角色（共用或檢視器）與內容類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚的總處理時間。 較高的總計相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚的平均處理時間。 較高的總計相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚的最大處理時間。 較高的總計相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間的突發事件發生方式。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間的暴沖密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間中的爆發時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間中的差距出現次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間的差距密度。 低差距密度可讓您獲得更佳的觀賞體驗。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>遠端桌面通訊協定（RDP）磚處理時間中的差距持續時間。 短差距期間會等同于更佳的觀賞體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>捕獲磚的總速率（每秒磚）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>捕獲磚的平均速率（每秒磚）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>捕獲磚的最大速率（每秒磚）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>在 t</p></td>
<td></td>
<td><p>在捕獲磚（每秒磚數）中，突發發生的頻率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>捕獲磚（每秒磚）的流量峰值密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>以捕獲磚（每秒磚）為單位的爆發時段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>間距出現在捕獲磚的速率中（每秒磚）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>已捕獲磚（每秒磚）中的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>所捕獲磚（每秒磚）中的差距間隔時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器的內容總百分比，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器的內容平均百分比，而是由新內容捨棄並覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器的內容的最大百分比，而是由新內容捨棄並覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>無法到達檢視器的內容突發事件，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器之內容的突發密度，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>無法到達檢視器之內容的爆發持續時間，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>未到達檢視器之內容的差距出現次數，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器之內容的差距密度，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>未到達檢視器之內容的差距持續時間，但已被新內容捨棄並覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的畫面總 scraped 數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的平均幀 scraped 數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源中的最大幀 scraped 數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>來自圖形來源的 [幀 scraped] 中的 [突發] 出現次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的 [幀 scraped] 中的 [暴沖密度]。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的 [幀 scraped] 中的 [突發期間]。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>圖形來源的 [幀 scraped] 中的空隙出現次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的 [框架 scraped] 中的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>圖形來源的 [框架 scraped] 中的 [空隙] 工期。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入畫面播放速率總計。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的平均接收畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的傳入磚速率上限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收到的傳入磚速率中的爆發次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入磚速率中的高載密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入磚速率中的爆發持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收的傳入磚速率中的間距值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入磚速率中的差距密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的內送磚速率中的差距持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入畫面播放速率總計。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的平均接收畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的最大傳入畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收到的傳入畫面播放速率中的爆發次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的傳入畫面播放速率中的暴沖密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收到的傳入畫面播放速率中的爆發持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收到的內送畫面播放速率中出現的間距。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入畫面播放速率中的差距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>檢視器接收的傳入畫面播放速率中的差距持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄磚率總計。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的平均外寄磚速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的最大外寄磚速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的傳出磚速率中的突發事件。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的傳出磚速率的高載密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的傳出磚頻率內的爆發持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的外寄磚頻率中出現空隙。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄磚工資率的差距密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄磚工資率的差距持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率總計。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的平均傳出畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的最大外寄畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者在外寄畫面播放速率中的突發事件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率中的暴沖密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率中的爆發持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率中出現空隙。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率中的差距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者的外寄畫面播放速率中的差距持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均視頻解析度高度（以圖元為單位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以圖元為單位的平均視頻解析度寬度。</p></td>
</tr>
<tr class="even">
<td><p><strong>進貨</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>入站傳輸的平均畫面播放速率（在每秒的幀數）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>發</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>輸出傳送的平均畫面播放速率（在每秒的幀數）。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>1表示資料流程方向從來電者到被叫方。</p>
<p>0表示資料流程方向是從被叫方到來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

