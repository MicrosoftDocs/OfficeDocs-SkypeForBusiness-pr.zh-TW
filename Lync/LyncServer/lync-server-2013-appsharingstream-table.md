---
title: Lync Server 2013： AppSharingStream 表格
description: Lync Server 2013： AppSharingStream 表格。
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
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574719"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AppSharingStream 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-21_

AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質計量。 此表格已引進 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話開始的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用來區分在相同日期和同一時間開始之會話的連續識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要，外部</p></td>
<td><p>代表通話中使用的影片線條類型。 允許的值為：</p>
<ul>
<li><p>0–音訊</p></li>
<li><p>1–影片</p></li>
<li><p>2–全景影片</p></li>
<li><p>3–應用程式/桌面共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>應用程式共用資料流程的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在 RTP 封包抵達之間偵測到的最大抖動。  (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>往返</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。 在200毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Real-Time 傳輸通訊協定資料包移至另一個端點後，所需的 (（毫秒）) 數目上限。 在200毫秒或更少的來回行程時間，會考慮可接受的品質。</p>
<p>高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。 較高的往返時間會導致使用雙向即時音訊交談的困難。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p> (RTP) 封包遺失 Real-Time 傳輸通訊協定的最大速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。 封包遺失通常會導致音訊失真或遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>傳送的封包數目。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在會話結束時可使用的預估單向頻寬。 每秒的位數報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>應用程式共用負載的描述。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的平均金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向突發的發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向爆炸流量密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向突發持續時間。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>對單向間隔的總發生次數。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向間距密度。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總的單向間距持續時間。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256) </p></td>
<td></td>
<td><p> (共用或檢視器的應用程式角色) 和內容類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 麻將牌的總處理時間。 較高的總數相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚的平均處理時間。 較高的總數相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚的處理時間上限。 較高的總數相當於觀賞體驗中較長的延遲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 的處理時間中的爆發發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚的處理時間中的暴沖密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP 的處理時間中的暴沖持續時間) 磚。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定的處理時間中的缺口發生次數 (RDP) 麻將牌。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 圖塊的處理時間中的缺口密度。 低間距密度相當於更好的觀賞體驗。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP 的處理時間中的缺口持續時間) 麻將牌。 短的缺口持續時間等於更好的觀賞體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>每秒 (每秒磚) 中的捕獲磚總速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>每秒 (每秒磚的已捕獲磚的平均速率) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>每秒 (每秒的磚) 中所捕獲的麻將牌的最大速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>在 t</p></td>
<td></td>
<td><p>以每秒 (每秒磚數為單位所捕獲的麻將牌的速率) 中的爆發次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>) 中每秒 (以每秒所捕獲的麻將牌速率為單位的流量密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以每秒磚數 (為單位的每秒) 中捕獲的磚的流量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以每秒貼圖)  (所捕獲的麻將牌速率為單位的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的總百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的平均百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的最大百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的爆發發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器之內容的暴沖密度，但已被捨棄並以全新內容覆寫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的暴沖持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器之內容的缺口密度，但已被捨棄並以全新內容覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的框架總數目。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的平均框架數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的最大相框數目。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從圖形來源消去的幀中的出現爆發。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去之框架中的流量密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去之框架中的暴沖持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從圖形來源消去之框架中的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去之框架中的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去之框架中的空隙 duration。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收到的內送框架速率總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收的平均內送框架速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器所收到的傳入磚率上限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>由檢視器接收的傳入磚速率中的突發流量。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由檢視器接收的傳入磚速率中的暴沖密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由檢視器接收的傳入磚速率中的暴沖持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>由 viewer 接收的內送磚速率中的間距發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由 viewer 接收的內送磚速率中的間距密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>依檢視器接收的內送磚速率中的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收到的內送框架速率總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收的平均內送框架速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收到的內送框架速率上限。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收的內送畫面播放速率中的突發流量發生方式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由檢視器接收的內送畫面播放速率中的暴沖密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以瀏覽器接收的傳入相框速率中的暴沖持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>檢視器接收的內送畫面播放速率中的間距發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>檢視器接收的內送框架速率中的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>依檢視器接收的內送框架速率中的間距持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的傳出磚總速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的平均傳出磚速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的傳出磚流量上限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以寄件者的傳出磚速率表示的突發流量發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以傳送者之傳出磚速率表示的暴沖密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以寄件者的傳出磚速率表示的暴沖持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以寄件者的傳出磚速率表示的缺口發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以寄件者的傳出磚速率表示的缺口密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以寄件者的傳出磚速率表示的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的傳出畫面速率總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的平均傳出畫面速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的最大傳出畫面速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的傳出畫面速率中的暴沖出現次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的傳出畫面速率中的暴沖密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以寄件者的傳出畫面速率表示的暴沖持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以寄件者的傳出畫面速率表示的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者的傳出畫面速率中的間距密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以寄件者的傳出畫面速率表示的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>影片的平均解析度高度（以圖元為單位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>影片的平均解析度寬度（以圖元為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>入境</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>輸入傳輸的平均每秒幀 () 的平均框架速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>出境</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>輸出傳輸) 每秒幀中 (的平均框架速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>1表示資料流程的方向從來電者到被叫方。</p>
<p>0表示資料流程方向從被叫方傳送給來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

