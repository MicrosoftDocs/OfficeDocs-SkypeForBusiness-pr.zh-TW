---
title: 'Lync Server 2013: AppSharingStream 表'
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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AppSharingStream 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-21_

AppSharingStream 表包含用於應用程式共用的網路資料流的經驗品質計量。 Microsoft Lync Server 2013 中已採用此表格。


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
<th><strong>主索引鍵 /</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>主要、外部</p></td>
<td><p>日期和啟動工作階段的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用來區分工作階段的開始日期相同，並同時連續的識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主要，外部</p></td>
<td><p>代表呼叫時所使用的視訊線的類型。 允許的值為：</p>
<ul>
<li><p>0 – 音訊</p></li>
<li><p>1 – 影片</p></li>
<li><p>2 – 全景視訊</p></li>
<li><p>3 – 應用程式/桌面共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>應用程式共用資料流的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>偵測到之間 RTP 封包抵達的平均抖動值。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>偵測到 RTP 封包抵達之間的最大抖動。 (抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來回</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均量 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳輸至另一個端點，再重新。 200 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>最大量 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳輸至另一個端點，再重新。 200 毫秒或更低的來回行程時間會被視為的可接受的品質。</p>
<p>高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。 高的來回行程時間會導致雙向、 即時音訊交談的問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>即時傳輸通訊協定 (RTP) 封包遺失平均速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>即時傳輸通訊協定 (RTP) 封包遺失量的最大速率。 （封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。 封包遺失通常會導致扭曲或遺失音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>傳送的封包數。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>估計可用的單向頻寬工作階段的結尾。 報告每秒位元數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>共用裝載的應用程式的描述。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總數量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>平均量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最大數量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向的高載發生次數。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的高載密度。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的高載持續時間。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向的缺口發生次數。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的缺口密度。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向缺口持續時間。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar(256)</p></td>
<td></td>
<td><p>應用程式角色 （共享者或檢視器） 及內容類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚的總處理時間。 較高的總等於長的延遲時間，以檢視體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>平均處理時間遠端桌面通訊協定 (RDP) 磚。 較高的總等於長的延遲時間，以檢視體驗。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚的最大處理時間。 較高的總等於長的延遲時間，以檢視體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚之處理時間內，高載發生次數。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚之處理時間內，高載密度。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載持續時間在遠端桌面通訊協定 (RDP) 磚之處理時間。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口密度。 低表示的缺口密度等於較佳的檢視經驗。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口持續時間。 簡短表示的缺口持續時間等同於較佳的檢視經驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>擷取磚 （單位為每秒磚數） 的總速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>擷取磚 （單位為每秒磚數） 的平均速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>擷取磚 （單位為每秒磚數） 的最大速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>高載發生次數 （單位為每秒磚數） 擷取磚的速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載密度 （單位為每秒磚數） 擷取磚的速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載持續時間 （單位為每秒磚數） 擷取磚的速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>（單位為每秒磚數） 擷取磚速率表示的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>（單位為每秒磚數） 擷取磚速率表示的缺口密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>（單位為每秒磚數） 擷取磚速率表示的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的總百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的平均百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的最大百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>高載發生次數未抵達檢視者而被捨棄並以更新內容覆寫之內容。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載密度未抵達檢視者而被捨棄並以更新內容覆寫之內容。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載持續時間之內容的未抵達檢視者而被捨棄並以更新內容覆寫。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的平均數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消去的數目上限。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從圖形來源消高載發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消高載密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消高載持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>從圖形來源消表示的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消表示的缺口密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>從圖形來源消表示的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的總傳入畫面速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的平均傳入畫面速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的最大的傳入磚速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>高載發生次數的傳入磚速率，以檢視者接收到。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載密度的傳入磚速率，以檢視者接收到。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載持續時間的傳入磚速率，以檢視者接收到。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以檢視者接收到的傳入磚速率表示的缺口發生次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的傳入磚速率表示的缺口密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的傳入磚速率表示的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的總傳入畫面速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的平均傳入畫面速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最大傳入畫面速率為以檢視者接收到。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>高載發生次數的傳入畫面速率，以檢視者接收到。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載密度的傳入畫面速率，以檢視者接收到。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>高載持續時間的傳入畫面速率，以檢視者接收到。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>以檢視者接收到的傳入畫面速率表示的缺口發生次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的傳入畫面速率表示的缺口密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以檢視者接收到的傳入畫面速率表示的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>傳出磚總速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>傳出磚平均速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最大傳出磚速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>表示之高載發生次數之傳出磚速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示之高載密度之傳出磚速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示之高載持續時間之傳出磚速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>表示的缺口發生次數之傳出磚速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者之傳出磚速率表示的缺口密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者之傳出磚速率表示的缺口持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>傳出畫面總速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>傳出畫面平均速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最大傳出畫面速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>表示之高載發生次數之傳出畫面速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示之高載密度之傳出畫面速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示之高載持續時間之傳出畫面速率寄件者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>表示的缺口發生次數之傳出畫面速率寄件者。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者之傳出畫面速率表示的缺口密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者之傳出畫面速率表示的缺口持續時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均視訊解析度高度，以像素為單位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均視訊解析度寬度，以像素為單位。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸入</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>平均畫面速率 （以每秒畫面數） 輸入傳輸。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>平均播放速率 （以每秒） 輸出傳輸的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>1 表示資料流是從發話者流向受話者。</p>
<p>0 表示資料流是從受話者流向發話者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

